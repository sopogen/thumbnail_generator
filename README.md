# :video_camera: Youtube Thumbnail Generator
> Automatic thumbnail generating program for Youtube  
for ybigta 2020-2 Conference  
<div>
<img width="400" src="https://user-images.githubusercontent.com/61009073/103433785-c01ef300-4c3a-11eb-959b-481dcc6b1248.png">
</div>

# Why?
- Individual streamers want to upload their streaming video to Youtube
- However, it is difficult to make Youtube thumbnail for the streamers who don't have their own broadcast editor
- THEN, how about a program which can make high-quality thumbnail AUTOMATICALLY?

# How?
<div>
<img width="750" src="https://user-images.githubusercontent.com/61009073/103165819-aa3ab800-485f-11eb-845e-0ac5abf798d2.png">
</div>

# Results?

# Specific Processes?
- [Getting comments and preprocessing](https://github.com/sopogen/thumbnail_generator#Getting-comments-and-preprocessing)
- [Highlight extraction](https://github.com/sopogen/thumbnail_generator#Highlight-extraction)
- [Selecting thumbnail image](https://github.com/sopogen/thumbnail_generator#Selecting-thumbnail-image)
- [Selecting thumbnail typography](https://github.com/sopogen/thumbnail_generator#Selecting-thumbnail-typography)
- [Making thumbnail](https://github.com/sopogen/thumbnail_generator#Making-thumbnail)

# Getting comments and preprocessing
- Getting comments
  - Used Twitch API to get comments of twitch videos
  - Got time, nickname, and chatting contents from comments
- Preprocssing
  - Committed feature engineering for highlight detection  
  <div>
  <img width="750" src="https://user-images.githubusercontent.com/61009073/103359055-79c27a80-4afa-11eb-85f7-0d092acc89d4.png">
  </div>
  
# Highlight extraction
- Highlight detection
  - Utilitized anomaly detection to get highlight area from video
  - Isolation Forest was the best model for the task
  - Removed anomalies which are not hightlights. Ex) start of the video
- Extracting highlights
  - Used twitch licker software to get specific period of video

# Selecting thumbnail image
> Select thumbnail image as the scene which streamer showing extreme emotions
- Face detection
  - Used Haar Cascade Classifier to detect streamers' face in a video
  <div>
  <img width="400" src="https://user-images.githubusercontent.com/61009073/103433871-59023e00-4c3c-11eb-9f17-2ad1e320012a.png">
  </div>  
- Emotion classifcation
  - Committed CNN-based emotion classification
  - Seleceted the moment streamers' emotion percentages are extremely high
  <div> 
  <img width="400" src="https://user-images.githubusercontent.com/61009073/103434448-bf8b5a00-4c44-11eb-8956-87c682c7aca7.png">
  </div>

# Selecting thumbnail typography
- Keyword extraction
  - Extracted keyword frequently commented from comments
  - Used Soynlp package to apply gramatical whitespaces to the comments
  <div>
  <img width="400" src="https://user-images.githubusercontent.com/61009073/103434495-5d7f2480-4c45-11eb-87ba-f00cff6ac576.png">
  </div>

# Making thumbnail
- Object seperation
  - Used sematic segmentation to seperate people and background
  - Combined new background based on extracted keyword
  <div>
  <img width="750" src="https://user-images.githubusercontent.com/61009073/103434594-0ed28a00-4c47-11eb-9350-2f1453e287bb.png">
  </div>
- Combine typography with thumbnail
  <div>
  <img width="750" src="https://user-images.githubusercontent.com/61009073/103434612-4f320800-4c47-11eb-88c6-19eba0cf1b69.png">
  </div>

# References
- [Adaptive Video Highlight Detection by Learning from User History](https://arxiv.org/abs/2007.09598)  
- [Highlight Detection using Linguistic Features of Real-time Korean Game Audience Chat](https://scienceon.kisti.re.kr/srch/selectPORSrchArticle.do?cn=NART96173440&dbt=NART)  
- [An Automatic Extraction System of Streaming Broadcasting Highlight Section Using User Chat Data](https://www.dbpia.co.kr/Journal/articleDetail?nodeId=NODE09874604)  
