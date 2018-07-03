# HICSS-Evolution

Interactive visualizations celebrating 50 years of scientific work at HICSS.  Code underlying visual displays of "HICSS Evolution" selection at  http://hicss.hawaii.edu/

*****  DRAFT IN PROCESS

In celebration of the 50th anniversary of the Hawaiian International Conference on System Sciences I undertook an analysis of all the conference proceedings from 1968-2017. The focus was on tracking the changes in content from the early beginnings of IT to the present day.  In part, this turned out to be a massive project because of the substantial changes that occurred from 1968 to 2017 in the structure of the organization, conference and proceedings, as well as the changes in the media used to record the proceedings/abstracts/papers across the years -- from paper handouts, to bound paper volumes, to PDFs, to floppy disks, to CDs, to thumb drives and to online repositories.  The result is that much of the data collection for the years prior to 2000 had to be done manually (typing in various TOCs) or creating various programs to "scrape and clean" the myriad of data formats used from one year to the next. In the end, I decided to focus on analyzing the text from the titles found in the table of contents (TOCs) for each of the 50 track proceedings. In addition to the text, the TOCs also provided information about the changing structure of the conference as well as detailed information about the paper authors (and their affiliations).

<h3>Wrangling the Data</h3>

The overall analysis was divided into two parts -- analysis of the changing structure and participation and text analysis of the changing content. As noted, it took a tremendous amount of data wrangling over a number of months to produce a data set that could be used to perform these analyses. The wrangling actually involved two steps.  

First, because the actual structure of the TOCs often varied substantially from one decade to another, a series of customized Python programs had to be written to capture the data from the various decades.  This resulted in 45 text files that housed in the zipfile labeled <em>HICSS Conference Proceedings TOCs -1968-2017.zip</em>. Unfortunately, while there were obviously 50 HICSS conferences between 1968 and 2017 (and hence the "50th Anniversary"), I could only locate the TOCs for 45 of them (leaving out the proceedings for the years 1975, 1976, 1979, 1989, and 1991).  

A segment from one of the files (1977) is shown below.  It's typical of the contents found in all the individual files. Not only does it illustrate the structure of the TOC content for each file, but it also provides a general idea of the structure of the conference. Basically, each conference consists of a series of tracks (with one or more chairs) each containing a series of minitracks (also with one or more chairs) in turn consisting of at least 3 papers with one or more authors. There is a caveat to this ongoing structure. Before 1977, there were no tracks or minitracks, only sessions with one or more chairs.  For analysis purposes, with these earlier conferences I treated the conference as if it had one track titled "All Sessions" and used the title of the session for the title of the minitrack.

HICSS10 1977<br>
####<br>
Track: MANAGEMENT INFORMATION SYSTEMS<br>
Track Chair: R. Sprague, University of Hawaii<br>
Minitrack: Database Processing Software<br>
Minitrack Chair: G. Kopp, Honofed Corporation<br>
Paper: A File Structure for Muiple Key Retrieval<br>
Author: H. Hsu, Colorado State University<br>
Paper: Information Specification Processing by Use of Iterative Inference from Meta<br>
Author: T. Cousins, University of Southwestern Louisiana<br>
Author: W. Dominick, University of Southwestern Louisiana<br>
...<br>
Minitrack: Computer-Based Corporal Modeling<br>
Minitrack Chair: R. Sprague, University of Hawaii<br>
Paper: Automated Evaluation of the Plan of Internal Control<br>
Author: R. Miyahara, Fujitsu Ltd.<br>
...<br>

The second step in the wrangling process involved combining the individual files into a single data set. Although it should have been straightforward, there were an endless number of issues often resulting from the fact that same names (tracks, minitracks and authors) often varied from one year to the next. For example, sometimes an author was designated by his or her first and last name, other times by the first initial and last name. Similarly, tracks and minitracks names varied from one year to the next even though they had the same chairs and basic content. Finally, from one year to the next it was a "crap shoot" whether locations and affiliations were included in the proceedings. For this reason, they were excluded from the final data set.

Most of this second step was carried out by a series of Python programs that eventually resulted in both a collection of Python dictionaries that could be further analyzed with other Python programs and a tab delimited text file that could be easily read and analyzed by Excel. Neither the Python Programs nor the dictionaries are included in this repository.  However, the Excel sheet with the cleansed data is -- see <EM>HICSS_1968-2017_Trk_MT_Pap_Aut.xlsx<EM>. Within this spreadsheet, each row contains the data associated with one of the authors of a specific paper.  More specifically, each row has the track name, minitrack name, paper title, and an author's name (denoted by first initial and last name). It also includes the unique IDs associated with the names and titles -- these are used to locate items in the Python dictionaries.  What is excluded are the names of the associated track and minitrack chairs. Obviously, there is quite a bit of redundancy from one row to the next because papers usually have multiple co-authors. While this could have easily been stored in a relational or noSQL database, much of the final analysis was done with Excel pivot tables.

Note: Anyone is welcome to download either of the date sets. However, please cite the source referencing my name (Dave King) and this github repository. 

<h3>Analyzing Structure and Participation</h3>

Like the wrangling, the analysis of the final data set proceeded in two steps.  First, the Excel spreadsheet was used as the basis of a visual analysis the changing structure and participation over the years over the years.  

<OL>
  <LI> Python was used to read each of the individual files and to merge the data into a python dictionary containing an entry for each of the papers
  <LI> xxx
</OL>
Python was used to create a series of dictionaries c

Much of the analysis

History of Tracks (1968-2017) : Year Start and End
Summary of Key Counts by Year (1968-2017)
Summary of Key Ratios (1977-2017)
Number and % of Minitracks by Track and Year (1977-2017)
Number and % of Papers by Track and Year (1977-2017)
Number and % of Authors by Track and Year (1977-2017)
Area Charts - Number per Year by Track (1977-2017)
Mean Number of Authors per Paper by Year and Track (1968-2017)
Authorship: Papers by Number of Authors and Authors by Number of Papers (1968-2017)

Various data formats were employed with this project

<ul> 
<li> Data for the analysis of the general demographics of the conference - tracks, minitracks, authors and associated titles. These data are found in their original coded form in the zipfile <em>HICSS Conference Proceedings TOCs -1968-2017.zip</em> and in row format in the worksheet "Details-Trk-MT-PAP-Authors" in the Excel file <em>Trk-MiniT-Pap-Authors.xlsx</em>. For those who are interested in the demographics its probably best to use the worksheet rather than the original coded form.
<li> Data for the analysis of the textual analysis of the titles in the conference proceedings. Again, the underlying data for this analysis comes from the 
<li> Programs for setting up the data and for carrying out the demographic and the textual analysis
</ul>

A small number of potential visual analyses of the data can be found at:

<ul>
<li> The HICSS conference site --  http://hicss.hawaii.edu/ which covers 1977-2017 (selecting HICSS Evolution) -- which leads to Kaveh Abhari's tableau site: 

https://public.tableau.com/profile/kaveh.abhari#!/vizhome/HICSS50_0/AreaChartsofCounts.  

This covers track and author information for the years 1977-2017</li>

<li> My public tableau site which provides all of the above, as well as the textual analysis for the years from 1968-2017:

https://public.tableau.com/profile/david.king7957#!/vizhome/HICSS50/HistoryofTracks
https://public.tableau.com/profile/david.king7957#!/vizhome/HICSSTitleTxtAnalysis/BigramAnalysis</li>

</ul>
