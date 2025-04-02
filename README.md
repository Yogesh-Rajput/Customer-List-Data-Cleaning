# 🧹 Customer-List-Data-Cleaning
This project demonstrates a simple yet practical example of data cleaning using Python and pandas library. The dataset contains customer details, which are cleaned and preprocessed to prepare for future marketing or analytics applications.

## 📁 Project Files
* Customer Call List.xlsx – Raw dataset with customer names, phone numbers, addresses, etc.
* Customer_List_Data_Cleaning.ipynb – Jupyter Notebook containing step-by-step data cleaning operations.

## 🧾 Before Cleaning
Some messy data...
<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CustomerID</th>
      <th>First_Name</th>
      <th>Last_Name</th>
      <th>Phone_Number</th>
      <th>Address</th>
      <th>Paying Customer</th>
      <th>Do_Not_Contact</th>
      <th>Not_Useful_Column</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1001</td>
      <td>Frodo</td>
      <td>Baggins</td>
      <td>123-545-5421</td>
      <td>123 Shire Lane, Shire</td>
      <td>Yes</td>
      <td>No</td>
      <td>True</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1002</td>
      <td>Abed</td>
      <td>Nadir</td>
      <td>123/643/9775</td>
      <td>93 West Main Street</td>
      <td>No</td>
      <td>Yes</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1003</td>
      <td>Walter</td>
      <td>/White</td>
      <td>7066950392</td>
      <td>298 Drugs Driveway</td>
      <td>N</td>
      <td>NaN</td>
      <td>True</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1004</td>
      <td>Dwight</td>
      <td>Schrute</td>
      <td>123-543-2345</td>
      <td>980 Paper Avenue, Pennsylvania, 18503</td>
      <td>Yes</td>
      <td>Y</td>
      <td>True</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1005</td>
      <td>Jon</td>
      <td>Snow</td>
      <td>876|678|3469</td>
      <td>123 Dragons Road</td>
      <td>Y</td>
      <td>No</td>
      <td>True</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1006</td>
      <td>Ron</td>
      <td>Swanson</td>
      <td>304-762-2467</td>
      <td>768 City Parkway</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>True</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1007</td>
      <td>Jeff</td>
      <td>Winger</td>
      <td>NaN</td>
      <td>1209 South Street</td>
      <td>No</td>
      <td>No</td>
      <td>False</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1008</td>
      <td>Sherlock</td>
      <td>Holmes</td>
      <td>876|678|3469</td>
      <td>98 Clue Drive</td>
      <td>N</td>
      <td>No</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1009</td>
      <td>Gandalf</td>
      <td>NaN</td>
      <td>N/a</td>
      <td>123 Middle Earth</td>
      <td>Yes</td>
      <td>NaN</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1010</td>
      <td>Peter</td>
      <td>Parker</td>
      <td>123-545-5421</td>
      <td>25th Main Street, New York</td>
      <td>Yes</td>
      <td>No</td>
      <td>True</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1011</td>
      <td>Samwise</td>
      <td>Gamgee</td>
      <td>NaN</td>
      <td>612 Shire Lane, Shire</td>
      <td>Yes</td>
      <td>No</td>
      <td>True</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1012</td>
      <td>Harry</td>
      <td>...Potter</td>
      <td>7066950392</td>
      <td>2394 Hogwarts Avenue</td>
      <td>Y</td>
      <td>NaN</td>
      <td>True</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1013</td>
      <td>Don</td>
      <td>Draper</td>
      <td>123-543-2345</td>
      <td>2039 Main Street</td>
      <td>Yes</td>
      <td>N</td>
      <td>False</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1014</td>
      <td>Leslie</td>
      <td>Knope</td>
      <td>876|678|3469</td>
      <td>343 City Parkway</td>
      <td>Yes</td>
      <td>No</td>
      <td>False</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1015</td>
      <td>Toby</td>
      <td>Flenderson_</td>
      <td>304-762-2467</td>
      <td>214 HR Avenue</td>
      <td>N</td>
      <td>No</td>
      <td>False</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1016</td>
      <td>Ron</td>
      <td>Weasley</td>
      <td>123-545-5421</td>
      <td>2395 Hogwarts Avenue</td>
      <td>No</td>
      <td>N</td>
      <td>False</td>
    </tr>
    <tr>
      <th>16</th>
      <td>1017</td>
      <td>Michael</td>
      <td>Scott</td>
      <td>123/643/9775</td>
      <td>121 Paper Avenue, Pennsylvania</td>
      <td>Yes</td>
      <td>No</td>
      <td>False</td>
    </tr>
    <tr>
      <th>17</th>
      <td>1018</td>
      <td>Clark</td>
      <td>Kent</td>
      <td>7066950392</td>
      <td>3498 Super Lane</td>
      <td>Y</td>
      <td>NaN</td>
      <td>True</td>
    </tr>
    <tr>
      <th>18</th>
      <td>1019</td>
      <td>Creed</td>
      <td>Braton</td>
      <td>N/a</td>
      <td>N/a</td>
      <td>N/a</td>
      <td>Yes</td>
      <td>True</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1020</td>
      <td>Anakin</td>
      <td>Skywalker</td>
      <td>876|678|3469</td>
      <td>910 Tatooine Road, Tatooine</td>
      <td>Yes</td>
      <td>N</td>
      <td>True</td>
    </tr>
    <tr>
      <th>20</th>
      <td>1020</td>
      <td>Anakin</td>
      <td>Skywalker</td>
      <td>876|678|3469</td>
      <td>910 Tatooine Road, Tatooine</td>
      <td>Yes</td>
      <td>N</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>

