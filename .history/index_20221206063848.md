# Analysis and detection of singing techniques <br> in repertoires of J-POP solo singers
## Yuya Yamamoto, Juhan Nam, Hiroko Terasawa
<!-- You can use the [editor on GitHub](https://github.com/yamathcy/ISMIR2022J-POP/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files. -->


<!-- ### Abstract of the paper
```
Singing techniques in vocal performances are important and have close relationships to singers’ singing styles. Each professional singer of popular music has a unique singing style, that is, the use of singing techniques. We focused on singing techniques within the scope of music information retrieval research.We investigated how singers use singing techniques using real-world recordings of famous solo singers in Japanese popular music songs (J-POP). First, we built a new dataset of singing techniques. The dataset consists of 168 commercial J-POP songs, and each song is annotated using various singing techniques with timestamps and vocal pitch contours.We also present descriptive statistics of singing techniques on the dataset to clarify what and how often singing techniques appear.We further explored the difficulty of the automatic detection of singing techniques using previously proposed machine learning techniques. In the identification, we also investigated the effectiveness of auxiliary information (i.e., pitch and distribution of label duration), not only providing the baseline. 
We provide the some metadata and annotation of the dataset https://yamathcy.github.io/ISMIR2022J-POP/.

``` -->
[Paper on ArXiv](https://arxiv.org/abs/2210.17367)

### Abstract of the paper

```In this paper, we focus on singing techniques within the scope of music information retrieval research.
We investigate how singers use singing techniques using real-world recordings of famous solo singers in Japanese popular music songs (J-POP). 
First, we built a new dataset of singing techniques. 
The dataset consists of 168 commercial J-POP songs, and each song is annotated using various singing techniques with timestamps and vocal pitch contours.
We also present descriptive statistics of singing techniques on the dataset to clarify what and how often singing techniques appear.
We further explored the difficulty of the automatic detection of singing techniques using previously proposed machine learning techniques. 
In the detection, we also investigate the effectiveness of auxiliary information (i.e., pitch and distribution of label duration), not only providing the baseline. 
The best result achieves 40.4% at macro-average F-measure on nine-way multi-class detection.
We provide the annotation of the dataset and its detail on the appendix website (this site). https://yamathcy.github.io/ISMIR2022J-POP/ 
```
   

### Dataset "COSIAN"
<div style="text-align: center;">
    <img src="COSIAN_LOGO.png" width="300px">
</div>


#### Description
We built a new dataset named **COSIAN** (a COllection of SInging voice ANnotation) to conduct the analysis.
COSIAN is an annotation collection of Japanese popular (J-POP) songs, focusing on singing style and expression of famous solo-singers.

It consists of various **168 songs**.
There are 21 female- and 21 male singers. Each singer has four songs that have different moods from each other.

### What is the motivation?
**Understanding the singing voice more**

The basic concept of the work is **analyzing the singers' characteristics by clarification of how they render the song**.
One of the naive ways to realize it is annotating the presence of **singing techniques**, which are produced by fluctuating the pitch, timbre, etc. 
However, there are no such datasets, so we decided to build it.

#### Metadata
It contains songlist. it contains following information;
<iframe width="1000" height="500" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRAkgcnUAJkbBLqnpvs2qk9uAdqkVyjygsI7wvrBC4zrpKhc_lVTIR0xTm5Yk6I-aFt1O5DQqxVITj1/pubhtml?gid=1530300283&amp;single=true&amp;widget=true&amp;headers=false"></iframe>

#### Annotations
<img src="example_homura.png" width="600px">

- **Singing techniques**: Overlapping strong labeled annotation (i.e. kinds and timestamps) of singing techniques. -> If you want the annotation files, access [here](https://drive.google.com/file/d/1o4TTd7Xeog5oVBiVuolckQM1vg0Z0Ldd/view?usp=share_link) and request a permission. 

- **Pitch (not publicly available)**: Since pitch is an essential component of singing technique analysis, we further annotated melodic pitch using [Tony](https://www.sonicvisualiser.org/tony/), followed by manual correction such as removing the unvoiced parts and reverberation tails.


**Because of copyright issue, we don't provide raw audio tracks.** Instead, we provide links of music streaming service for each songs in COSIAN.

- **Spotify links**: Because of copyright issue, we don't provide raw audio tracks. Instead, we provide Spotify links of each songs in COSIAN.

- **YouTube links**: We also provides YouTube links on the YouTube playlist. Note that the playlist only contains official mv without alignment information. 

- **Amazon music links** (work in progress): We will also provides Amazon music links for you to purchase CD recordings, which we actually used in the task.

**We are planning to make more types of annotation within the copyright law.**

**The administrator may update these conditions of use at any time.**

### Annotation procedure
We used [Sonic visualiser](https://www.sonicvisualiser.org/), to annotate the singing techniques with both of the help of sound playback and visualizing the spectrograms and pitchgrams.
<div style="text-align: center;">
    <img src="annotation_sonic.png" width="600px">
</div>


### Annotated singing techniques

Overview
<div style="text-align: center;">
    <img src="overview_stream.png" width="600px">
</div>
<div style="text-align: center;">
    <img src="singing_techniques_list.png" width="400px">
</div>

#### Examples of each singing technique
<div style="text-align: center;">
    <img src="example.png" width="600px">
</div>


### Data statistics 
- Annotated duration
<div style="text-align: center;">
    <img src="song_duration.png" width="600px">
</div>

- Song released year
<div style="text-align: center;">
    <img src="released_year.png" width="600px">
</div>

- Count and duration of singing techniques
<div style="text-align: center;">
    <img src="statistics_technique.png" width="600px">
</div>

- Distribution of duration of each singing technique
<div style="text-align: center;">
    <img src="dist_duration.png" width="600px">
</div>

- Singer-wise count of singing techniques
<div style="text-align: center;">
    <img src="singer_wise.png" width="600px">
</div>

### Detected examples
These are the examples automatically detected by Focal-GT model. 
**Note that videos are sample of audio clip, we actually used audio from the CD recordings for the task.**
<div style="text-align: center;">
    <img src="model.png" width="300px">
    <img src="stacking.png" width="300px">
</div>

#### Good examples

<table>
    <thead>
        <tr>
            <th colspan="2">#1: Sakura / Ikimono gakari</th>
        </tr>
    </thead>
    <tbody>
      <tr>
            <td>Video clip 1:30-1:36</td>
            <td>Label (Upper: ground truth label, lower: detected labels)</td>
        </tr>
        <tr>
            <td><iframe width="400" height="300" src="https://www.youtube.com/embed/61z-cqg28R8?start=90" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></td>
            <td><img src="good_example_2_sakura.png" width="800px"></td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th colspan="2">#2: Omoiga karanaru sono mae ni / Ken Hirai</th>
        </tr>
    </thead>
    <tbody>
      <tr>
            <td>Video clip 2:38-2:45</td>
            <td>Label (Upper: ground truth label, lower: detected labels)</td>
        </tr>
        <tr>
            <td><iframe width="400" height="300" src="https://www.youtube.com/embed/n2zqrJMuJvM?start=158" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</td>
            <td><div style="text-align: left;">
    <img src="good_example_1_omoiga.png" width="800px">
</div></td>
        </tr>
    </tbody>
</table>

#### Bad examples

We confirmed that one of the common mis-detection cases is from the detection of too short or frequently switching regions.


<table>
    <thead>
        <tr>
            <th colspan="2">#1: Readymade / Ado</th>
        </tr>
    </thead>
    <tbody>
      <tr>
            <td>Video clip 0:50-0:55</td>
            <td>Label (Upper: ground truth label, lower: detected labels)</td>
        </tr>
        <tr>
            <td><iframe width="400" height="300" src="https://www.youtube.com/embed/jg09lNupc1s?start=50" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></td>
            <td><img src="bad_example_1_readymade.png" width="800px"></td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th colspan="2">#2: Honey / L'Arc～en～Ciel</th>
        </tr>
    </thead>
    <tbody>
      <tr>
            <td>Video clip 0:14-0:20</td>
            <td>Label (Upper: ground truth label, lower: detected labels)</td>
        </tr>
        <tr>
            <td>
            <iframe width="400" height="300" src="https://www.youtube.com/embed/WmM-KTcG3QY?start=14" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></td>
            <td><img src="bad_example_2_honey.png" width="800px"></td>
        </tr>
    </tbody>
</table>

### Contact
If you have any questions about the paper, please contact the first author Yuya. We also accept issues in [github repository](https://github.com/yamathcy/ISMIR2022J-POP/issues).

### Citation 
Cite the ISMIR 2022 paper.
```
@inproceedings{yamamoto2022analysis,
         author = {Yamamoto, Yuya and Nam, Juhan and Terasawa, Hiroko},
         title = {Analysis and Detection of Singing Techniques in Repertoires of J-POP solo singers},
         booktitle = {Proceedings of the 23rd International Society for Music Information Retrieval Conference (ISMIR)},
         year = {2022}
}
```
