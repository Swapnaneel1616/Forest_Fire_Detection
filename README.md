# Forest Fire FWI Prediction

This is a machine learning web application built with **Flask** and **Scikit-learn** that predicts the **Fire Weather Index (FWI)** based on meteorological data.

## 📋 About The Project

This project deploys a trained **Ridge Regression** model as a web service. A user can input weather observations, and the model will predict the FWI, which is a key indicator of fire intensity and danger.

The model was trained on the **Algerian Forest Fires Dataset**, which includes data from two regions: Bejaia and Sidi Bel-abbes.

### Key Features (Inputs)

The model uses 9 features to make a prediction:
* **Temperature**: Temperature in Celsius
* **RH**: Relative Humidity (%)
* **Ws**: Wind Speed (km/h)
* **Rain**: Rain (mm)
* **FFMC**: Fine Fuel Moisture Code
* **DMC**: Duff Moisture Code
* **ISI**: Initial Spread Index
* **Classes**: A binary (1 for fire, 0 for no fire) used as an input feature
* **Region**: A binary (1 for Sidi-Bel Abbes, 0 for Bejaia)

---

## 🚀 How It Works

The application logic is handled by `application.py`:
1.  **User Interface**: A user accesses the root route (`/`) and is shown `index.html`, which contains a form.
2.  **Data Submission**: The user fills in the 9 features and submits the form, which sends a `POST` request to the `/predictdata` endpoint.
3.  **Data Preprocessing**: The app loads the saved `StandardScaler` (`scaler.pkl`) and uses it to scale the user's input data. This is crucial as the model was trained on scaled data.
4.  **Prediction**: The scaled data is fed into the pre-trained `Ridge` regression model (`ridge.pkl`).
5.  **Display Result**: The model's prediction (a single FWI value) is returned and rendered on the `home.html` page.

---

## 🛠️ Technology Stack

* **Backend**: Flask
* **Machine Learning**: Scikit-learn 
* **Data Handling**: NumPy, Pandas
* **Models**: Linear Regression ,  Ridge Regression , Elasticnet Regularisation 
* **Model Deployment**: `pickle`

---

## 📂 Project Structure
