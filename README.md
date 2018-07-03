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

The analysis of the data set had two foci. 

**Changes in Structural and Participation**

Besides intellectual curiousity, a major impetus behind this analysis is that the HICSS leadership wanted to post this information to the HICSS50 website to serve as a visual reminder of the conferences long history and to entice viewers to attend the 50th anniversary meeting. They had decided to use the public Tableau site which provides a straightforward way to produce data visualizations for online public consumption. Towards this end, pivot tables were used with the Excel dataset to produce various text files that could be analyzed with Tableau.  

The link to the visualizations still exists and is available on the HICSS web site (http://hicss.hawaii.edu/ -- scroll down to the middle of the page to access the HICSS Evolution link). The HICSS link will lead to:

https://public.tableau.com/profile/kaveh.abhari#!/vizhome/HICSS50_0/AreaChartsofCounts

The data can also be access at:

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

As noted, the changes in conference content were analyzed by performing various sorts of textual analysis on the paper titles.  This was carried out by first generating a data set containing a list of all the titles along with the year, track and minitracks in which they appeared.  Next, the file was read into a Python program which utilized Python's natural language toolkit (NLTK) to extract the terms, stems, bigrams and trigrams in the titles.  Various statistical analyses were then performed