## ✅ After Cleaning
Much cleaner and standardized!
<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CustomerID</th>
      <th>First_Name</th>
      <th>Last_Name</th>
      <th>Phone_Number</th>
      <th>Address</th>
      <th>Paying Customer</th>
      <th>Do_Not_Contact</th>
      <th>Street_Address</th>
      <th>State</th>
      <th>Zip_Code</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1001</td>
      <td>Frodo</td>
      <td>Baggins</td>
      <td>123-545-5421</td>
      <td>123 Shire Lane, Shire</td>
      <td>Yes</td>
      <td>No</td>
      <td>123 Shire Lane</td>
      <td>Shire</td>
      <td></td>
    </tr>
    <tr>
      <th>1</th>
      <td>1003</td>
      <td>Walter</td>
      <td>White</td>
      <td>706-695-0392</td>
      <td>298 Drugs Driveway</td>
      <td>No</td>
      <td></td>
      <td>298 Drugs Driveway</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>2</th>
      <td>1005</td>
      <td>Jon</td>
      <td>Snow</td>
      <td>876-678-3469</td>
      <td>123 Dragons Road</td>
      <td>Yes</td>
      <td>No</td>
      <td>123 Dragons Road</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>3</th>
      <td>1008</td>
      <td>Sherlock</td>
      <td>Holmes</td>
      <td>876-678-3469</td>
      <td>98 Clue Drive</td>
      <td>No</td>
      <td>No</td>
      <td>98 Clue Drive</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>4</th>
      <td>1010</td>
      <td>Peter</td>
      <td>Parker</td>
      <td>123-545-5421</td>
      <td>25th Main Street, New York</td>
      <td>Yes</td>
      <td>No</td>
      <td>25th Main Street</td>
      <td>New York</td>
      <td></td>
    </tr>
    <tr>
      <th>5</th>
      <td>1012</td>
      <td>Harry</td>
      <td>Potter</td>
      <td>706-695-0392</td>
      <td>2394 Hogwarts Avenue</td>
      <td>Yes</td>
      <td></td>
      <td>2394 Hogwarts Avenue</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>6</th>
      <td>1013</td>
      <td>Don</td>
      <td>Draper</td>
      <td>123-543-2345</td>
      <td>2039 Main Street</td>
      <td>Yes</td>
      <td>No</td>
      <td>2039 Main Street</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>7</th>
      <td>1014</td>
      <td>Leslie</td>
      <td>Knope</td>
      <td>876-678-3469</td>
      <td>343 City Parkway</td>
      <td>Yes</td>
      <td>No</td>
      <td>343 City Parkway</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>8</th>
      <td>1015</td>
      <td>Toby</td>
      <td>Flenderson</td>
      <td>304-762-2467</td>
      <td>214 HR Avenue</td>
      <td>No</td>
      <td>No</td>
      <td>214 HR Avenue</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>9</th>
      <td>1016</td>
      <td>Ron</td>
      <td>Weasley</td>
      <td>123-545-5421</td>
      <td>2395 Hogwarts Avenue</td>
      <td>No</td>
      <td>No</td>
      <td>2395 Hogwarts Avenue</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>10</th>
      <td>1017</td>
      <td>Michael</td>
      <td>Scott</td>
      <td>123-643-9775</td>
      <td>121 Paper Avenue, Pennsylvania</td>
      <td>Yes</td>
      <td>No</td>
      <td>121 Paper Avenue</td>
      <td>Pennsylvania</td>
      <td></td>
    </tr>
    <tr>
      <th>11</th>
      <td>1018</td>
      <td>Clark</td>
      <td>Kent</td>
      <td>706-695-0392</td>
      <td>3498 Super Lane</td>
      <td>Yes</td>
      <td></td>
      <td>3498 Super Lane</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>12</th>
      <td>1020</td>
      <td>Anakin</td>
      <td>Skywalker</td>
      <td>876-678-3469</td>
      <td>910 Tatooine Road, Tatooine</td>
      <td>Yes</td>
      <td>No</td>
      <td>910 Tatooine Road</td>
      <td>Tatooine</td>
      <td></td>
    </tr>
  </tbody>
</table>
</div>

## 🛠️ Tasks Performed
* Removed duplicate entries.
* Dropped irrelevant columns.
* Cleaned inconsistent formatting in names (e.g., slashes or trailing punctuation).
* Standardized phone number formats.
* Converted ambiguous labels to uniform values.
* Handled missing values in columns.
* Ensured final data is clean and ready for downstream tasks such as segmentation, visualization, or CRM integration.

## 📌 Skills & Tools Used
* Python 🐍
* pandas 📊
* Jupyter Notebook

## 🚀 How to Run
* Clone this repository.
* Open Customer_List_Data_Cleaning.ipynb in Jupyter Notebook.
* Make sure Customer Call List.xlsx is in the same folder.
* Run the notebook cells step-by-step to reproduce the cleaning process.
