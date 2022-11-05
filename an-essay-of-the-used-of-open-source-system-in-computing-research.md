---
description: >-
  By Indra Dewaji, part of assignment of Research Methodology, University of
  York, January 2022
---

# An Essay of the Used of Open Source System  in Computing Research

Recently, the use of Open Source software has had significant importance in computing research. With the consideration of cost and community to support the system, the use of open-source systems become popular \[3]. This essay will discuss two research where both are using open-source software as the tools to analyze the research data. The published journal from E. Balkanli, et.al (2014), titled “Supervised Learning to Detect DDoS Attack”, is discussing the Distributed Denial of Service (DDoS) attacks via backscatter traffic and how to detect the attack by employing the Bro and Corsaro open-source system. The dataset used to train the machine where the classifiers generated through Cart Decision Tree and Naive Bayes machine learning classifier \[1].

The second research from Ather. A, et.al (2020), titled “Digital Forensic Analysis of Fitbit Wearable Technology: An Investigator’s Guide”, is discussing the digital forensic analysis of Fitbit wearable technology \[2]. The research discusses the forensic analysis to be used in the criminal case employing two different open source tools, Autopsy Sleuth Kit and Bulk Extractor View. The objective of the research is to analyze the physical activity of the user linked with the crime scene \[2].&#x20;

&#x20;

## Overview and Introduction

The first research pointing to the issue of effectiveness analyzing the accuracy of Network Intrusion Detection System (NIDS) which is popular and commonly used to detect the backscatter traffic, are Bro and Corsaro open-source systems. And this paper also sees how the improvement can be made by applying CART Decision Tree and Naïve Bayes on the supervised machine learning, by giving the training dataset which does not include source/destination of IP and port numbers \[1].

The research compares with the existing other research where mostly the studies analyze the unusual network traffic from the destination/source IP address to identify the attacks. Based on this comparison, the research is focusing on detecting backscatter traffic from unidentified sources/destinations or ports to fill the gap by employing the supervised learning method \[1].

Bro's open-source system was in 2018 changed its name become Zeek, has the capability to log all the network activities, is fully customizable, and has extensive capabilities to detect traffic \[4]. While Corsaro open systems can classify backscatter category mainly from TCP and ICMP packets \[1].

The software collects all data identified as backscatter traffic, and those datasets are classified by the classifier CART Decision Tree and Naïve Bayes machine learning \[1]. The approach used in the research is supervised machine learning. The data is labeled and used to create a model to train the machine based on the known expected result.

The second research points the issue of data classification that can be used for forensic investigation and data validity, like the possibility of data that can be modified \[2]. This information is required for the investigator to get the accurate conclusion of the investigation. For the cost reason, the research is using the open-source system using Autopsy Sleuth Kit and Bulk Extractor \[2].

The fast change of technology and innovation of the tracker tools/application made the forensic investigator always need to learn and update the knowledge of analyzing the device. This problem statement becomes the background of why this research is being conducted \[2].&#x20;

Both kinds of research are using the same methods in their methodology. The methods they used are data collection, examination, analysis, and reporting. But during the examination, the first research adds additional steps to employ machine learning to predict and track the type of backscatter traffic. The first research has an adequate method compared to the second research. The first research shows the quantitative result of the research. It measures the performance of Bro and Corsaro software. The comparison result between software to detect the backscatter traffic for the DDoS attack, also shows how effective the method is being implemented.

However, the second research shows more in the qualitative aspect. The research may be improved by giving the comparison of the processing performance between software to generate the result since the objective of the research is to reduce the time for the investigator to investigate the data on the Fitbit tracker. It also can be improved by adding sufficient data based on the past criminal case to see what kind of data was used from the Fitbit tracker. This study also will help the investigator to classify the data where the investigator can prioritize which data should be analyzed.

## Case Study: Digital Forensic Analysis

The research of “Digital Forensic Analysis of Fitbit Wearable Technology: An Investigators’ Guide” \[2] is the focus of this section. The change of lifestyle has impacted the use of technology. Wearable devices, such as Samsung, Xiaomi, Huwaei, or Fitbit become part of the lifestyle. The Fitbit wearable device is used to track daily activity includes heart rate, total steps count, calory burned, location, and sleep activity.  Digital data can lead to evidence in the crime scene.

