---
layout: single
title: "The Value of Innovation: Using Worldwide Patent Data to Compare Patents Based on Value"
tags: Project Regression NLP
#toc: true
#toc_label: Contents
classes: wide
excerpt: "For this project, I attempted to tie patent value to easily-attainable patent data, with the goal of motivating companies to think more long-term" 
header:
    overlay_image: assets/images/beakers.jpeg
    overlay_filter: 0.5
---
### My Motivation for the Project ###  
<br/>
I spent about a year after graduating with my Chemical Engineering degree working with my father on developing a patent on a new drying process. More recently, my parents have spent the last couple of years trying to launch a company based on a new technology they developed. I have experienced firsthand the difficulties in securing a patent and communicating its value, and secondhand the difficulties in securing funding for a new, unproven technology.  
<br/>
Companies, and in turn, investors, have become more and more short-term oriented as time has gone on. This has resulted in decreased R&D spending, and thus decreased innovation as companies place less value on long-term investments. This is due in part to the fact that it is difficult to quantify innovation, and thus put a value on it. In an increasingly numbers-focused world, where every decision needs to have quantifiable metrics to back it up, putting a dollar value on patents, and thus research, would go a long way in correlating Research to real-world value. 
 
{% include figure image_path="https://raw.githubusercontent.com/giraldon/patent-regression/master/pics/innovationdiscountpatent.png" alt="innovation discounting" caption="Market Discounting vs. R&D Productivity, 1980 - 2010." %}

This is a graph from [this paper](https://github.com/giraldon/patent-regression/blob/master/Patents%20Data/SSRN-id2837524.pdf), I think it drives home the point of this exercise, which is to apply a value to innovation in order to encourage long-term thinking, and allow companies to justify R&D spending.  

### Project Info ###   

[This](https://github.com/giraldon/patent-regression/blob/master/Patents_Topics_Regression_Desktop.ipynb) is a notebook which runs through the project step-by-step as a whole.  
  
Data was obtained from [Google's Patent Data](https://console.cloud.google.com/marketplace/details/google_patents_public_datasets/google-patents-research-data?filter=solution-type:dataset&q=google%20patents%20public%20datasets&id=4154f240-a4fb-461b-ac9d-2003ea3d107e) hosted on BigQuery. 
  
*Initially*, my goal was to create a model which would predict the value of a given patent, by building a regression model around ground-truth values which were obtained from [this paper](https://github.com/giraldon/patent-regression/blob/master/SSRN-id2193068.pdf).  
However, I eventually found that I could not correlate the patent metadata strongly enough with the ground-truth values to justify predicting the exact value of any given patent.  
  
Despite this, the project was still very useful for visualizing which companies have put out the most valuable patents, and comparing across companies based on relative innovation value. By correlating this with R&D spending, companies could use this data to ballpark return on investment.  Furthermore, I was able to determine the most valuable patent topics, to a certain degree, which allowed for an easy visual comparison on a technology basis.  

This project would be valuable to companies looking for their next move, or at least looking to put a ballpark value on a given technology or investment. While this does not solve the problem I posed in the beginning, it certainly helps. 
  
The presentation containing all of the visuals I created in tableau, as well as a general narrative is available [here](https://github.com/giraldon/patent-regression/blob/master/Patent_design%20(2).pdf)  
  
The video of my presentation is located [here](https://livestream.com/metis/events/8360820/videos/180566594). This is from the livestream of presentations given on our final projects at Metis.   
**My presentation starts at ~17:45**
  
Any questions feel free to contact me at [nicolas.giraldowingler@gmail.com](mailto:nicolas.giraldowingler.com)  

## Some interesting Results ##  
<br>
{% include figure image_path="/assets/images/companybubblefull.png" alt="Company Patent Values" caption="Company Patent Values  - [Full Viz](https://public.tableau.com/views/companypatentvalues/Sheet1?:embed=y&:display_count=yes&:origin=viz_share_link)" %}

This bubble chart shows the most valuable companies relative to each other by the value of their patent portfolios. This and all following charts were created in Tableau:   
<br/>

{% include figure image_path="/assets/images/totalbubblefull.png" alt="Overall Patent Values" caption="Overall Patent Values -  [Full Viz](https://public.tableau.com/views/MostValuableTopics/Sheet3?:embed=y&:display_count=yes&:origin=viz_share_link)" %}

These are the most valuable patent topics, or technologies, overall.  
The reason chemical patents came out on top instead of tech patents despite the recent explosion in number and value of these patents, is that the tech field is more fragmented in terms of topics.   
More topics means smaller blobs, but as an aggregate they are the most valuable.  

Still interesting to note is that before tech, most of the money was in chemical manufacturing, especially in coatings and adhesives.  
<br/>
{% include figure image_path="/assets/images/techbubblefull.png" alt="Tech Patent Values" caption="Tech Patent Values" %}

After removing the top chemical topics, the tech field comes out. As expected, the most valuable topics pertain to Chip manufacturing, Sensors, and Wireless Communications. 
<br/>
