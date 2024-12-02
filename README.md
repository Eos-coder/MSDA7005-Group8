# MSDA7005-Group8
Our source code contains three files which are 1.Final script crawler; 2.LDA Analysis; 3.Emotional analytic.You can refer to the following guide to run the code in jupyternotebook.

## 1.Final script crawler
### a) Environment
Before running final-script-crawler, you need to install these python libraries: DrissionPage, BeautifulSoup, tqdm, pandas. If it is not installed, you can install it with the command pip install.

### b) Process
Crawl the code by sign in to the account - automatically type keywords to search - crawl the link of the post in the search interface - extract the URLs from the note_link column for crawling the detailed content.

### c) Operation
Run them one by one in cell order.
After running the sign in function, a simulated browser window will pop up, and you need to scan the QR code to log in to your Xiaohongshu account.
There is a list of predefined keywords in the code, including words such as "marriage". If you want to change the topic keywords crawled, you can modify the list according to your needs.
After a full run, the extracted file is automatically saved to a file named xhs_content.xlsx, and the pathname can be modified as needed if needed.

### d) Output Files
After running the script, the following output file will be generated:
- xhs_content.csv: Scraped posts information.

### e)Warning
This code may take some time to run, depending on how many keywords you want to search for and how many times each keyword is scrolled down.

## 2.LDA Analysis
### a) Environment
Before running the LDA( Latent Dirichlet Allocation ) analysis script, make sure to install the following Python libraries: pandas, jieba, wordcloud, gensim, pyldavis, and matplotlib. If any of these libraries are not installed, use the command pip install to install them.

### b) Process
Text cleaning by removing HTML tags, emojis and special characters, marks - tokenize the text with unwanted words filtered out based on stopwords.txt - generate a word cloud - apply LDA topic modeling - save the results in CSV files - visualize the LDA topics using pyLDAvis.

### c) Operation
To run the script, ensure that the input file xhs_content.csv includes the columns author_name, content, and time. Place this file in the same directory as the script or update the file_path variable. Running the script will automatically clean the text, tokenize and tag it, generate a word cloud, apply LDA, and save the output files (xhs_content_cleaned.csv, xhs_content_segmented.csv, wordcloud.png, etc.). The results of topic modeling are saved in CSV files, and an interactive LDA visualization is generated and saved as lda_visualization.html. Users can customize stopwords and reserved words by updating the corresponding text files, and all outputs are ready for further analysis.

### d) Output Files
After running the script, the following output files will be generated:
- xhs_content_cleaned.csv: Cleaned content.
- xhs_content_segmented.csv: Tokenized and part-of-speech tagged data.
- wordcloud.png: Generated word cloud image.
- coherence_vs_themes.png: Generated coherence v.s. themes image.
- word_topics.csv: CSV file containing words and their most probable topic assignments.
- Topic_Freq_1.csv: Topic frequency data in CSV format.
- Topic_Freq_Total_Term_2.csv: Word frequency data for each topic.
- Topic_Freq_Term_3.csv: CSV file displaying the relationship between topics and words.
- lda_visualization.html: Interactive LDA topic model visualization.


## 3.Emotional analytic
### a) Environment
Before running this script, you need to ensure the following Python libraries are installed: pandas, jieba, matplotlib, and seaborn. These libraries are required for data manipulation, Chinese text segmentation, and visualizations. If these libraries are not installed, you can use the command pip install pandas jieba matplotlib seaborn to install them. 

### b) Process
Read text from a CSV file - calculate sentiment scores based on emotion dictionary - adjust scores for negation and degree words - classify each entry as positive, negative, or neutral - visualize emotional tendencies

### c) Operation
To use this script, run each section of code sequentially. Start by ensuring your input CSV file (xhs_content_segmented.csv) contains a column named Tokenization Result with pre-segmented text data. The script will calculate the emotional scores and categorize them into positive, negative, or neutral. These results will be added to the CSV file. Finally, the script will generate a histogram to visualize the distribution of sentiment scores and a pie chart to display the proportions of each emotional tendency (positive, negative, neutral). The results are saved in the same CSV file after processing.