A case of the use of Fitbit as the key evidence on the crime scene is on Connie Dabate's murder, on December 23, 2015. Based on Richard Dabate's claim, between 08.45 – 09.00 am he went upstairs to check the intruder came to his house. During that time, the intruder fatally shot Connie Dabate then tied him up. At 10.11 am he was able to turn the panic button to call 911. The police tracked the Fitbit data of Connie Dabate. The Fitbit collected movement data at 9.23 am and at 10.05 am all movement stopped. Data from Facebook also showed at 9.43 am, Connie Dabate still uploading 3 videos. From this information, the police realized that the statement from Richard Dabate does not match with the digital data. And after finding some motives for the murder and linking with the key evidence from Fitbit, Richard Dabate was then charged with murder \[7].

Fitbit is already used to proof on the manipulation of personal injury cases. Or it can be the proof to back up the statement of a case. The activities that are tracked using Fitbit, can show the level of activities if it is under the baseline of the normal activity for the same person of the same age and profession \[8].

To conduct a digital forensic investigation, required a few steps to conclude \[9].

1\.      Data collection. In this step, data is categorized to support the purpose of digital forensic investigation including a classification for interrelated discipline and legal.

2\.      Examination of the data. In this stage, the data is examined and filtered where the unrelated data might be excluded.

3\.      Data analysis. Once the data has been extracted, the relevant information is classified and analyzed. The analysis should include all relevant entities, such as people, location, time, and actions, and relate all of this to a conclusion.

4\.      Reporting. The final stage of digital forensic investigation is reporting based on the analysis result and conclusion of the analysis.

This research \[2] only focuses on the data source from two types of Fitbit devices, Alta Tracker and Ionic. The research aims to reduce the time for the investigator to analyze these two devices to get an accurate conclusion on the investigation. The scope of the research only points to the aspect of what data can be extracted from the device, how to identify which data can be extracted, and the credibility of the data if the records can be modified. The research differs from other existing research where it includes the use of open source as the method of investigation \[2].

The research \[2] methodology is divided into five steps, they are, the selection of the tool, environmental setup, data population, data collection, and analysis. The researcher selects the forensic software Autopsy – The Sleuth Kit and Bulk Extractor View. The Sleuth Kit is the library used to investigate the data \[10] while Autopsy is the platform for digital forensic and a graphical user interface \[11]. Bulk Extractor Viewer is a C++ program used to extract the disk image using its graphical user interface, without parsing the data, and can be analyzed on instance \[14]. The use of an open-source system can reduce the cost for the investigator compared to commercial software.

To process the Fitbit data, the researcher is using VMWare Workstation Pro 14 and Windows 10 Operating System. Referring to the official website of Fitbit (www.fitbit.com), the use of Windows Operating systems, is because of Fitbit application, only can run on Windows and Mac OS when connecting to the computer. Autopsy received RAW file format to analyze the data, so its required another application, QEMU to convert the Virtual Machine Disk extension (VMDK) into RAW format \[2].&#x20;

On the data population step, the researcher checks Alta and Ionic’s features, such as if the heartbeat and steps recorded only during the device are used or any other methods can be recorded, such as data modification or deletion. This step is to find all the possibilities of the data being generated \[2]. Data collected from the Fitbit application synch with the cloud and accessed from the desktop, website, and mobile. The image was collected and converted using QEMU software to convert into RAW type to be read by Autopsy.

Two software are used to analyze the downloaded data. The analysis includes identifying what kind of data can be extracted from the application and log any change covering update delete insert. The researcher concludes that the use of both software, Autopsy and Bulk Extractor Viewer can provide sufficient information to the investigator to do the forensic investigation. Both software can generate important information such as user data, friends, messages, posts, besides the information related to activities, such as distance, calories burnt, and location. It depends on the requirement of the investigation, those data can be easily extracted using the software. However, Bulk Extractor Viewer has a better search feature to help the investigator search specific words \[2].

## Recommendation on Case Study

