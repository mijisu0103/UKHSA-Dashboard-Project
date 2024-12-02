<div align="justify">
  
# About this Repository ℹ️

This repository contains the project I did as a part of the coursework for ECS780P - Computer Programming. <br>
The assignment required me to develop a simple dashboard that downloads and displays the UK Government's infectious diseases [data](https://ukhsa-dashboard.data.gov.uk/) published by the UK Health Security Agency ([UKHSA](https://www.gov.uk/government/organisations/uk-health-security-agency)).

Click the below button to launch this repository as a Binder: <br>
<div align = center>
  <a href="https://mybinder.org/v2/gh/mijisu0103/UKHSA-Dashboard-Project/HEAD" target="_blank">
      <img src="https://mybinder.org/badge_logo.svg" alt="Binder">
  </a>
</div>

<br>

Click [here](https://hub.binder.curvenote.dev/user/mijisu0103-ukhs-shboard-project-80h0jz5g/voila/render/DIY%20Dashboard.ipynb) to render the dashboard template (```DIY Dasboard.ipynb```) with Voila <br>
- Sometimes, it takes a while to load the dashboard or execution gets stuck at a certain point
    - In this case, simply spam refreshing button until it loads the dashboard

<br>

## Motivation ⚙️
### Chosen Disease Data
- Influenza
- Rhinovirus (Common Cold)
- COVID-19

<br>

### Motivation of Choosing These Three Diseases
As the weather gets colder, it is common for people to feel unwell. Whether it is a cough, sore throat, or fatigue, it is easy to wonder if one has caught a cold (Rhinovirus) or flu (Influenza) or COVID-19. This is because all three share similar symptoms. This overlap can make it difficult for one to determine which illness one might have. For this reason, I decided to compare and contrast these three diseases using data from the UKHSA.

<br>

### What I am doing specifically using such data
To be specific, I am using these APIs for this project:
- Influenza percentage of positive PCR tests in a 7 day period
- Rhinovirus(Common cold) percentage of positive PCR tests in a 7 day period
- Covid-19 percentage of positive PCR tests in a 7 day rolling period

<br>

The first two APIs provide the weekly average percentage of positive PCR tests for Influenza and Rhinovirus, while the third API offers the daily percentage of positive PCR tests for COVID-19. To ensure consistency in the comparison, adjusting the data from the third API to align with the weekly average format used by the first two is required. Eventually, the weekly average percentage of positive PCR tests for Influenza, Rhinovirus, and COVID-19 will be compared. 

<br>

The UKHSA has been experiencing technical issues in updating the percentage of positive PCR tests for COVID-19, which has resulted in "NaN" (Not a Number) values in the data. I have chosen not to fill these missing values with zeros, as doing so could misrepresent the actual situation and lead to inaccurate conclusions. While I am transforming the daily data to a weekly format to compare it with the Influenza and Rhinovirus data, this transformation does not alter the underlying data itself — it is only the aggregation method. By leaving the NaN values unchanged, I have tried to maintain the integrity of the analysis and ensure that any gaps in reporting are accurately reflected.

<br>

It is important to note that, as I am using live APIs, the data is continually updated. Once the UKHSA resolves the technical issues and updates the data, the missing values (NaNs) will be replaced with the most current information. Therefore, the NaN values are temporary, and the analysis will reflect the updated data when it becomes available.

<br>

## Environment 👩🏻‍💻 

<div align="center">
  <img src="https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=flat-square&logo=jupyter&logoColor=white">&nbsp;&nbsp;&nbsp;&nbsp;
    
<img src="http://img.shields.io/badge/Visual%20Studio%20Code-eeeeee.svg?style=flat-square&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAeCAYAAAA7MK6iAAAFU0lEQVRIx+1Wa2iWZRi+nuc9fedt7uCnrth0y9QMzVTSLFxhs8iaEFkRCwrKisSCIEgUifpjICFRRgc6iKClleWkxEjRskxHbvPUnC530O3b9p2/932e++7HNw+luP0YCNUDN++fh/t67+u+rvu5BTPjWhyJa3T+e8Dinz3+srkPmw/3w2cZWDqrGD+cTGJhdQggQnNXHOMKAygJ+xBLprFhfzvKwj6MK/RjVNAZs+tE7I2kVTh6fGlkXdBQPyY9I6GYMXOMidrxgZGtWEoBITDpw32nvtx+8GR9S3e69qceY1tLv9zqMeoNgaAQI0y1zGecvuVgx+YjHQMzQ44JWwoAAn8kRM1vveKjxpjYSYT5IwLMAPyWAUOKudsaOz4/1h2fHLAlNAOaGQzANgQUAX2umP3JUb12WMBCAFIAhrycIwEgaJvY2xqr3XP83MaeRLbSMSU0MZQiENHf8tgGkFIiMiSwzxRQGg/Ec7QumdPltiHAlyQKORZ2NHXWr/3++Ka+lFvusw1oYmgipF0FhlCaAU2AYsDL/wcNCdx0Nvf4oa7sx7tPJZ9bsbPr24Ec3Rtx8tf8loEvDv65bE1D83pmDjmmAWZAaUJWERZOjb4/p6p4fcrV0ACI86GvMB0vA/6xLflYT0ZFIo7EiVhu6ieNfRs3NcVf8FvS2n20+5X1u0+s8YhtQwCKCPGsBwLceVUlr94/dczS0pC/NacYRAARoBkgghjSx3taYxOXN5x9/0xCzQ1aAq5mkBD6xgJ5pO30qUmkPGlZJogY8azC+JLQsedrql4805f5pl+E4DkFq/Z08UrfYIuIAb/JrQ114QlXrVgIHL056jwyu9y3M+kSLClgAkZLH01R4aiUdgCep9Gf8TCvumTb2iXT7qsqDXyjLT9koBCKiDUBRHwxeBg+Lg+bmBW12m8v9y26oyK4Ja0YQgCOAQjTgRceDeVE8MydE1Y8NOO6uori4ImEC2TMMAT0BbvpS0JdgerLgG1T4voCG0dOd4dine1hlRqAZgFFDKU1NAl4/mKc5YKSHu2EcopxOsFIugI6r13WfFFYg6GHAWygYyAzZV9rz44Dbb1325leuIkYki7BUwwwQYDx2aHYsk2HB75r7MrMNSUQEhmMDUmkPTJo0E6aBoHBQ1fc2D4w980dLZ+f6klN89kmkjkPMt2bnl6CXYYh0ymPQEwI2QI/t6dufX7bma+bzuWeqh5lYUKhCUX5iZWfYnkvD4vq17cfWd3SGZ8Y9pnoS7soKwh03ndzeX1Nhb9m+ZzSp13FiaRL0AyEbIlYRhW9tffcez+0pd6JOl5RNCjj7nkbYfDLwwCeWVm8pros1HkunsW86rJdL9dOXhTymZtTLmF+ZfDT1XeVPRm2jVgiq6GJYRoCjinxwYHep1/a3rGhrd+daUoBzQw9qGoweEgfr/z6MCQwK+fx9Po5FRuauhKJ75u7URQOYOFNY1FZZOGXM5napV+1f9idVNECR4IBsACSWYVx0TIUjSqGpryeiIGAiZO/PhoZf9WKlWY4prE/WuB7128biZwinH9PGUA8q/Hg5EjDstuKF08YZR9LuJQvh4GgJQFmaOYLiub8vDaH9ToRMxTlqbrSk+jmvb3vsWlFddUlzsF4ji5yeUk3NQMpj1HsQ+eILQKaAE9z87OzSxcvqArtSmQUmAHBDE8zBrIER3J6UhG2vjLDempENxBNDGa0raoZ/ciCGyINyZxCymM4Eql7rsPmukqxeP44WSeA30d8y9TMUITu1XePXfLEraNfu2Ws7+1FFbzggQrxsG1ghzs4RIZU9f8L/b8O+C9rntGn+AUx4QAAAABJRU5ErkJggg==">
</div>

<br>

## Stack 🛠️
<div align="center">
  <img src="https://img.shields.io/badge/python-3670A0?style=flat-square&logo=python&logoColor=white">
</div>

<br>

## Repository Structure 🌲
```bash
.
├── DIY Dashboard.ipynb
├── binder
│   └── requirements.txt
├── covid19.json
├── covid19_2.json
├── influenza.json
├── rhinovirus.json
├── timeseriesdf.pkl
└── README.md
```

<br>

## Reflection 🪞
Developing the dashboard to visualise data on Influenza, Rhinovirus, and COVID-19 was a rewarding experience that combined data analysis, visualisation, and interactive web technologies. The project required transforming daily COVID-19 data into weekly averages to align with Influenza and Rhinovirus data, ensuring consistency for comparison. Handling "NaN" values in COVID-19 data, caused by UKHSA technical issues, presented an ethical challenge; I chose not to fill these gaps to preserve data integrity, accurately reflecting incomplete reporting while ensuring the dashboard adapts as updates become available.

Using Python, I leveraged pandas for data manipulation, matplotlib for visualisation, and iPywidgets for interactivity. Deploying with Voila and Binder transformed the project into an accessible web application. These tools highlighted the challenges of harmonising datasets and working with live APIs, emphasising the need for adaptability and clear documentation of limitations.

This project reinforced critical lessons in data integrity, technical skill development, iterative problem-solving, and accessibility. While the dashboard effectively compares the selected diseases, future improvements could include integrating additional metrics (e.g., hospitalisation rates) and enhancing interactivity. Overall, the project demonstrated the importance of building reliable, flexible, and user-friendly tools that reflect real-world complexities.


<br>
  
</div>




