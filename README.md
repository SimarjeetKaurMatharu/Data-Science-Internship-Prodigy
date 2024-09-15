# Data-Science-Internship-Prodigy InfoTech TASK 1
{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "74774a5a",
   "metadata": {},
   "source": [
    "**Task 1:- to create a bar chart or histogram to visualize the distribution of a categorical or continuous variable.**"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "a9dbe51b",
   "metadata": {},
   "source": [
    "In this task, we conducted an analysis of the Titanic dataset to determine the distribution of passengers who survived versus those who did not. This analysis was performed using Python, specifically leveraging the pandas and matplotlib.pyplot libraries within a Jupyter Notebook environment.\n",
    "\n",
    "**Analysis Summary**\n",
    "\n",
    "Objective:- To visualize and quantify the number of passengers who survived and those who did not.\n",
    "\n",
    "Tools Used- Pandas (for data manipulation and analysis) and  Matplotlib (for creating visual representations of data)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "ba57adaa",
   "metadata": {},
   "source": [
    "The analysis revealed that,\n",
    "\n",
    "**342 passengers survived** the titanic disaster and **549 did not survive**.\n",
    "\n",
    "Out of Survivors, **109 were Females** and **233 were males**"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "id": "5d3e31c5",
   "metadata": {},
   "outputs": [],
   "source": [
    "import numpy as np\n",
    "import pandas as pd\n",
    "import matplotlib.pyplot as plt\n",
    "import seaborn as sns"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "11606921",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Cabin</th>\n",
       "      <th>Embarked</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C85</td>\n",
       "      <td>C</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>C123</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>886</th>\n",
       "      <td>887</td>\n",
       "      <td>0</td>\n",
       "      <td>2</td>\n",
       "      <td>Montvila, Rev. Juozas</td>\n",
       "      <td>male</td>\n",
       "      <td>27.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>211536</td>\n",
       "      <td>13.0000</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>887</th>\n",
       "      <td>888</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Graham, Miss. Margaret Edith</td>\n",
       "      <td>female</td>\n",
       "      <td>19.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>112053</td>\n",
       "      <td>30.0000</td>\n",
       "      <td>B42</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>888</th>\n",
       "      <td>889</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Johnston, Miss. Catherine Helen \"Carrie\"</td>\n",
       "      <td>female</td>\n",
       "      <td>NaN</td>\n",
       "      <td>1</td>\n",
       "      <td>2</td>\n",
       "      <td>W./C. 6607</td>\n",
       "      <td>23.4500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>889</th>\n",
       "      <td>890</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Behr, Mr. Karl Howell</td>\n",
       "      <td>male</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>111369</td>\n",
       "      <td>30.0000</td>\n",
       "      <td>C148</td>\n",
       "      <td>C</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>890</th>\n",
       "      <td>891</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Dooley, Mr. Patrick</td>\n",
       "      <td>male</td>\n",
       "      <td>32.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>370376</td>\n",
       "      <td>7.7500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>Q</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>891 rows × 12 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "     PassengerId  Survived  Pclass  \\\n",
       "0              1         0       3   \n",
       "1              2         1       1   \n",
       "2              3         1       3   \n",
       "3              4         1       1   \n",
       "4              5         0       3   \n",
       "..           ...       ...     ...   \n",
       "886          887         0       2   \n",
       "887          888         1       1   \n",
       "888          889         0       3   \n",
       "889          890         1       1   \n",
       "890          891         0       3   \n",
       "\n",
       "                                                  Name     Sex   Age  SibSp  \\\n",
       "0                              Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1    Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                               Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3         Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                             Allen, Mr. William Henry    male  35.0      0   \n",
       "..                                                 ...     ...   ...    ...   \n",
       "886                              Montvila, Rev. Juozas    male  27.0      0   \n",
       "887                       Graham, Miss. Margaret Edith  female  19.0      0   \n",
       "888           Johnston, Miss. Catherine Helen \"Carrie\"  female   NaN      1   \n",
       "889                              Behr, Mr. Karl Howell    male  26.0      0   \n",
       "890                                Dooley, Mr. Patrick    male  32.0      0   \n",
       "\n",
       "     Parch            Ticket     Fare Cabin Embarked  \n",
       "0        0         A/5 21171   7.2500   NaN        S  \n",
       "1        0          PC 17599  71.2833   C85        C  \n",
       "2        0  STON/O2. 3101282   7.9250   NaN        S  \n",
       "3        0            113803  53.1000  C123        S  \n",
       "4        0            373450   8.0500   NaN        S  \n",
       "..     ...               ...      ...   ...      ...  \n",
       "886      0            211536  13.0000   NaN        S  \n",
       "887      0            112053  30.0000   B42        S  \n",
       "888      2        W./C. 6607  23.4500   NaN        S  \n",
       "889      0            111369  30.0000  C148        C  \n",
       "890      0            370376   7.7500   NaN        Q  \n",
       "\n",
       "[891 rows x 12 columns]"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df=pd.read_csv(\"C:\\\\Users\\\\Simarjeet kaur\\\\Downloads\\\\titanic.csv\")\n",
    "df"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "id": "8dc64a58",
   "metadata": {
    "scrolled": true
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Fare</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>count</th>\n",
       "      <td>891.000000</td>\n",
       "      <td>891.000000</td>\n",
       "      <td>891.000000</td>\n",
       "      <td>714.000000</td>\n",
       "      <td>891.000000</td>\n",
       "      <td>891.000000</td>\n",
       "      <td>891.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>mean</th>\n",
       "      <td>446.000000</td>\n",
       "      <td>0.383838</td>\n",
       "      <td>2.308642</td>\n",
       "      <td>29.699118</td>\n",
       "      <td>0.523008</td>\n",
       "      <td>0.381594</td>\n",
       "      <td>32.204208</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>std</th>\n",
       "      <td>257.353842</td>\n",
       "      <td>0.486592</td>\n",
       "      <td>0.836071</td>\n",
       "      <td>14.526497</td>\n",
       "      <td>1.102743</td>\n",
       "      <td>0.806057</td>\n",
       "      <td>49.693429</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>min</th>\n",
       "      <td>1.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>0.420000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>0.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>25%</th>\n",
       "      <td>223.500000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>2.000000</td>\n",
       "      <td>20.125000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>7.910400</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>50%</th>\n",
       "      <td>446.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>3.000000</td>\n",
       "      <td>28.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>14.454200</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>75%</th>\n",
       "      <td>668.500000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>3.000000</td>\n",
       "      <td>38.000000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>31.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>max</th>\n",
       "      <td>891.000000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>3.000000</td>\n",
       "      <td>80.000000</td>\n",
       "      <td>8.000000</td>\n",
       "      <td>6.000000</td>\n",
       "      <td>512.329200</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "       PassengerId    Survived      Pclass         Age       SibSp  \\\n",
       "count   891.000000  891.000000  891.000000  714.000000  891.000000   \n",
       "mean    446.000000    0.383838    2.308642   29.699118    0.523008   \n",
       "std     257.353842    0.486592    0.836071   14.526497    1.102743   \n",
       "min       1.000000    0.000000    1.000000    0.420000    0.000000   \n",
       "25%     223.500000    0.000000    2.000000   20.125000    0.000000   \n",
       "50%     446.000000    0.000000    3.000000   28.000000    0.000000   \n",
       "75%     668.500000    1.000000    3.000000   38.000000    1.000000   \n",
       "max     891.000000    1.000000    3.000000   80.000000    8.000000   \n",
       "\n",
       "            Parch        Fare  \n",
       "count  891.000000  891.000000  \n",
       "mean     0.381594   32.204208  \n",
       "std      0.806057   49.693429  \n",
       "min      0.000000    0.000000  \n",
       "25%      0.000000    7.910400  \n",
       "50%      0.000000   14.454200  \n",
       "75%      0.000000   31.000000  \n",
       "max      6.000000  512.329200  "
      ]
     },
     "execution_count": 17,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.describe()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 18,
   "id": "6386cdac",
   "metadata": {
    "scrolled": true
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Cabin</th>\n",
       "      <th>Embarked</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C85</td>\n",
       "      <td>C</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>C123</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PassengerId  Survived  Pclass  \\\n",
       "0            1         0       3   \n",
       "1            2         1       1   \n",
       "2            3         1       3   \n",
       "3            4         1       1   \n",
       "4            5         0       3   \n",
       "\n",
       "                                                Name     Sex   Age  SibSp  \\\n",
       "0                            Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                             Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                           Allen, Mr. William Henry    male  35.0      0   \n",
       "\n",
       "   Parch            Ticket     Fare Cabin Embarked  \n",
       "0      0         A/5 21171   7.2500   NaN        S  \n",
       "1      0          PC 17599  71.2833   C85        C  \n",
       "2      0  STON/O2. 3101282   7.9250   NaN        S  \n",
       "3      0            113803  53.1000  C123        S  \n",
       "4      0            373450   8.0500   NaN        S  "
      ]
     },
     "execution_count": 18,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 19,
   "id": "700a07ed",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0"
      ]
     },
     "execution_count": 19,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df['Fare'].isnull().sum()  "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 29,
   "id": "8c12e67b",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAAArcAAAIhCAYAAABUopIpAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjcuMCwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy88F64QAAAACXBIWXMAAA9hAAAPYQGoP6dpAABFTklEQVR4nO3deVyU5f7/8ffIMgIiKiiIW6hoC2iJ5dFSNNRyrayTZR617LSYFqnHk3m+R9rA5bilmS0mlqdsOdqeqWmWmecgai5tlgtqkKHEouxcvz96ML9GIGUYHbh9PR+P+/Forvua6/7ccw347p5rbmzGGCMAAADAAup5ugAAAADAXQi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3wO8kJyfLZrNVuk2ePNnT5engwYNONfn4+Cg4OFhXXnmlHn74Ye3du7fCcz799FPZbDZ9+umn1TrW4sWLlZycXK3nVHasMWPGqEGDBtUa50y2bNmihIQE/frrrxX29e7dW71793br8VC1iy66qMqfmd9vycnJSkhIkM1mc3q+K+8zV5X/fB88eLDGY5W/18s3Ly8vhYaG6s9//rO++eabmhcLwGXeni4AqI2WLVumiy++2KktPDzcQ9VUNGHCBI0YMUJlZWX69ddftWPHDr300ktauHChkpKS9Le//c3Rt0uXLvryyy916aWXVusYixcvVkhIiMaMGXPWz3H1WNW1ZcsWPfbYYxozZowaNWrktG/x4sXn9Nhwtnr1ahUWFjoev/jii1q6dKnWrFmjoKAgR3u7du1UWFio66+/3un5rrzPXDVo0CB9+eWXat68udvGTExMVJ8+fVRUVKRt27bp8ccf1yeffKLdu3erRYsWbjsOgLNHuAUqERUVpa5du7p1zOLiYtlsNnl71/zHrnXr1vrTn/7keDxw4EBNnDhRw4YN05QpUxQVFaUBAwZIkho2bOjU91woP7fzcawzOdfBGs6uuOIKp8dr1qyRJMXExCgkJKRC/5YtW56XuirTtGlTNW3a1K1jRkZGOt7zvXr1UqNGjTR27FglJydr2rRpbj2WlZ06dUr+/v6eLgMWwbIEoBp++OEH3XnnnYqMjJS/v79atGihIUOGaPfu3U79yj+yfOWVVzRp0iS1aNFCdrtdP/zwgyRp/fr1iouLU8OGDeXv76+rr75an3zySY1q8/Pz09KlS+Xj46PZs2dXqOX3SwX279+v2267TeHh4bLb7QoNDVVcXJx27twp6bePmvfu3atNmzY5Pna96KKLznhuf7QEYu/evYqLi1NAQICaNm2q8ePH69SpU4795UsuKvuI2mazKSEhQZKUkJDguDIdERHhqK/8mJUtSzhx4oTGjRunFi1ayNfXV23bttW0adOcrjiWH2f8+PF65ZVXdMkll8jf31+dO3fW+++/f8bXv6CgQJMmTdLll1+uoKAgNWnSRN27d9c777xT6fmMHz9ey5YtU8eOHeXn56euXbtq69atMsZo9uzZioiIUIMGDXTttdc63je/99JLL6lz586qX7++mjRpoptuuqnCx+HlS0J++OEHDRw4UA0aNFCrVq00adKkCud+5MgR3XLLLQoMDFSjRo10xx13KCUlpco5ccXpyxL+6H3myut5pnmralnCmjVrFBcXp6CgIPn7++uSSy5RUlKSS+dYHnQPHTokSXrmmWfUq1cvNWvWTAEBAYqOjtasWbNUXFzs9LwdO3Zo8ODBatasmex2u8LDwzVo0CAdOXLE0efNN99Ut27dHHW2bdtWd911l9M4OTk5mjx5siIiIuTr66sWLVooPj5eJ0+edOk1k6R33nlHnTp1kt1uV9u2bbVgwYJKl5gYY7R48WJdfvnl8vPzU+PGjXXLLbdo//79Tv169+6tqKgoffbZZ+rRo4f8/f0d57Fhwwb17t1bwcHB8vPzU+vWrXXzzTc7/a4AzoQrt0AlSktLVVJS4tTm7e2tn376ScHBwZoxY4aaNm2qEydOaPny5erWrZt27Nihjh07Oj1n6tSp6t69u5YsWaJ69eqpWbNmWrFihUaNGqUbbrhBy5cvl4+Pj5577jldd911+vjjjxUXF+dy3eHh4YqJidGWLVtUUlJS5VXigQMHqrS0VLNmzVLr1q2VmZmpLVu2ONawrl69WrfccouCgoIcH/Pb7fYznltGRkalxysuLtbAgQN177336pFHHtGWLVv05JNP6tChQ3rvvfeqdY533323Tpw4oYULF2rVqlWOj5irumJbUFCgPn366Mcff9Rjjz2mTp066fPPP1dSUpJ27typDz74wKn/Bx98oJSUFD3++ONq0KCBZs2apZtuuknfffed2rZtW2VdhYWFOnHihCZPnqwW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0EALFy7U6NGjdeLECd1yyy1q1qyZfvnlF3311Vf65Zdf9Oyzz55xnLS0NG3dulVlZWXKzs52/BGHQ4cOac6cOerfv3+Vz921a5fGjx+vP//5z4qMjJSvr682bNigXbt2Oa4QSf//StLrr7+utm3bqn79+tX+B6qcr6+v5syZo7y8PF155ZWOuyUMGDBA11xzjSQ51uu99NJLateunTp37qz//e9/jhD8e+V1LFiwQKNHj5aPj486duzotH6w3KhRo/TMM89o9OjROnjwoKKjo7V582YlJiZq4MCB6tu3r0vndLrBgwdr1apVGjdunG655RYdPnxYTzzxhJo3b659+/a55RiS1KhRI/3f//2fHn30UY0aNUq33367jh8/rscee0z169fX9OnTqz3m6NGjNW/ePI0cOVJPPvmk2rdvr48++kgff/yxJKlevXN3HaSq99n5eD0bNGigOXPm6O6771bfvn3117/+VaGhofrhhx/01VdfadGiRTUav1+/fvL19dXtt9+uKVOmqKCgQM8++6yysrKc+r3//vtavHixbrzxRrVt21bGGK1atUq//vqr+vXrJ0n65z//qSNHjiguLk4tW7bUr7/+qgULFsjHx0exsbGSpPj4eP3nP/9Rr1699PDDD6tTp04qKytTWlqa1q5dq0mTJqlbt27VOofHH39cgwYN0nXXXaeHHnpIpaWlmj17tho0aOC0hOrqq6/WPffcozvvvFPbtm1Tr169FBAQoPT0dG3evFnR0dG6//77//BYS5Ys0YYNGzRo0CC1bt1aBQUFjqvQ7vo5xQXCQ19kA2ql8m9Tn/5t43JZWVlm7NixplmzZsbf399cc8015vPPP6/wDf3yb1K/+eablY6zadMmM2jQINOkSRPj4+NjWrRoYQYNGlRl/3LldxQo37y8vEzjxo1NTEyMiY+PN3v37q3wnNPvYPDzzz+bMWPGmIsvvtgEBASYBg0amE6dOpl58+aZkpISx/MOHjxo+vfvbwIDA40k06ZNmzOeW1V3SwgICDC7du0yvXv3Nn5+fqZJkybm/vvvd7pbgDHGZGdnm7vvvtuEhoaagIAAM2TIEHPw4MEKd0swxpipU6ea8PBwU69ePadjnj4Xxhhz/Phxc99995nmzZsbb29v06ZNGzN16lRTUFDg1E+SeeCBByqcV5s2bczo0aMrtJ9uxowZ5qKL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zjfCbR2XpzzZZNPIkSPdMp5ffT99+923BFwAAFAnEW7ruAIVyMhomIYpRCE1GitTmVpVsEqZmZmEWwAAUCcRbi0iRCEKV7inywAAAPCoWvFHHAAAAAB3INwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMgi3AAAAsAzCLQAAACyDcAsAAADLINwCAADAMjwabj/77DMNGTJE4eHhstlsevvtt532G2OUkJCg8PBw+fn5qXfv3tq7d69Tn8LCQk2YMEEhISEKCAjQ0KFDdeTIkfN4FgAAAKgtPBpuT548qc6dO2vRokWV7p81a5bmzp2rRYsWKSUlRWFhYerXr59yc3MdfeLj47V69WqtXLlSmzdvVl5engYPHqzS0tLzdRoAAACoJbw9efABAwZowIABle4zxmj+/PmaNm2ahg0bJklavny5QkND9eqrr+ree+9Vdna2li5dqldeeUV9+/aVJK1YsUKtWrXS+vXrdd111523cwEAAIDn1do1twcOHFBGRob69+/vaLPb7YqNjdWWLVskSampqSouLnbqEx4erqioKEefyhQWFionJ8dpAwAAQN1Xa8NtRkaGJCk0NNSpPTQ01LEvIyNDvr6+aty4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RUVJYu5qs927d6t79+4qKChQgwYNtHr1al166aWOfyyZs9pp5cqV2r59u1JSUirs4+etdurWrZtefvlldejQQT///LOefPJJ9ejRQ3v37rX8nBFuPcBmszk9NsZUaEPt4cp8Mafnz/jx47Vr1y5t3ry5wj7mrvbp2LGjdu7cqV9//VX/+c9/NHr0aG3atMmxnzmrfQ4fPqyHHnpIa9euVf369avsx9zVLgMGDHD8d3R0tLp376527dpp+fLl+tOf/iTJunPGsoTzKCQkRF5eXhX+j+fYsWMV/u8Jnlf+rdI/mq+wsDAVFRUpKyuryj44dyZMmKB3331XGzduVMuWLR3tzF3t5evrq/bt26tr165KSkpS586dtWDBAuasFktNTdWxY8cUExMjb29veXt7a9OmTXr66afl7e3teO2Zu9otICBA0dHR2rdvn+V/3gi355Gvr69iYmK0bt06p/Z169apR48eHqoKVYmIiFBYWJjTfBUVFWnTpk2O+YqJiZGPj49Tn/T0dO3Zs4c5PYeMMRo/frxWrVqlDRs2KCIiwmk/c1d3GGNUWFjInNVicXFx2r17t3bu3OnYunbtqjvuuEM7d+5U27Ztmbs6oLCwUN98842aN29u/Z83T3yL7UK2cuVK4+PjY5YuXWq+/vprEx8fbwICAszBgwc9XdoFKTc31+zYscPs2LHDSDJz5841O3bsMIcOHTLGGDNjxgwTFBRkVq1aZXbv3m1uv/1207x5c5OTk+MY47777jMtW7Y069evN9u3bzfXXnut6dy5sykpKfHUaVne/fffb4KCgsynn35q0tPTHdupU6ccfZi72mfq1Knms88+MwcOHDC7du0yjz76qKlXr55Zu3atMYY5q0t+f7cEY5i72mjSpEnm008/Nfv37zdbt241gwcPNoGBgY68YeU5I9x6wDPPPGPatGljfH19TZcuXRy3L8L5t3HjRiOpwjZ69GhjzG+3S5k+fboJCwszdrvd9OrVy+zevdtpjPz8fDN+/HjTpEkT4+fnZwYPHmzS0tI8cDYXjsrmTJJZtmyZow9zV/vcddddjt99TZs2NXFxcY5gawxzVpecHm6Zu9pn+PDhpnnz5sbHx8eEh4ebYcOGmb179zr2W3nObMYY45lrxgAAAIB7seYWAAAAlkG4BQAAgGUQbgEAAGAZhFsAAABYBuEWAAAAlkG4BQAAgGUQbgEAAGAZhFsAAABYBuEWAAAAlkG4BYA6YMyYMbLZbBW2H374wdOlAUCt4u3pAgAAZ+f666/XsmXLnNqaNm1arTFKS0tls9lUrx7XNgBYE7/dAKCOsNvtCgsLc9oWLFig6OhoBQQEqFWrVho3bpzy8vIcz0lOTlajRo30/vvv69JLL5XdbtehQ4dUVFSkKVOmqEWLFgoICFC3bt306aefeu7kAMBNCLcAUIfVq1dPTz/9tPbs2aPly5drw4YNmjJlilOfU6dOKSkpSS+++KL27t2rZs2a6c4779QXX3yhlStXateuXfrzn/+s66+/Xvv27fPQmQCAe9iMMcbTRQAA/tiYMWO0YsUK1a9f39E2YMAAvfnmm0793nzzTd1///3KzMyU9NuV2zvvvFM7d+5U586dJUk//vijIiMjdeTIEYWHhzue27dvX1111VVKTEw8D2cEAOcGa24BoI7o06ePnn32WcfjgIAAbdy4UYmJifr666+Vk5OjkpISFRQU6OTJkwoICJAk+fr6qlOnTo7nbd++XcYYdejQwWn8wsJCBQcHn5+TAYBzhHALAHVEQECA2rdv73h86NAhDRw4UPfdd5+eeOIJNWnSRJs3b9bYsWNVXFzs6Ofn5yebzeZ4XFZWJi8vL6WmpsrLy8vpGA0aNDj3JwIA5xDhFgDqqG3btqmkpERz5sxx3P3gjTfeOOPzrrjiCpWWlurYsWPq2bPnuS4TAM4rvlAGAHVUu3btVFJSooULF2r//v165ZVXtGTJkjM+r0OHDrrjjjs0atQorVq1SgcOHFBKSopmzpypDz/88DxUDgDnDuEWAOqoyy+/XHPnztXMmTMVFRWlf//730pKSjqr5y5btkyjRo3SpEmT1LFjRw0dOlT//e9/1apVq3NcNQCcW9wtAQAAAJbBlVsAAABYBuEWAAAAlkG4BQAAgGUQbgEAAGAZhFsAAABYBuEWAAAAlkG4BQAAgGUQbgEAAGAZhFsAAABYBuEWAAAAlkG4BQAAgGX8P3ms9eoq15fEAAAAAElFTkSuQmCC\n",
      "text/plain": [
       "<Figure size 800x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "plt.figure(figsize=(8,6))\n",
    "plt.hist(df['Fare'], bins=30, color='purple', edgecolor='black')\n",
    "plt.title('Fare Distribution among Titanic Passengers')\n",
    "plt.xlabel('Fare')\n",
    "plt.ylabel('Frequency')\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 21,
   "id": "ec9ccbbd",
   "metadata": {},
   "outputs": [],
   "source": [
    "Survived=df[\"Survived\"]\n",
    "Age=df[\"Age\"]\n",
    "Pclass=df[\"Pclass\"]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 31,
   "id": "0ad25688",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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VCAe7jz4+vXrXZaXLl2qGjVqKDU1VQ899JCMMVqwYIGmTp2qvn37SpKWLVum0NBQJSUlafTo0crOztbixYu1fPlydezYUZK0YsUKRUZG6sMPP1SXLl1u+XkBAICKo0Lds5OdnS1Jqlq1qiTp8OHDysjIUOfOna0ap9Op9u3ba/v27ZKk1NRUXbx40aUmIiJCjRo1smqulJeXp5ycHJcHAACwpwoTdowxmjBhgn75y1+qUaNGkqSMjAxJUmhoqEttaGiotS4jI0NeXl4KDg4useZKs2bNUlBQkPWIjIws79MBAAAVRIUJO0899ZT27Nmjt956q8g6h8PhsmyMKTJ2pavVTJkyRdnZ2dbj2LFjZW8cAABUaBUi7IwdO1br1q3Tpk2bVKtWLWs8LCxMkorM0GRmZlqzPWFhYcrPz1dWVlaJNVdyOp0KDAx0eQAAAHtya9gxxuipp57S6tWr9fHHHysqKsplfVRUlMLCwpSSkmKN5efna8uWLWrXrp0kqUWLFvL09HSpSU9P1759+6waAABw53Lru7F++9vfKikpSf/4xz8UEBBgzeAEBQXJx8dHDodD48eP18yZMxUdHa3o6GjNnDlTvr6+iouLs2pHjhypiRMnKiQkRFWrVtWkSZPUuHFj691ZAADgzuXWsLNo0SJJUkxMjMv40qVLNWzYMEnS5MmTlZubqzFjxigrK0utW7fWxo0bFRAQYNXPnz9fHh4e6t+/v3Jzc9WhQwclJiaqcuXKt+pUAABABeXWsGOMuWaNw+FQfHy84uPjS6zx9vZWQkKCEhISyrE7AABgBxXiBmUAAICbhbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbADAABsjbAD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X9cHzsH+CDu4Ll27dlV6erqOHDmiDz74QLGxsRo3bpx69OjhEgjCwsLK5S2f3t7eev7553Xx4sUb3te1pKWlqVu3bmrVqpW2bt2qvXv3KiEhQZ6enkXCXGnk5+dfV11QUBCf4A3b6tevn7788kstW7ZMBw8e1Lp16xQTE6NTp06VaX/GmOv6I8TLy0thYWF8BRAkEXZwnS7/RVazZk01b95czz33nP7xj3/ogw8+cJmVuHIm5d///rfuu+8+eXt7q2XLlvriiy+u63gDBw5Udna23nzzzavWLVq0SHfddZe8vLxUv359LV++3Fp3eRbo0UcflcPhKHFWKCUlReHh4ZozZ44aNWqku+66S127dtVf/vIXeXl5SZLi4+PVrFkzl+2unGm6PJ09a9YsRURE6J577tGUKVPUpk2bIsds0qSJpk+f7rKdJL3++uuqWbNmkZDVq1cvDR061Fp+99131aJFC3l7e6tevXqaMWPGLZmFAkrj9OnT2rZtm15++WXFxsaqTp06uv/++zVlyhR179692Mvap0+flsPh0ObNmyX973LUhg0b1LJlSzmdTi1evFgOh0NfffWVy/HmzZununXryhjjchkrOztbPj4+Wr9+vUv96tWr5efn979viP/+ez3++OMKDg5WSEiIevfurSNHjlj1BQUFmjBhgqpUqaKQkBBNnjz5mt+2jYqBsIMye/jhh9W0aVOtXr262PXnzp1Tjx49VL9+faWmpio+Pl6TJk26rn0HBgbqueee0wsvvKBz584VW7NmzRqNGzdOEydO1L59+zR69GgNHz5cmzZtkiTt2rVLkrR06VKlp6dby1cKCwtTenq6tm7del29Xc1HH32kAwcOKCUlRf/85z81aNAgffrppzp06JBVk5aWpr1792rQoEFFtv/Vr36lkydPWucgSVlZWdqwYYNVv2HDBg0ePFhPP/209u/fr9dff12JiYl66aWXbrh/oDz5+/vL399fa9euVV5e3g3ta/LkyZo1a5YOHDigxx57TC1atNDKlStdapKSkhQXF1dkNicoKEjdu3cvtr53797y9/fX+fPnFRsbK39/f23dulXbtm2Tv7+/unbtas3Szp07V0uWLNHixYu1bds2nTp1SmvWrLmh88ItYoBrGDp0qOndu3ex6x5//HHToEEDa1mSWbNmjTHGmNdff91UrVrVnDt3zlq/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nTpp2rRp2r59u4YNG6bp06erUqWffiT9/L6XixcvFrsPPz8/l+Xw8HDFxsZasztvvfVWibM60k83LD/22GNWfVJSkh5//HHrRufCwkK1aNFCu3fvdnkcPHhQcXFxZT95ALccYQeA2zVs2FDnzp1T9erVJUnp6enWup/frHwtgwYN0ttvv60dO3bo0KFDGjBgwDXr169fr7S0NG3atEmDBg2y1jVv3lzffPONatSoobvvvtvlERQUpKCgIIWHh1szSZJ06dIlpaamXne/AG4Nwg6AW+bHH3/Uww8/rBUrVmjPnj06fPiw/va3v2nOnDnq3bu3fHx81KZNG82ePVv79+/X1q1b9fzzz1/3/vv27aucnBz95je/UWxsrGrWrHnV+vbt2ys0NFSDBg1S3bp11aZNG2vdoEGDVK1aNfXu3VuffPKJDh8+rC1btmjcuHE6fvy4JGncuHGaPXu21qxZo6+++kpjxoy56R9aCKD0CDsAbhl/f3+1bt1a8+fP10MPPaRGjRrpD3/4g0aNGqWFCxdKkpYsWaKLFy+qZcuWGjdunF588cXr3n9gYKB69uypL7/80mWWpiQOh0MDBw4stt7X11dbt25V7dq11bdvXzVo0EAjRoxQbm6uAgMDJUkTJ07UE088oWHDhqlt27YKCAjQo48+WopnBMCt4DB8KAQAALAxZnYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICtEXYAAICt/X/RFggKZ4/MZQAAAABJRU5ErkJggg==\n",
      "text/plain": [
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "df['Survived'].value_counts().sort_index().plot(kind='bar', title='Survival Distribution', color=\"skyblue\",edgecolor=\"Black\")\n",
    "\n",
    "plt.xlabel('Survived')\n",
    "plt.ylabel('Count')\n",
    "\n",
    "plt.xticks(ticks=[0, 1], labels=['Did Not Survive', 'Survived'], rotation=0)\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 23,
   "id": "43c76d08",
   "metadata": {
    "scrolled": true
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "342 people survived\n"
     ]
    }
   ],
   "source": [
    "Survived=(df[\"Survived\"]).sum()\n",
    "print(f\"{Survived} people survived\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 24,
   "id": "38b1f734",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "549 people did not survived\n"
     ]
    }
   ],
   "source": [
    "did_not_survive=(df[\"Survived\"]==0).sum()\n",
    "print(f\"{did_not_survive} people did not survived\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 25,
   "id": "3f40cc93",
   "metadata": {},
   "outputs": [],
   "source": [
    "survivors = df[df['Survived'] == 1]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 32,
   "id": "389f03f2",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "survivors['Sex'].value_counts().plot(kind='bar', title='Survivors by Gender', edgecolor=\"Black\")\n",
    "plt.xticks(ticks=[0, 1], labels=['Female', 'Male'], rotation=0)\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 27,
   "id": "417b4771",
   "metadata": {},
   "outputs": [],
   "source": [
    "survivors=df[df[\"Survived\"]==1]\n",
    "gender_count=survivors[\"Sex\"].value_counts()\n",
    "male_survivor=gender_count.get(\"male\",0)\n",
    "female_survivor=gender_count.get(\"female\",0)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 28,
   "id": "fbfbd9f1",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Total 109 males survived\n",
      "Total 233 females survived\n"
     ]
    }
   ],
   "source": [
    "print(f\"Total {male_survivor} males survived\")\n",
    "print(f\"Total {female_survivor} females survived\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 33,
   "id": "286e07ae",
   "metadata": {},
   "outputs": [],
   "source": [
    "import jovian"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "080a566d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "application/javascript": [
       "window.require && require([\"base/js/namespace\"],function(Jupyter){Jupyter.notebook.save_checkpoint()})"
      ],
      "text/plain": [
       "<IPython.core.display.Javascript object>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "jovian.commit(project=\"Task 1 Data Science Internship Prodigy InfoTech\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "0da77f55",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "75ef5237",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "2a0328a9",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "fd7ae59a",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "af1022e6",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "a8d61127",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "6df325b3",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "dc4196b5",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "664445a2",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "517f099a",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "d40d6810",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "6dcb8195",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "833f8e64",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.10.9"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
