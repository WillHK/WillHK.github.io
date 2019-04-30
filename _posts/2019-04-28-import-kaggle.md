---
layout: post
title: Importing Kaggle Datasets Into Google Colab
subtitle: Easily Import Datasets
gh-repo: WillHK/kaggleapitutorial
gh-badge: [star, fork, follow]
tags: [tutorial]
comments: true
---

If you're just getting started in your data science career then you'll soon find out acquiring data to analyze is actually pretty difficult. Most companies don't want to hand out their giant datasets as they're worth a lot of money, so they limit you to a RESTful API at best or you're forced to programmatically scrape their site. This is where Kaggle comes to the rescue, they have huge datasets available that you can analyze, use for machine learning models or just look at because they're so pretty.
You might have also found that Google's Colab application is a very easy way to jump into using Jupyter notebooks without the hassle of setting up your own environment. Unfortunately it seems that if you want to use Kaggle datasets in Colab you'll need to download csv files from Kaggle and then upload them to Colab manually. What a hassle!
Luckily this isn't the case, with just a few simple steps we can set up an environment where you can download any dataset your heart desires from Kaggle. To start you'll need an account on kaggle.com and be logged in. On the top right corner of the site is an icon (Or your pretty face if you've uploaded your picture) representing your account, click on it and click My Account. About 2/3rds of the way down the page is an API section, just click on the "Create New API Token" button and it will download a file named kaggle.json.
Now that you have your API token downloaded to your computer you can open up a Google Colab notebook and type in the code below. You should get an output similar to the one below.
If you run the code block a file selection widget will appear in the output. Once you click on the "Choose Files" button a file selection window will appear and you can find where kaggle.json was saved and select it. Colab will download it to your VM's root directory and then you'll need to input the code below in a new code block.
This creates the directory which the Kaggle API expects our API key to be, moves the api key file to the directory and then restricts access to only your user account. The last command is not just good practice but it also stops the Kaggle API from yelling at us later. We can now start using the Kaggle CLI to search and download from all their datasets. I'll give an examples below.
`!kaggle datasets list -s football`
This command will list all the datasets Kaggle has related to football, you can obviously replace football with anything you'd like to search for. For this example I'm going to choose to download the NFL Football Player Stats dataset made by Zynicide
```!kaggle datasets download zynicide/nfl-football-player-stats
!unzip fivethirtyeight-nfl-wide-receivers-dataset.zip```
You'll now have 2 new JSON files you can import into a Pandas dataframe and analyze to your hearts content so you'll never lose at Fantasy Football again. (Ok, maybe not. You'll probably have a lot of fun and learn new things though.)
If you'd like to look at a notebook containing this code feel free to go here: https://colab.research.google.com/drive/1i-vu5Y6iA6_6-aQHqN5gJlpPg8SFgTOf (API key shown in the notebook is already expired, nice try though)
Thanks for reading and I hope this tutorial helped you. You can find me on Twitter @WillH and my Github username is WillHK, feel free to reach out with questions.