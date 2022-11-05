---
description: >-
  By Indra Dewaji, part of assignment of Understanding AI, University of Essex,
  May 2022
---

# Artificial Intelligence and  Its Applications in Investment Industry

## 1.  Executive Summary

Indo Invest Securities is a startup company on investment management company providing investment services including stock trading and mutual fund management. It operates in Indonesia and is registered on the Jakarta stock exchange. The company operates through an online operation to serve the customer with minimal branches in the main cities in Indonesia. There is a need to employ Artificial Intelligence to improve efficiency in its operation, especially in customer verification, customer care, and stock trading tool.

## 2.  Introduction

Artificial Intelligence has been adopted and grown in recent years in the finance industry (Guerrero et al., 2021). The affordability and increase in computing power have supported this growth (OECD, 2022). Based on Barclay Hedge’s (2018) survey, in the investment industry, shows that 56% of respondence already used Artificial Intelligence/Machine Learning (AI/ML) for their investment processes. Of the respondence who employed machine learning, around two-thirds are using AI/ML to generate the idea of trading, and the rest use AI/ML to optimize their portfolio.

There are two types of investors in the investment industry. The first type is the fundamental investors, where investment decisions will be based on the fundamental of the company, such as financial statements, profit and loss calculations, market growth, etc. While the second type of investor is based on quantitative, where their decision is based on the historical data. They do not really pay attention to the financial statement or other fundamental data (McPartland, 2018).

****![](<.gitbook/assets/image (13).png>)****

**Figure 1**. Evolution of Trading (OECD, 2022)

Stock trading involving those two types of investment has evolved where it employs AI/ML to help the decision. The trading begins with the conventional trading in the 80s, then it starts employing probabilistic statistical calculation. From the statistical calculation, it’s evolved into the algorithm for high-frequency trading. By the time it evolved with AI-driven algorithmic trading (OECD, 2022).

## 3.  Problem Identification and the AI Solution

OECD (2022) has identified some problems that can be solved by AI/ML. It is divided into the back office, middle office, and front office. AI/ML in the back office such as post-trade processing, reporting, data analytics, and trading profit and loss reconciliation. In the middle office, AI/ML can be employed for the “Know Your Customer” or KYC function, risk management, anti-fraud detection, or compliance. And for the front office, AI/ML can be employed for asset allocation, Robo trading advisors, or customer service functions.&#x20;

The company has identified the three AI/ML function where it is crucial to implement, those are “Know Your Customer” or KYC, Stock Trading Prediction Tool, and Customer Service function through a chatbot.

### **3.1        Know Your Customer (KYC) for the Customer Verification**

“Know Your Customer” or KYC is an investor identification process based on the information given by the investor and it’s validated with the authority data. This validation is quite tedious if it is involving a huge number of investors managed by the company. It will require a huge number of resources and time. The KYC is required as part of authority regulation for anti-money laundering validation (Smith, 2022).

United Nations office has reported that financial services globally have been penalized for about USD 35 Billion annually for non-compliance (WNS, 2022). The KYC needs to have an accurate risk profile and due diligence to make sure of compliance with the authority. The KYC also needs to improve the investor experience when onboarding as a client of the company (Twomey, 2018).         &#x20;

In the current process, the KYC will do through online and offline. The customer filled the information through an online or offline form. The most important process during the KYC is uploading the proof of the information, such as a photo, identification card, or tax card scanned copy (Sable, 2021). In the offline process, the photo is verified with the person directly, while the identification card and tax card will be verified with the original documents. This process is complex through online applications.

Image processing and text detection are employed for the automation of identification and tax card. To perform character recognition, the technology of Optical Character Recognition (OCR) is used to recognize the character on the card. Tesseract is an open-source OCR software developed by HP used for character recognition (Satyawan et al., 2019). Tesseract uses Artificial Intelligence for text detection. It’s using adaptive recognition method where the first step is the stage to recognize the character, and the second step is to fill the character which is not recognized compared to the word or sentence in the context (Medium, 2019).

