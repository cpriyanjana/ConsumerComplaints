# Consumer Complaints

This is an analysis of the ConsumerComplaints Dataset. This dataset consists of consumer complaints related to various financial products and services. Below are key insights that I have extracted:

## Most Commonly Complained About Products and Issues
  These are the products and issues that the consumers complained about the most. This is valuable because it helps businesses focus on the key areas of consumer dissatisfaction.
```
ggplot(df_summary, aes(x = reorder(Product, -Complaint.Count), y = Complaint.Count)) +
  geom_bar(stat = "identity", fill = "blue") +
  coord_flip() +
  labs(title = "Number of Complaints by Product", x = "Product", y = "Complaint Count")
```
![Rplot](https://github.com/user-attachments/assets/25514c6d-7047-40c2-865c-17d5753b3701)

# Here's the Top 10
```
product_counts <- df %>%
  count(Product, sort = TRUE) %>%
  top_n(10)

ggplot(product_counts, aes(x = reorder(Product, n), y = n, fill = Product)) +
  geom_bar(stat = "identity") +
  coord_flip() +
  labs(title = "Top 10 Most Complained About Products",
       x = "Product", y = "Number of Complaints") +
  theme_minimal()
```
![MostComplainedAboutProducts](https://github.com/user-attachments/assets/aef5e5f7-0679-4ad3-9bb8-63ef8562dec6)


## Trend Analysis of Complaints Over Time
  Here is a visualization of how complaints have occured over time. This is valuable to identify trends, spikes, and improvements.



Sentiment Analysis of Consumer Complaint Narratives

Perform sentiment analysis using Bing and NRC sentiment lexicons on consumer complaint narratives.
Helps in understanding consumer emotions and their intensity.
Company Response Effectiveness

Analyze how companies respond to complaints and whether consumers dispute the resolution.
Important to assess customer service effectiveness and consumer satisfaction.
Geographical Distribution of Complaints

Identify states with the highest number of complaints.
Useful for targeted regulatory actions and local business improvements.