The use of digital forensic for any criminal case will vary for each case. The research on the study case above, limited to the use of the tool to generate the data from the Fitbit tracker which is defined specifically for Alta and Ionics tracker. The objective of the research is to reduce the analysis time by employing an open-source system. However, the aspect of usability by the user, never been investigated. Based on the objective to reduce the time to analyze, it depends on how easy the software can be used by the investigator.

The research also does not cover the download process time compared to the amount of data. Or compare if the different operating system, between Windows and Mac OS, has any significant impact on the performance.

The essay writer is suggesting a different view when Fitbit tracker is used for digital forensic investigation. Digital forensic investigation will not be limited to the past investigation only but can use to track the current activity related to the subject of investigation. Also, the use of the data can be leveraged to a different dimension. For example, the heartbeat change might be impacted in the case of the crime victim being in an uncomfortable situation. This can detect the time and relate to the location where the criminal case happened. In another sample, the heartbeat change also can be used as a preliminary check on the condition of a suspect during the investigation if the suspect hides anything or not \[12].

The essay writer is suggesting to add few additional coverages in the future research related to the Fitbit tracker such as:

1\.      Collect past cases involving Fitbit tracker as the digital evidence and identify what kind of data was used to investigate the case. This step is useful for the investigator to filter the necessary data to be used in their investigation.

2\.      Create categorization for each case and label the data for each category as the new dimension to interpret the data related to the case.

3\.      The legal aspect related to the data need to includes in the research.

Another suggestion is to add quantitative research, for example, to include the survey where the target is the investigator on which open-source software practically can be used based on the characteristics, like usability, how easy to use the software, and performance. Based on the result of the survey, in the initial stage of the research, can be decided, which software can be included in the research as the tool.

There are a few challenges for the digital forensic investigation using the Fitbit tracker that needs to consider like stated in the research by A. Shamlawi, et.al \[15]:

1\.      Legality of the use of digital data in forensic investigation. Each country has its law to allow which kind of data can be used in the court for forensic investigation. The research should be adjusted based on the country where it belongs. This legality issue could be a constraint when conducting research.

2\.      Operational issues during the investigation. The accuracy of the data might be questioned. For example, if the time set in the device, is not set correctly then the timestamp collected will not give accurate data. Another sample is the GPS location. If for any chance, the user using the path where the GPS can not be reached, for example, in the basement, then the investigation might not come to the right conclusion.

3\.      Device ownership. There is a possibility where the device is used by one person. The investigator needs to verify the time, location, and the person who used the device to get valid data.

Based on those challenges, future research might consider to includes those items as consideration. The software device is also updated from time to time, the future research should create the guidelines to be able to capture the changes.

## Key Characteristics

The first research, populated the data from two different open-source software, Bro and Corsaro to detect the attack rate and measure the performance between them. The research shows that Corsaro has a higher detection rate compared to Bro software. From the performance perspective, Corsaro shows a better processing time \[2].

The data was then classified by two different classifiers, Decision Tree and Naïve Bayes classifier. The research shows the performance of the Decision Tree classifier is better than the Naïve Bayes classifier \[2].

The first research shows the quantitative approach on their research as the main characteristic. Quantitative research is the research based on the numerical interpretation, based on the formula measurement to get the conclusion \[13]. Future research can consider another open-source tool as another option to get a better comparison. This quantitative approach, support the objective of the research to compare the performance of the software in the scope of the research.

The second research employs two open-source software, Autopsy and Bulk Extractor View to populate and analyze the data. There is no clear quantitative measurement of the research. The research only focuses on what type of data can be populated. No performance comparison is also available between that two software. The qualitative aspect of the research is analyzing the possible data that can be generated. The research comparing which is the better software can aid the investigator to investigate the case using digital forensic data. However, the result is subjective and debatable because the claim is not based on any standard. Both software can generate the same result of the data, where the Bulk Extractor View has additional capability on the search text. In the future, the researcher might go deep comparing the functionality and feature of each software and includes the comparison of the performance on a different platform.

Quantitative and Qualitative approaches might be used based on the situation and in which environment the research is being conducted \[13].  The researcher might mix both approaches for a broad perspective. The researcher also needs to have the expertise in the area to interpret the correct conclusion of the research.

## References

