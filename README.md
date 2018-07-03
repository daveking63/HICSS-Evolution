# HICSS-Evolution

Interactive visualizations celebrating 50 years of scientific work at HICSS.  Code underlying visual displays of "HICSS Evolution" selection at  http://hicss.hawaii.edu/

*****  DRAFT IN PROCESS

In celebration of the 50th anniversary of the Hawaiian International Conference on System Sciences I undertook an analysis of all the conference proceedings from 1968-2017. The focus was on tracking the changes in both the structure and the content of the conference from the early beginnings of IT to the present day.  In large part, this turned out to be a massive project not only because of the the structure of the organization, conference and proceedings but also because of the changes in the media used to record the proceedings/abstracts/papers across the years -- from paper handouts, to bound paper volumes, to PDFs, to floppy disks, to CDs, to thumb drives and to online repositories.  The result is that much of the data collection for the years prior to mid-90s had to be done manually -- typing in various TOCs -- and specialized programs had to be created to "scrape and clean" the myriad of data formats used from one year to the next. In the end, I decided to focus on analyzing data found in the table of contents (TOCs) for each of the 50 track proceedings. The TOCs provided information about the changing structure of the conference, as well as detailed information about the paper titles and the associated authors.

<h3>Data Set</h3>

Just like many other data analysis projects, "data wrangling" took the bulk of the time (measured in months, not days). The primary result from the wrangling process was an Excel file <EM>HICSS_1968-2017_Trk_MT_Pap_Aut.xlsx</EM> consisting of ~39K rows of data containing the following fields for each row:

| CID | CNum | CYear | TID | TName | TAbbrev | MID | MName | PID | PTitle | AID | AName |
|---|---|---|---|---|---|---|---|---|---|---|---|---|

Here,

- The letters "C, T, M, P, and A" refer to the Conference, Track, Minitrack, Paper, and Author, respectively.
- The IDs are unique identifiers for their respectively entities (e.g. TID is a uniquely assigned Track ID)
- For papers with co-authors, all the info except the AID and AName is duplicated for each author

Obviously, this format results in quite a bit of redundancy from one row to the next because most papers have multiple co-authors. While the size of the data set could have been reduced by storing it in either a relational or noSQL database, the data was stored in Excel primarily because it simplified the process of analyzing the data (much of which required the construction of simple frequency distributions and crosstabs).

<h3>Analyzing the Data</h3>

The analysis of the data set had two phases.  The first of these focused on the evolution of the organization and structure of the conference.  The second on the evolution of the content.

**Changes in Organization and Structure**

Besides intellectual curiousity, a major impetus behind this analysis is that the HICSS leadership wanted to post this information to the HICSS50 website to serve as a visual reminder of HICSS' long history and to entice viewers to attend the 50th anniversary meeting. Towards this end, they decided to rely on Tableau's public website in order to: (1) easily produce a visual analysis of the data; and (2) seamless link this analysis to the HICSS site.

Even though the 50th anniversary has come and gone, the link to the visualizations still exists. It can be accessed by going to the HICSS site -- http://hicss.hawaii.edu/ -- scrolling down to the middle of the page, and clicking on *HICSS Evolution*. This will link to a project on the Tableau site:

https://public.tableau.com/profile/kaveh.abhari#!/vizhome/HICSS50_0/AreaChartsofCounts

The data can also be accessed at:

https://public.tableau.com/profile/david.king7957#!/

Regardless, either set of visualizations will provide information about:

History of Tracks (1968-2017) : Year Start and End<br>
Summary of Key Counts by Year (1968-2017)<br>
Summary of Key Ratios (1977-2017)<br>
Number and % of Minitracks by Track and Year (1977-2017)<br>
Number and % of Papers by Track and Year (1977-2017)<br>
Number and % of Authors by Track and Year (1977-2017)<br>
Area Charts - Number per Year by Track (1977-2017)<br>
Mean Number of Authors per Paper by Year and Track (1968-2017)<br>
Authorship: Papers by Number of Authors and Authors by Number of Papers (1968-2017)<br>

**Changes in Content**

Of less interest to the general HICSS population, but of more interest to me, was the changes in "content" over the years.  Ideally, this analysis would have involved an analysis of either the paper abstracts or   As noted, the changes in conference content were analyzed by performing various sorts of textual analysis on the paper titles.  This was carried out by first generating a data set containing a list of all the titles along with the year, track and minitracks in which they appeared.  Next, the file was read into a Python program which utilized Python's natural language toolkit (NLTK) to extract the terms, stems, bigrams and trigrams in the titles.  Various statistical analyses -- primarily frequency counts and crosstabulations by year, track and minitracks - were then performed on the extractions (e.g. answering questions such as: What were the top 10 terms, stems, bigrams and trigrams by year?).

In addition to the statistical analysis, 

In addition to the statistical analysis