There are two possible methods to verify the data, verify the information in the card with the inputted data in the online form or connect to a government-provided API to check and verify the authenticity of the card. For more advanced methods, may use the picture of the customer holding the identity card for the verification process. There are many available AI methods for the image comparison, such as Peak Signal to Noise Ratio (PSNR), Means Squared Error (MSE), Structure Similarity Index (SSIM), and many more (Raval, 2021). Those methods will compare the images, especially on the face area from the customer picture who holds the id card, with the photo on the id card. This verification process adds to the authenticity of the customer.

### **3.2        Stock Trading Prediction Tool**

Trading in the stock exchange required a highly skilled and experienced investment/fund manager. One of the growth factors for the investment company is the operation activity at the stock exchange (Lomakin, 2020). The activity must be effective and efficient whereas most startup companies only employ small members at the beginning. There is a need to have a tool for stock trading that will enhance the effectiveness of the company to build the portfolio.

The stock analysis is mainly divided into two characteristic, fundamental analysis, and technical analysis. Fundamental analysis focuses on the financial report, macroeconomy, market strategy, assets, and liability. Technical analysis focuses on the historical data based on the price action during the trading (Chen, 2021). In most cases, people's sentiments also become one of the factors impacting the stock market. Sentiment analysis is required to predict how the price action might happen in the market (Cakra & Trisedya, 2015).

An artificial method such as Regression and Long Short-Term Memory (LSTM) has been used by researchers to analyze and predict the stock market (Parmar et al., 2018). The simplest technique is using linear regression. Linear regression calculates the prediction based on the dependent and independent variables (Bini & Matthew, 2016). The more advanced regression is multiple regression. Like its name, the prediction involves multiple independent variables.

LSTM is an advanced model of Recurrent Neural Networks (RNN) (Roondiwala, 2017). LSTM used long historical data while the relationship between the current and previous information is calculated based on the RNN model (Parmar et al. 2018). It has been proved by researchers that LSTM gives high accuracy in its prediction.

### **3.3        Chatbot for the Customer Service Function**

Maintaining the relationship between the company and investors is crucial. The customer service will take functions such as answering general queries from the investor until to do the trading of the stock on behalf of the customer.

Customer service also may give some suggestions for the new client who become the first-time investor or still have less knowledge of the investment industry (Arabian News, 2019). But since those functions basically are redundant tasks, it is more efficient if there is a tool such as a chatbot that employs an AI tool to do those redundant tasks.

According to Insight (2018), there are some benefits to the company when implementing chatbots for the customer service function such as reducing operation costs, increasing engagement, helping to analyze the conversation for decision making, time efficiency, and can invest more in the staff skill. Chatbot builds on the Natural Language Processing (NLP) a part of Artificial Intelligence platform (Piskovoj, 2022).

The chatbot can interact with humans to answer any questions or link it with another tool, such as stock prediction, or general queries about the service. There are ready-made chatbot applications with a little customization in the market that can be implemented such as IBM Watson (Karman, 2017). A chatbot can interact with the user while it integrates with another application to populate the data required.

## 4.  Implementation

Based on the problem identification and the technical solution, there are two possible approaches to implement the solution, such as implementing ready-made software or implementing a customized solution. The pros and cons of implementing the ready-made software listed by Piskovoj (2022) such as, it is fast to implement, easy to integrate with the API provided, and in terms of cost, it is budget friendly. But it has limited functionality and is hard to customize.

In the end, up to the company whether to choose which approach with the pros and cons given. If functionality is the consideration, the custom solution developed internally is the best approach. But if the budget becomes the consideration, the company might choose ready-made software as the approach.

## 5.  Conclusion

Artificial Intelligence (AI) technology helps investment management company to improve their service. Technology such as KYC, Stock Prediction tool, or Chatbot, are some AI technologies that can be implemented. The implementation of the technology will depend on the needs of the company, and whether to use the ready-made software or full-custom implementation. AI has changed the way companies operate where the investment will be allocated efficiently to more useful allocation.

&#x20;

## References

