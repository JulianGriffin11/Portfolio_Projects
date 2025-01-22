# 🎧 **Spotify Symphony: Dashboard Analysis of Song Attributes** 🎧

<img src="../../Media/SS_E_Dashboard.gif" alt="Spotify Dashboard Visual" width="85%" />

## Introduction  

**Spotify Symphony** embarks on an exciting journey to **decode** the relationship between song attributes and their **popularity**. Leveraging the power of an interactive **Excel Dashboard**, this part of the project **dazzles** with visually compelling insights into key covariates like **Danceability**, **Energy**, and **Tempo**. Watch the story unfold through **interactive visualizations**, **pivot tables**, and more! 🎶📊


---

## Questions to Analyze  

1. **What is the relationship between each song attribute and Popularity?**
2. **How well does the linear model predict song Popularity?**
3. **Does higher Danceability always lead to higher Popularity?**

---

## Excel Skills Used  

- **📊 Dashboard Creation**
- **📌 Pivot Tables**  
- **🔄 Conditional Formatting**  
- **🔍 Data Filtering**  
- **💡 Data Visualization**  

---

## Data Overview  

The dataset includes information on Spotify song attributes and popularity, such as:

- **🎶 Danceability**: A measure of how suitable a song is for dancing.  
- **⚡ Energy**: The intensity and activity level of the track.  
- **🎵 Tempo**: The beats per minute (BPM) of the song.  
- **📊 Popularity**: A popularity score based on various factors.  
- **🔊 Acousticness & Instrumentalness**: Measures of the song’s acoustic nature and instrumental quality.  

<br>

<img src="../Media/SS_Excel_Dashboard.png" alt="Song Data Overview" width="55%" />

---

## Analysis Highlights  

### 1️⃣ **What is the relationship between each song attribute and Popularity?**  

#### 📊 Methodology  
- Visualized relationships using the **Excel Dashboard**, focusing on each covariate's correlation with Popularity.  
- Applied conditional formatting and slicers for more intuitive visual interpretation.  

#### 💡 Insights  
- Danceability and Energy showed a moderate positive correlation with Popularity.  
- Songs with higher Acousticness and lower Energy appeared less popular on average.

<br> 

<img src="../Media/SS_Excel_Visual.png" alt="Song Attributes vs Popularity" width="70%" />  

---

### 2️⃣ **How well does the linear model predict song Popularity?**  

#### 📈 Methodology  
- Interpreted the results from the linear model in **R** to understand how the model predicts song Popularity.  
- Linked key R findings with Excel visuals for a seamless analysis experience.

#### 💡 Insights  
- The linear model accounted for about 75% of the variance in Popularity.  
- Energy and Danceability were the most significant predictors of Popularity in the model.

<img src="../Media/SS_Excel_Model_Results.png" alt="Linear Model Results" width="75%" />  

---

### 3️⃣ **Does higher Danceability always lead to higher Popularity?**  

#### 🔍 Methodology  
- Used **Pivot Tables** to explore how different ranges of Danceability correlate with Popularity.  
- Visualized trends using dynamic charts based on Danceability scores and Popularity levels.

#### 💡 Insights  
- Songs with Danceability between 0.6 and 0.8 had the highest median popularity scores.  
- Danceability wasn’t always a reliable predictor; other factors like Tempo and Energy played a role.

<img src="../Media/SS_Excel_Danceability.png" alt="Danceability Analysis" width="60%" />

---

## Conclusion  

The **Spotify Symphony** Excel dashboard offers insightful visualizations that help uncover the key relationships between song attributes and Popularity. By combining **Pivot Tables**, **Conditional Formatting**, and dynamic **Dashboards**, we gain a clear understanding of the factors that drive Spotify song success. This analysis opens doors for more refined prediction models and actionable recommendations for producers and artists.

---

### 📂 Access the Project  

Click [here](./Chapter%202%20-%20Excel%20Dashboard) to explore the **Spotify Symphony: Excel Dashboard** in more detail.

---

- Check out some of my other work:  
  - [📊 SQL Projects](https://github.com/JulianGriffin11/SQL_Projects)  
  - [📘 R Projects](https://github.com/JulianGriffin11/R_Projects)

Kind Regards,  
**Julian Griffin**
