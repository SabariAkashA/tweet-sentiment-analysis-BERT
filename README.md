# Tweet Sentiment Analysis using BERT

This project uses Hugging Face's BERT and RoBERTa models to perform sentiment classification on airline tweets from Kaggle. It evaluates binary vs. 3-class models using confusion matrices and classification reports.

## 📂 Dataset
- **Source**: [Twitter US Airline Sentiment Dataset](https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment)
- **Labels**: positive, negative, neutral

## 📌 Tasks Performed
- Used Hugging Face `pipeline()` with:
  - `distilbert-base-uncased-finetuned-sst-2-english`
  - `cardiffnlp/twitter-roberta-base-sentiment-latest`
- Compared confusion matrices of both
- Evaluated performance using `classification_report`

## 🔍 Results
- BERT performed well for binary but failed on neutral
- Twitter-RoBERTa handled 3-class sentiment more accurately

## 📊 Classification Report Analysis
| Metric        | Negative | Neutral | Positive |
| ------------- | -------- | ------- | -------- |
| **Precision** | 93%      | 68%     | 78%      |
| **Recall**    | 87%      | 68%     | 95%      |
| **F1-score**  | 90%      | 68%     | 86%      |

`✅ Overall Accuracy: 85%`

## 📌 Conclusion

In this project, we explored tweet sentiment classification using pre-trained transformer models.

- We started with `distilbert-base-uncased-finetuned-sst-2-english`, which is limited to binary sentiment (positive/negative). As expected, it struggled with neutral tweets.
- To improve accuracy and coverage, we switched to `cardiffnlp/twitter-roberta-base-sentiment-latest`, a RoBERTa-based model trained on millions of tweets for 3-class sentiment (positive, neutral, negative).

### ✅ Final Results:
- **Overall Accuracy**: 85%
- **Negative Tweets**: Precision 93%, F1-score 90%
- **Neutral Tweets**: Precision 68%, F1-score 68%
- **Positive Tweets**: Recall 95%, F1-score 86%

The RoBERTa model clearly handled nuanced sentiment better than the earlier binary BERT.

---

## 🧠 Key Learnings:
- Hugging Face `pipeline()` enables quick experimentation with powerful models
- Pretrained models work well but choosing the right one for your dataset matters
- Confusion matrix + classification report help interpret model behavior in real-world cases

This project highlights how transformer models like RoBERTa can be effectively used for social media sentiment analysis.

