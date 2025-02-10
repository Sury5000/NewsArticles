# News Classification using BERT/DistilBERT

This project leverages the **BERT** model (specifically **DistilBERT**, a smaller and faster version) for text classification on a dataset of news articles from various genres. The goal is to classify news articles into genres such as **sports**, **technology**, **politics**, **business**, **entertainment**, **health**, and **science**.

### Key Features:
- **Text Classification** using pre-trained BERT models.
- **Multiple Genres**: Classifying news articles into seven different genres.
- **Fine-Tuning**: Hyperparameter tuning to improve model performance.
- **Evaluation**: Includes accuracy, precision, recall, and F1 score metrics.
- **Early Stopping**: Stops training if model performance does not improve after a set number of evaluations.

## Requirements

- Python 3.6 or higher
- `transformers` (Hugging Face library)
- `torch` (PyTorch)
- `sklearn` (for evaluation metrics and data handling)
- `requests` (for fetching news articles)

You can install the required dependencies with the following command:

```bash
pip install -r requirements.txt



torch>=1.9.0
transformers>=4.0.0
scikit-learn>=0.24.0
requests>=2.25.0
pandas>=1.2.0


Setup
Clone the Repository: Clone this repository to your local machine using the following command:

bash
Copy code
git clone https://github.com/yourusername/news-classification-bert.git
cd news-classification-bert
Fetch News Data: The script fetches news articles for each genre (sports, technology, politics, etc.) from the NewsAPI. You will need an API key to fetch articles:

Visit NewsAPI and get your free API key.
Replace the api_key in the script with your own key.
How It Works
Fetch News Articles: The script pulls news articles for each genre (sports, technology, politics, etc.) from the NewsAPI.

Data Preprocessing:

Combines article titles and descriptions.
Handles missing data (e.g., missing descriptions or titles).
Labels the articles with their corresponding genres.
Model:

Uses DistilBERT for sequence classification.
Fine-tunes the model on the news dataset, using labels for genre classification.
Trains the model for multiple epochs, applying early stopping to prevent overfitting.
Evaluation: The model is evaluated based on:

Accuracy
Precision
Recall
F1 Score
Output: After training, the model is evaluated on a test set, and results (metrics) are printed to the console.

Training and Evaluation
Training the Model
Run the script to start training the model:

bash
Copy code
python train.py
The model will be trained for 10 epochs and evaluate after each epoch. It will save the best model during training based on validation performance.

Early Stopping
If the models performance stops improving for 2 consecutive evaluations, the training process will stop early to save resources and avoid overfitting.

Evaluation Metrics
During evaluation, the following metrics are computed:

Accuracy: The percentage of correctly classified samples.
Precision: The ability of the classifier to identify only relevant samples.
Recall: The ability of the classifier to identify all relevant samples.
F1 Score: A balanced metric that combines precision and recall.
Results
After training, the evaluation results (loss, accuracy, precision, recall, and F1 score) are printed in the console. These metrics help assess how well the model is performing on the test dataset.

Sample evaluation output:

text
Copy code
Evaluation Results: {'eval_loss': 1.6125, 'eval_runtime': 42.5, 'eval_samples_per_second': 3.29, 'eval_steps_per_second': 0.21, 'epoch': 5.0}