1        E. Balkanli, J. Alves and A. N. Zincir-Heywood, "Supervised learning to detect DDoS attacks," _2014 IEEE Symposium on Computational Intelligence in Cyber Security (CICS)_, 2014, pp. 1-8, doi: 10.1109/CICYBS.2014.7013367.

2        A. Almogbil, A. Alghofaili, C. Deane, T. Leschke, A. Almogbil and A. Alghofaili, "Digital Forensic Analysis of Fitbit Wearable Technology: An Investigator’s Guide," 2020 7th IEEE International Conference on Cyber Security and Cloud Computing (CSCloud)/2020 6th IEEE International Conference on Edge Computing and Scalable Cloud (EdgeCom), 2020, pp. 44-49, doi: 10.1109/CSCloud-EdgeCom49738.2020.00017.

3        Steinmacher, I., & Gerosa, M. A. (n.d.). Choosing an Appropriate Task to Start with in Open Source Software Communities: A Hard Task. In Collaboration and Technology (pp. 349–356). Cham: Springer International Publishing. [https://doi.org/10.1007/978-3-319-10166-8\_31](https://doi.org/10.1007/978-3-319-10166-8\_31)

4        Zeek Documentation \[Online]. Available: [https://docs.zeek.org/en/current/about.html](https://docs.zeek.org/en/current/about.html), \[Accessed: Jan 2022].

5        FAQ \[Online]. Available: [https://zeek.org/faq/](https://zeek.org/faq/) , \[Accessed: Jan 2022].

6        Corsaro Tarbal \[Online]. Available: [https://catalog.caida.org/details/software/corsaro](https://catalog.caida.org/details/software/corsaro) , \[Accessed: Jan 2022].

7        Fitbit Used as Key Evidence in Murder Case \[Online]. Available: [https://h11dfs.com/fitbit-data-used-as-evidence-in-murder-case/](https://h11dfs.com/fitbit-data-used-as-evidence-in-murder-case/) , \[Accessed: October 2022].

8        P. Olson. “Fitbit Data Now Being Used In The Courtroom” \[Online]. Available: [https://www.forbes.com/sites/parmyolson/2014/11/16/fitbit-data-court-room-personal-injury-claim/?sh=3a1e02987379](https://www.forbes.com/sites/parmyolson/2014/11/16/fitbit-data-court-room-personal-injury-claim/?sh=3a1e02987379)

9        K. Kent, S. Chevalier, T. Grance, Hung Dan. “Guide to Integrating Forensic Techniques into Incident Response”. National Institute of Standards and Technology. 2006.

10    Overview \[Online]. Available: [https://www.sleuthkit.org/sleuthkit/](https://www.sleuthkit.org/sleuthkit/) \[Accessed: Jan 2022].

11    Autopsy \[Online]. Available: [https://www.sleuthkit.org/autopsy/](https://www.sleuthkit.org/autopsy/) \[Accessed: Jan 2022].

12    E. Haseltine. “7 Ways to Really Tell If Someone is Lying to You” \[Online]. Available: [https://www.psychologytoday.com/us/blog/long-fuse-big-bang/201510/7-ways-really-tell-if-someone-is-lying-you](https://www.psychologytoday.com/us/blog/long-fuse-big-bang/201510/7-ways-really-tell-if-someone-is-lying-you) \[Accessed: Jan 2022]

13    R. Miller. “Qualitative vs Quantitative Research” \[Online]. Available: [https://domyessay.com/blog/qualitative-vs-quantitative](https://domyessay.com/blog/qualitative-vs-quantitative) \[Accessed: 2022]

14    S. Meister. “Find Potentially Sensitive Information with Bulk Extractor Viewer” \[Online]. Available: [https://confluence.educopia.org/display/BC/Find+Potentially+Sensitive+Information+with+Bulk+Extractor+Viewer](https://confluence.educopia.org/display/BC/Find+Potentially+Sensitive+Information+with+Bulk+Extractor+Viewer) \[Accessed: Jan 2022]

15    A. Shamlawi, T. Khairallah. “Wearables as Digital Evidence, Fitbit Evidence Case Study”. Princess Sumaya University for Technology, Jordan. 2019.

&#x20;