Arabian News. (2021) Man vs Machine: How AI robots are taking over online trading. Available from: [https://www.arabianbusiness.com/money/wealth/alternative-assets/467610-man-vs-machine-how-ai-robots-are-taking-over-online-trading](https://www.arabianbusiness.com/money/wealth/alternative-assets/467610-man-vs-machine-how-ai-robots-are-taking-over-online-trading) \[Accessed 17 April 2022].

Barclay Hedge. (2022) BarclayHedge Survey: Majority of Hedge Fund Pros Use AI/Machine Learning in Investment Strategies. Available from: [https://www.barclayhedge.com/insider/barclayhedge-survey-majority-of-hedge-fund-pros-use-ai-machine-learning-in-investment-strategies](https://www.barclayhedge.com/insider/barclayhedge-survey-majority-of-hedge-fund-pros-use-ai-machine-learning-in-investment-strategies) \[Accessed 17 April 2022].

Bini, B.S. and Mathew, T. (2016) Clustering and regression techniques for stock prediction. _Procedia Technology_ 24:1248-1255.

Cakra, Y.E. & Trisedya, D.B. (2015) _Stock price prediction using linear regression based on sentiment analysis_. Available from: doi:10.1109/icacsis.2015.7415179.

Chen, J. (2021) _What Is Stock Analysis?_: Investopedia. Available from: [https://www.investopedia.com/terms/s/stock-analysis.asp#:\~:text=Stock%20analysis%20is%20a%20method,markets%20by%20making%20informed%20decisions](https://www.investopedia.com/terms/s/stock-analysis.asp) \[Accessed 24 April 2022].

Guerrero, M., Liñán, F. & Cáceres-Carrasco, F.R. (2021) The influence of ecosystems on the entrepreneurship process: a comparison across developed and developing economies. _Small Business Economics_ 57(4): 1733–1759. Available from: doi:10.1007/s11187-020-00392-2.

Insight. (2018) 5 Undisputable Reasons to Invest in Chatbot Technology. Available from: [https://www.insight.com/en\_US/content-and-resources/2018/02142018-5-undisputable-reasons-to-invest-in-chatbot-technology.html](https://www.insight.com/en\_US/content-and-resources/2018/02142018-5-undisputable-reasons-to-invest-in-chatbot-technology.html) \[Accessed 8 May 2022].

Karman, M. (2017) _How to build an investment management chatbot_: IBM. Available from: [https://www.ibm.com/cloud/blog/announcements/build-investment-management-chatbot](https://www.ibm.com/cloud/blog/announcements/build-investment-management-chatbot) \[Accessed 8 May 2022].

Lomakin, N.I., Popov, I.A., Shohneh, A.B., Maramygin, M.C., et al. (2020) AI-System of Stock Exchange Trading Robot for Financial Risk Hedging: _Proceedings of the 3rd International Conference on Business and Management of Technology (ICONBMT 2021)_. \[Online]. 2020 Proceedings of the 3rd International Conference on Business and Management of Technology (ICONBMT 2021). p. Available from: doi:10.2991/aebmr.k.200312.473.

McPartland, K. (2018) _Quantimental Investing: The New Way to Beat The Market_: Forbes. Available from: [https://www.forbes.com/sites/kevinmcpartland/2018/07/12/quantimental-investing-the-new-way-to-beat-the-market/?sh=411d2f145f15](https://www.forbes.com/sites/kevinmcpartland/2018/07/12/quantimental-investing-the-new-way-to-beat-the-market/?sh=411d2f145f15) \[Accessed 17 April 2022].

Medium. (2019) What is Tesseract and how it works? Available from: [https://bytepace.medium.com/what-is-tesseract-and-how-it-works-dfff720f4a32](https://bytepace.medium.com/what-is-tesseract-and-how-it-works-dfff720f4a32) \[Accessed 7 May 2022].

OECD. (2022) _OECD Business and Finance Outlook 2021 : AI in Business and Finance_.  Available from: [https://www.oecd-ilibrary.org/sites/39b6299a-en/index.html?itemId=/content/component/39b6299a-en](https://www.oecd-ilibrary.org/sites/39b6299a-en/index.html?itemId=/content/component/39b6299a-en) \[Accessed 17 April 2022].

Parmar, I., Agarwal, N., Saxena, S., Arora, R., et al. (2018) _Stock Market Prediction Using Machine Learning_. Available from: doi:10.1109/icsccc.2018.8703332.

Piskovoj, D. (2022) _How to Build a Chatbot with Natural Language Processing_: Sloboda Studio. Available from: [https://sloboda-studio.com/blog/how-to-use-nlp-for-building-a-chatbot/#:\~:text=An%20NLP%20based%20chatbot%20is,%2C%20Facebook%20Messenger%2C%20or%20Telegram](https://sloboda-studio.com/blog/how-to-use-nlp-for-building-a-chatbot/) \[Accessed 8 May 2022].

Raval, P. (2021) _Measuring similarity in two images using Python:_ Medium. Available from: [https://towardsdatascience.com/measuring-similarity-in-two-images-using-python-b72233eb53c6](https://towardsdatascience.com/measuring-similarity-in-two-images-using-python-b72233eb53c6) \[Accessed 7 May 2022].

Roondiwala, M., Patel, H. and Varma, S. (2017) Predicting stock prices using LSTM. _International Journal of Science and Research (IJSR)_ _6_(4): 1754-1756.

Sable, A. (2021) _AI in KYC Automation: What Every Business Needs to Know:_ AI & Machine Learning Blog. Available from: [https://nanonets.com/blog/kyc-automation-using-deep-learning/](https://nanonets.com/blog/kyc-automation-using-deep-learning/) \[Accessed 7 May 2022].

Sanz, J.L.C. & Zhu, Y. (2021) _Toward Scalable Artificial Intelligence in Finance_. Available from: doi:10.1109/scc53864.2021.00067.

Satyawan, W., Octaviano Pratama, M., Jannati, R., Muhammad, G., Fajar, B., Hamzah, H., Fikri, R. and Kristian, K. (2019) Citizen Id Card Detection using Image Processing and Optical Character Recognition. _Journal of Physics: Conference Series_, 1235(1), p.012049.

Saxena, S. (2016) _Introduction to Long Short Term Memory (LSTM):_ Analytics Vidhya. Available from: [https://www.analyticsvidhya.com/blog/2021/03/introduction-to-long-short-term-memory-lstm/#:\~:text=Long%20Short%20Term%20Memory%20Network,is%20used%20for%20persistent%20memory](https://www.analyticsvidhya.com/blog/2021/03/introduction-to-long-short-term-memory-lstm/) \[Accessed 8 May 2022].

Smith, O. (2022) _How Artificial Intelligence is Revamping KYC and AML?:_ Medium. Available from: [https://medium.com/shufti-pro/how-artificial-intelligence-is-revamping-kyc-and-aml-f4b1538d5bc0](https://medium.com/shufti-pro/how-artificial-intelligence-is-revamping-kyc-and-aml-f4b1538d5bc0) \[Accessed 17 April 2022].

Smith, R. (2007). An overview of the Tesseract OCR engine. _Ninth international conference on document analysis and recognition (ICDAR 2007)_ (2): 629-633.

Twomey, N. (2018) _5 Ways AI is Impacting AML and KYC Compliance:_ Corporate Compliance Insights. Available from: [https://www.corporatecomplianceinsights.com/5-ways-ai-is-impacting-aml-and-kyc-compliance/](https://www.corporatecomplianceinsights.com/5-ways-ai-is-impacting-aml-and-kyc-compliance/) \[Accessed 17 April 2022].

WNS. (2022) _From Customer Knowledge to Customer Behavior: How AI & ML Have Shifted the Efficacy of the AML / KYC Process_. Available from: [https://www.wns.com/perspectives/blogs/blogdetail/611/from-customer-knowledge-to-customer-behavior-how-ai--ml-have-shifted-the-efficacy-of-the-aml-/-kyc-process](https://www.wns.com/perspectives/blogs/blogdetail/611/from-customer-knowledge-to-customer-behavior-how-ai--ml-have-shifted-the-efficacy-of-the-aml-/-kyc-process) \[Accessed 17 April 2022].

&#x20;
