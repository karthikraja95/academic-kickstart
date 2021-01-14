---
title: "Machine Learning Production, Machine Learning Research and Sofware Engineering"
date: 2021-01-114
math: true
diagram: true
image:
  # placement: 3
  # caption: 'Image credit: [**John Moeses Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)'
---
# Machine Learning Production Vs Machine Learning Research


Most people who are experts in Machine Learning gained their experience through academia: taking courses, doing research and reading research papers. 
Most companies nowadays use Machine Learning, although it is still relatively new compared to traditional software engineering. 
If you are one of the people who learned ML through academia, you might have a very different industry experience. **ML Production is very different from ML Research**. Lets talk about some of the differences.

## 1. Objectives/Goals/Intention

Often, ML Research has one single objective: **model performance and achieving state-of-the-art (SOTA) results**. In contrast, there are many stakeholders involved in bringing an ML system into Production. Also, **each stakeholder might have a different objective**. For example, consider an app like UberEats or DoorDash; they have ML engineers, sales team, product team, infrastructure teams and managers. 

- The **ML engineers** want a model that recommends restaurants that users will most likely order. They believe they can do so by using a more complex model with more data.
- The **sales team** wants a model that recommends restaurants that pay the highest advertising fee since ads bring more revenue than just service fees.
- The **product team** wants a model that can do inference faster than the ML engineers' model.
- The **infrastructure team** wants to hold off the production line to update the infrastructure due to some security reasons.
- The **manager** wants to maximize the margin, and one way to achieve it is to let go of the ML team. For example, [Airbnb](https://adage.com/article/cmo-strategy/airbnb-job-cuts-took-heavy-toll-marketers-designers-and-data-scientists/2256246) lays off several Data Scientists due to COVID-19 crisis.

These objectives require different models, yet the stakeholders will have to collaborate to create a model that will satisfy all of them.

Production having different objectives from the research is one reason why successful research projects might not always be used in production. Ensembling is a technique popular among the winners of many ML competitions, including the famed $1M Netflix Prize. It combines *"multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms alone."* While ensemble systems give a small improvement in performance, it might be too complex, error-prone to deploy, slower, and hard to interpret.


## 2. Computation - Training vs Inference

**Most research prioritizes fast training whereas most production prioritizes fast inference.** Just to refresh our memory. **Latency** refers to the time it takes from receiving a query to returning the result. **Throughput** refers to how many queries are processed within a specific period of time. One corollary of this is that *research prioritizes high throughput whereas production prioritizes low latency.*

In research, we care more about how many samples we can process in a second (throughput) and less about how long it takes for each sample to be processed (latency). We are willing to increase latency to increase throughput.

However, once we deploy our model into the real world, latency matters a lot. In 2009, [Google's experiments](https://services.google.com/fh/files/blogs/google_delayexp.pdf) demonstrated that increasing web search latency 100 to 400 ms reduces the daily number of searches per user by 0.2% to 0.6%. In 2019, [Booking.com](https://blog.acolyer.org/2019/10/07/150-successful-machine-learning-models/) found that an increase of about 30% in latency cost about 0.5% in conversion rates.


## 3. Data

In ML Research, the datasets we work with are often **cleaned and well-formatted**, which allows us to focus on developing and training models. Research Datasets are **static** by nature so that the researchers can use them to benchmark new architectures and techniques. In research, we mostly work with **historical data**, and we won't often serve our models to users.

In ML Production, there might be a case you don't have an excellent dataset to start with. Even if the data is available, it is **messy, noisy, unstructured and constantly shifting over time**. Annotated labels, if there are any, are **sparse, imbalanced, outdated, or incorrect**. Changing project or business requirements might require adding another label class or merging two existing label classes. If we work with users' data, we'll also have to think about **privacy and regulatory concerns**.

## 4. Ethics and Fairness

In my opinion, almost everyone or someone in our life might already be a victim of biased Machine Learning algorithms without even knowing it. For example:

- Loan application might be rejected because the ML algorithm picks on your zip code, which incorporates biases about the socio-economic background. 
- A resume might be ranked lower because the ranking system employers use picks on your name. For example, Bob can get more preference than Xin Lee.
- The mortgage might get a higher interest rate because it relies partially on credit scores, which reward the rich and punish the poor. 

[Other examples of ML biases in the real world](https://weaponsofmathdestructionbook.com/) are predictive policing algorithms, personality tests administered by potential employers, and college ranking.

**ML algorithms don’t predict the future but encode the past, perpetuating the biases in the data and more.** When *ML algorithms are deployed at scale, they can discriminate against people at scale.* For example, A human might only make incorrect judgments about a few individuals at a time. In that case, an ML algorithm can make incorrect judgments about millions in split seconds.  [McKinsey & Company research in 2019](https://www.mckinsey.com/featured-insights/artificial-intelligence/tackling-bias-in-artificial-intelligence-and-in-humans), **revealed only 13% of the large companies surveyed said they are taking steps to mitigate risks to equity and fairness, such as algorithmic bias and discrimination.**

## 5. Interpretability and Explainable AI

First of all, **Interpretability and Explainability is essential for users, both business leaders and end-users, to understand why a decision is made so that they can trust a model and detect potential biases as mentioned above**. Second, it’s important for Machine Learning engineers and developers to debug and improve a model.

Since most ML research is still evaluated on a single objective like model performance, researchers aren’t incentivized to work on model interpretability and explainability. However, *Interpretability isn’t just optional for most ML use cases in the industry, but a requirement.*

Just because Interpretability is a requirement doesn’t mean everyone is doing it. According to [Stanford](https://hai.stanford.edu/research/ai-index-2019), as of 2019, only **19% of large companies are working to improve the explainability of their algorithms.**
 
# Machine Learning Vs Software Engineering

Software Engineering (SWE) and best practices have been successfully used in the production environment for more than 50 years now. Since Machine Learning (ML) is a part of Sofware Engineering, some of you might think, why don't we just the best practices in Software Engineering and use that in Machine Learning?

Well, that's an *outstanding idea*. To be honest, ML Production would be way easier if ML experts are better Software Engineers. Still, both ML experts and Software Engineers are specialists in different areas. **ML experts** are *strong in statistical thinking, modelling techniques, feature engineering, etc*. At the same time, **Software specialists** are good at *building products, scalability and maintenance, etc*. Well, it's rare to find an expert in both ML and Software. But we can definitely use the best practices from both industries to build a stable ML product.

Many traditional SWE tools can be used to develop and deploy ML applications. However, **many challenges are unique to ML applications and require their own tools**. **In SWE, there's an underlying assumption that code and data are separated**. *In fact, in SWE, we want to keep things as modular and separate as possible.*

On the contrary, **ML systems are part code, part data. The last ten years trend shows that applications developed with the most/best data win (OpenAI's GPT3 and DALL-E).** Instead of focusing on improving ML algorithms, most companies will focus on improving their data. Because data can change quickly,*ML applications need to be adaptive to the changing environment, requiring faster development and deployment cycles.*

**In traditional SWE, you only need to focus on testing and versioning your code. With ML, we have to test and version our data too, which's the hard part. How to version large datasets? How to know if a data sample is good or bad for your system? Not all data samples are equal -- some are more valuable to your model than others.**

**The size of ML models gives another challenge.** As of 2020, it's common for ML models to have hundreds of millions, if not billions, of parameters, which requires GBs of RAM and GPU to load them into memory. A few years from now, a billion parameters might seem normal.

**Monitoring and debugging these models in production is also non-trivial**. As ML models get more complex, coupled with the lack of visibility into their work, it’s hard to figure out what went wrong or be alerted quickly enough when things go wrong.

Now, enough about the differences in ML and SWE. The good news is that these engineering challenges are being tackled at a tremendous pace. In 2018, when BERT first came out, people talked about how BERT was too big, too complex, and too slow to be practical. In 2021, BERT is just a few  lines of code with efficient libraries and almost used in every Natural Language Processing (NLP) tasks.

How can we also use these techniques in our day to day life and build models into production at ease? Here are some of the problems facing ML production and we might want to think about? Thanks to [Chip](https://twitter.com/chipro) for sharing the following amazing resources.


- **Data testing**: How to test the usefulness and correctness of data? How to know if a sample is good or bad for your system?
- **Data and model versioning**: How to version datasets and checkpoints? Line-to-line comparison like Git works for code but doesn’t work for datasets or model checkpoints. You can’t also naively make multiple copies of large datasets. How do you merge different versions of data? Example: [DVC](https://github.com/iterative/dvc).
- **Monitoring**: How to know that your data distribution has shifted and you need to retrain your model? Example: [Dessa](https://www.dessa.com/).
- **Data labeling**: How to quickly label the new data or re-label the existing data for the new model? Example: [Snorkel](https://www.snorkel.org/).
- **CI/CD test**: How to run tests to make sure your model still works as expected after each change, since you can’t spend days waiting for it to train and converge? Example: [Argo](https://argoproj.github.io/).
- **Deployment**: How to package and deploy a new model or replace an existing model? Example: [OctoML](https://octoml.ai/).
- **Model compression**: How to compress an ML model to fit onto consumer devices? 
- **Inference optimization**: How to speed up inference time for your models? Can we fuse operations together? Can we use lower precision? Making a model smaller might make its inference faster. Example: [TensorRT](https://developer.nvidia.com/tensorrt).
- **Edge device**: Hardware designed to run ML algorithms fast and cheap. Example: [Coral SOM](https://coral.ai/products/som/).
- **Privacy**: How to use user data to train your models while preserving their privacy? How to make your process GDPR-compliant? Example: [PySyft](https://github.com/OpenMined/PySyft).
- **Data manipulation**: DataFrames designed for parallelization and compatible with GPUs as pandas doesn’t work on GPUs. Example: [Dask](https://github.com/dask/dask).
- **Data format**: If your samples have many features and you only want to use a subset of them, using row-based data formats like CSV still requires you to load all features. Columnar file formats like PARQUET and ORC are optimized for that use case.

### In conclusion, ML production sounds scarier at first, but with these tools, it is FUN!!!

I hope this article is somewhat informative and helpful!!!
