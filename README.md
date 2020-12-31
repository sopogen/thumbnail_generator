# Youtube Thumbnail Generator
> Automatic thumbnail generating program for Youtube  
for ybigta 2020-2 Conference  

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
  <img width="750" src=https://user-images.githubusercontent.com/61009073/103359055-79c27a80-4afa-11eb-85f7-0d092acc89d4.png>
  </div>
  
# Highlight extraction
- Highlight detection
  - Utilitized anomaly detection to get highlight area from video
  - Isolation Forest was the best model for the task
  - Removed anomalies which are not hightlights. Ex) start of the video
- Extracting highlights
  - Used twitch licker software to get specific period of video

# Selecting thumbnail image
- Face detection
  - 
- Emotion detection


# Selecting thumbnail typography
- Keyword extraction


# Making thumbnail
- Object seperation

# References
