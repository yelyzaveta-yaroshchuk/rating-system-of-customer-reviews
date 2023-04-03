# -rating-system-of-customer-reviews
The project aimed to create a rating system of customer reviews for ride-hailing company (Uklon)  from the most crucial to the least.

Use case:
- Define what is critical feedbacks, find and prioritized them 
- Do not lose  driver as an employee
- Do no lose  client loyalty

<img width="504" alt="image" src="https://user-images.githubusercontent.com/129201759/229491495-d165525e-f2ea-4e70-bdea-9688d3a34b36.png">

**Exploratory Analysis**

- 60 % of  feedbacks are negative
- Sentiment analysis added 5% to negative feedbacks with positive marks
- Some region have significant low median mark

<img width="423" alt="image" src="https://user-images.githubusercontent.com/129201759/229492901-fb5a180c-1cdb-4e29-a5c0-300566f32ef7.png">

Critical cases – low frequent group ( 5% of negative feedbacks)
- another car
- another person in the car 
- violence 
- weapon mentioned
- driver found personal info( number, place of living etc.)
- dropped off far away from final way
- driver is drunk

<img width="235" alt="image" src="https://user-images.githubusercontent.com/129201759/229491999-9a889197-3495-49de-86c6-0f5c3efc324f.png">

**Preprocessing** 

1. Sentiment analysis with Hugging Face
2. Main data set – mark is in (1,2,3) or negative sentiment
3. Extend stop words list and remove it from feedbacks
4. Remove special signs and emoji
5. Lower Case
6. Spell correction with TextBlob 
7. Word tokenization
8. Lemmatization ('NOUN', 'ADJ', 'VERB', 'ADV’)

**Topic Modeling: Latent Dirichlet Allocation**

_Hyper parameter tunninig:  Grid Search 
Coherence Score: 0.49
Perplexity:  -7.5_

<img width="470" alt="image" src="https://user-images.githubusercontent.com/129201759/229492513-b711366a-1f29-4ba1-9213-ffddae9b075f.png">

**Regression Modeling**

- Split test/train 
- Balance data
    - Current solution : decrease number of non critical cases
- Logistic Regression

<img width="529" alt="image" src="https://user-images.githubusercontent.com/129201759/229492741-570ceba6-093b-4255-b4ca-162b0281c79a.png">

<img width="528" alt="image" src="https://user-images.githubusercontent.com/129201759/229492810-aa637eb7-ec5a-4a76-9002-134708bccfe6.png">









