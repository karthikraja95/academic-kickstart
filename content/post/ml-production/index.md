---
title: "Machine Learning Production, Machine Learning Research and Sofware Engineering"
date: 2021-01-114
math: true
diagram: true
image:
  # placement: 3
  # caption: 'Image credit: [**John Moeses Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)'
---

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
