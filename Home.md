---
cssclass: dashboard
banner: "![[home_wallpaper.png]]"
banner_y: 0.5
banner_lock: true
---

# Notes
- Useful Things
	- [DistributedFileSystem](./MyNotes/UsefulGeneralNotes/DistributedFileSystem.md)
	- [Git](./MyNotes/UsefulGeneralNotes/Git.md)
	- [Markdown](./MyNotes/UsefulGeneralNotes/Markdown.md)
- Google Cloud
	- [How Prepare GCP Data Engineer Exam](./MyNotes/GoogleCloud/How%20Prepare%20GCP%20Data%20Engineer%20Exam.md)
	- [Machine Learning Notes](./MyNotes/GoogleCloud/MachineLearning.md)
	- [GCP PDE - Quick Notes](./MyNotes/GoogleCloud/GCP%20PDE%20-%20Quick%20Notes.md)
- Databricks
	- [Overview](./MyNotes/Databricks/Overview.md)
	- [Notes](./MyNotes/Databricks/Notes.md)
- Apache
	- [HDFS](./MyNotes/Apache/HDFS.md)
	- [Hive](./MyNotes/Apache/Hive.md)
- SonarQube
	- [How Use SonarQube Locally](./MyNotes/SonarQube/How%20Use%20SonarQube%20Locally.md)
	- Slide SonarQube ![slides sonarqube in pptx](./MyNotes/SonarQube/SonarQube.pptx)

# Vault Info
- 🗄️ Recent file updates
 `$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(10).file.link)`
- 🔖 Tagged:  favorite 
 `$=dv.list(dv.pages('#favorite').sort(f=>f.file.name,"desc").limit(4).file.link)`
- 〽️ Stats
	- File Count: `$=dv.pages().length`
	- Note Count: `$=dv.pages('"MyNotes"').length`