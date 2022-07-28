# Potential-Telent

Our aim is to rank potential telent given a job title. If a candidate is selected, the ranking will change according to the new information of the selected candidate.


![image](https://user-images.githubusercontent.com/62399559/181297483-b76e3c43-ef69-4aaf-bf86-8b177fcf39db.png)

In order to find out the best match to the search key words, four similarity calculations are used - Fuzzy similarity, Cosine similarity, Euclidean distance, Jaccard Similarity. Note that Euclidean distance is scaled to range 0-1 by MinMax Scaling.

Combined similarity metric is obtained from the mixed ratio of the four similarity score.

To determine the threshold of each similarity measure, we create pareto plots for every similarity calculation. We want to create a short list that include at least the top 20% candidate. Therefore, we need to decide the cut-off point from the pareto plot. For fuzzy similarity, we choose 80%; For Jaccard similarity, we choose 70%, For Cosine similarity, we choose 60%; For Euclidean distance, we choose 1

![image](https://user-images.githubusercontent.com/62399559/181297253-786e50c5-b410-45ef-985a-afc09347d156.png)

After the creation of short list, we then employ a review procedure. 

# Re-ranking

The list will be re-ranked if a candidate is chosen. The selected candidate will be considered as ideal candidate and a new ranking will be generated based on the information of the ideal candidate.

The distance between the location of the ideal candidate and the location of other candidate will be one of the critiria for the new ranking. The closer the location, the higher is the rank. A new combined similarity score is also computed using the title of the ideal candidate.
