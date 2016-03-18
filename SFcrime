{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "import numpy as np\n",
    "import pandas as pd\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "metadata": {
    "collapsed": false,
    "scrolled": true
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Untitled.ipynb       test.csv\r\n",
      "sampleSubmission.csv train.csv\r\n"
     ]
    }
   ],
   "source": [
    "!ls"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "df_train=pd.read_csv('train.csv')\n",
    "df_test=pd.read_csv('test.csv')\n",
    "df_sampleSub=pd.read_csv('sampleSubmission.csv')\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "metadata": {
    "collapsed": false,
    "scrolled": true
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Dates</th>\n",
       "      <th>Category</th>\n",
       "      <th>Descript</th>\n",
       "      <th>DayOfWeek</th>\n",
       "      <th>PdDistrict</th>\n",
       "      <th>Resolution</th>\n",
       "      <th>Address</th>\n",
       "      <th>X</th>\n",
       "      <th>Y</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>2015-05-13 23:53:00</td>\n",
       "      <td>WARRANTS</td>\n",
       "      <td>WARRANT ARREST</td>\n",
       "      <td>Wednesday</td>\n",
       "      <td>NORTHERN</td>\n",
       "      <td>ARREST, BOOKED</td>\n",
       "      <td>OAK ST / LAGUNA ST</td>\n",
       "      <td>-122.425892</td>\n",
       "      <td>37.774599</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2015-05-13 23:53:00</td>\n",
       "      <td>OTHER OFFENSES</td>\n",
       "      <td>TRAFFIC VIOLATION ARREST</td>\n",
       "      <td>Wednesday</td>\n",
       "      <td>NORTHERN</td>\n",
       "      <td>ARREST, BOOKED</td>\n",
       "      <td>OAK ST / LAGUNA ST</td>\n",
       "      <td>-122.425892</td>\n",
       "      <td>37.774599</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>2015-05-13 23:33:00</td>\n",
       "      <td>OTHER OFFENSES</td>\n",
       "      <td>TRAFFIC VIOLATION ARREST</td>\n",
       "      <td>Wednesday</td>\n",
       "      <td>NORTHERN</td>\n",
       "      <td>ARREST, BOOKED</td>\n",
       "      <td>VANNESS AV / GREENWICH ST</td>\n",
       "      <td>-122.424363</td>\n",
       "      <td>37.800414</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                Dates        Category                  Descript  DayOfWeek  \\\n",
       "0 2015-05-13 23:53:00        WARRANTS            WARRANT ARREST  Wednesday   \n",
       "1 2015-05-13 23:53:00  OTHER OFFENSES  TRAFFIC VIOLATION ARREST  Wednesday   \n",
       "2 2015-05-13 23:33:00  OTHER OFFENSES  TRAFFIC VIOLATION ARREST  Wednesday   \n",
       "\n",
       "  PdDistrict      Resolution                    Address           X          Y  \n",
       "0   NORTHERN  ARREST, BOOKED         OAK ST / LAGUNA ST -122.425892  37.774599  \n",
       "1   NORTHERN  ARREST, BOOKED         OAK ST / LAGUNA ST -122.425892  37.774599  \n",
       "2   NORTHERN  ARREST, BOOKED  VANNESS AV / GREENWICH ST -122.424363  37.800414  "
      ]
     },
     "execution_count": 11,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_train.shape\n",
    "df_train.head(3)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "df_train['Dates']=pd.to_datetime(df_train['Dates'])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>X</th>\n",
       "      <th>Y</th>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>PdDistrict</th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>BAYVIEW</th>\n",
       "      <td>-122.393359</td>\n",
       "      <td>37.742516</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>CENTRAL</th>\n",
       "      <td>-122.409507</td>\n",
       "      <td>37.798740</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>INGLESIDE</th>\n",
       "      <td>-122.428734</td>\n",
       "      <td>37.729195</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>MISSION</th>\n",
       "      <td>-122.419393</td>\n",
       "      <td>37.760396</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>NORTHERN</th>\n",
       "      <td>-122.426428</td>\n",
       "      <td>37.792330</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>PARK</th>\n",
       "      <td>-122.445369</td>\n",
       "      <td>37.772418</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>RICHMOND</th>\n",
       "      <td>-122.469782</td>\n",
       "      <td>37.788294</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>SOUTHERN</th>\n",
       "      <td>-122.405185</td>\n",
       "      <td>37.782573</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>TARAVAL</th>\n",
       "      <td>-122.477214</td>\n",
       "      <td>37.740736</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>TENDERLOIN</th>\n",
       "      <td>-122.412152</td>\n",
       "      <td>37.793377</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                     X          Y\n",
       "PdDistrict                       \n",
       "BAYVIEW    -122.393359  37.742516\n",
       "CENTRAL    -122.409507  37.798740\n",
       "INGLESIDE  -122.428734  37.729195\n",
       "MISSION    -122.419393  37.760396\n",
       "NORTHERN   -122.426428  37.792330\n",
       "PARK       -122.445369  37.772418\n",
       "RICHMOND   -122.469782  37.788294\n",
       "SOUTHERN   -122.405185  37.782573\n",
       "TARAVAL    -122.477214  37.740736\n",
       "TENDERLOIN -122.412152  37.793377"
      ]
     },
     "execution_count": 12,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_train.groupby('PdDistrict').mean()[['X','Y']]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "LARCENY/THEFT                  174900\n",
       "OTHER OFFENSES                 126182\n",
       "NON-CRIMINAL                    92304\n",
       "ASSAULT                         76876\n",
       "DRUG/NARCOTIC                   53971\n",
       "VEHICLE THEFT                   53781\n",
       "VANDALISM                       44725\n",
       "WARRANTS                        42214\n",
       "BURGLARY                        36755\n",
       "SUSPICIOUS OCC                  31414\n",
       "MISSING PERSON                  25989\n",
       "ROBBERY                         23000\n",
       "FRAUD                           16679\n",
       "FORGERY/COUNTERFEITING          10609\n",
       "SECONDARY CODES                  9985\n",
       "WEAPON LAWS                      8555\n",
       "PROSTITUTION                     7484\n",
       "TRESPASS                         7326\n",
       "STOLEN PROPERTY                  4540\n",
       "SEX OFFENSES FORCIBLE            4388\n",
       "DISORDERLY CONDUCT               4320\n",
       "DRUNKENNESS                      4280\n",
       "RECOVERED VEHICLE                3138\n",
       "KIDNAPPING                       2341\n",
       "DRIVING UNDER THE INFLUENCE      2268\n",
       "RUNAWAY                          1946\n",
       "LIQUOR LAWS                      1903\n",
       "ARSON                            1513\n",
       "LOITERING                        1225\n",
       "EMBEZZLEMENT                     1166\n",
       "SUICIDE                           508\n",
       "FAMILY OFFENSES                   491\n",
       "BAD CHECKS                        406\n",
       "BRIBERY                           289\n",
       "EXTORTION                         256\n",
       "SEX OFFENSES NON FORCIBLE         148\n",
       "GAMBLING                          146\n",
       "PORNOGRAPHY/OBSCENE MAT            22\n",
       "TREA                                6\n",
       "Name: Category, dtype: int64"
      ]
     },
     "execution_count": 13,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_train.Category.value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "u'0.17.1'"
      ]
     },
     "execution_count": 14,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "pd.__version__"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Id</th>\n",
       "      <th>ARSON</th>\n",
       "      <th>ASSAULT</th>\n",
       "      <th>BAD CHECKS</th>\n",
       "      <th>BRIBERY</th>\n",
       "      <th>BURGLARY</th>\n",
       "      <th>DISORDERLY CONDUCT</th>\n",
       "      <th>DRIVING UNDER THE INFLUENCE</th>\n",
       "      <th>DRUG/NARCOTIC</th>\n",
       "      <th>DRUNKENNESS</th>\n",
       "      <th>...</th>\n",
       "      <th>SEX OFFENSES NON FORCIBLE</th>\n",
       "      <th>STOLEN PROPERTY</th>\n",
       "      <th>SUICIDE</th>\n",
       "      <th>SUSPICIOUS OCC</th>\n",
       "      <th>TREA</th>\n",
       "      <th>TRESPASS</th>\n",
       "      <th>VANDALISM</th>\n",
       "      <th>VEHICLE THEFT</th>\n",
       "      <th>WARRANTS</th>\n",
       "      <th>WEAPON LAWS</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>...</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>...</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>2</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>...</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>3 rows × 40 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "   Id  ARSON  ASSAULT  BAD CHECKS  BRIBERY  BURGLARY  DISORDERLY CONDUCT  \\\n",
       "0   0      0        0           0        0         0                   0   \n",
       "1   1      0        0           0        0         0                   0   \n",
       "2   2      0        0           0        0         0                   0   \n",
       "\n",
       "   DRIVING UNDER THE INFLUENCE  DRUG/NARCOTIC  DRUNKENNESS     ...       \\\n",
       "0                            0              0            0     ...        \n",
       "1                            0              0            0     ...        \n",
       "2                            0              0            0     ...        \n",
       "\n",
       "   SEX OFFENSES NON FORCIBLE  STOLEN PROPERTY  SUICIDE  SUSPICIOUS OCC  TREA  \\\n",
       "0                          0                0        0               0     0   \n",
       "1                          0                0        0               0     0   \n",
       "2                          0                0        0               0     0   \n",
       "\n",
       "   TRESPASS  VANDALISM  VEHICLE THEFT  WARRANTS  WEAPON LAWS  \n",
       "0         0          0              0         1            0  \n",
       "1         0          0              0         1            0  \n",
       "2         0          0              0         1            0  \n",
       "\n",
       "[3 rows x 40 columns]"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_sampleSub.head(3)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Id            0\n",
       "Dates         0\n",
       "DayOfWeek     0\n",
       "PdDistrict    0\n",
       "Address       0\n",
       "X             0\n",
       "Y             0\n",
       "dtype: int64"
      ]
     },
     "execution_count": 17,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_test.isnull().sum()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 18,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "SOUTHERN      157182\n",
       "MISSION       119908\n",
       "NORTHERN      105296\n",
       "BAYVIEW        89431\n",
       "CENTRAL        85460\n",
       "TENDERLOIN     81809\n",
       "INGLESIDE      78845\n",
       "TARAVAL        65596\n",
       "PARK           49313\n",
       "RICHMOND       45209\n",
       "Name: PdDistrict, dtype: int64"
      ]
     },
     "execution_count": 18,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_train.PdDistrict.value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 19,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "NONE                                      526790\n",
       "ARREST, BOOKED                            206403\n",
       "ARREST, CITED                              77004\n",
       "LOCATED                                    17101\n",
       "PSYCHOPATHIC CASE                          14534\n",
       "UNFOUNDED                                   9585\n",
       "JUVENILE BOOKED                             5564\n",
       "COMPLAINANT REFUSES TO PROSECUTE            3976\n",
       "DISTRICT ATTORNEY REFUSES TO PROSECUTE      3934\n",
       "NOT PROSECUTED                              3714\n",
       "JUVENILE CITED                              3332\n",
       "PROSECUTED BY OUTSIDE AGENCY                2504\n",
       "EXCEPTIONAL CLEARANCE                       1530\n",
       "JUVENILE ADMONISHED                         1455\n",
       "JUVENILE DIVERTED                            355\n",
       "CLEARED-CONTACT JUVENILE FOR MORE INFO       217\n",
       "PROSECUTED FOR LESSER OFFENSE                 51\n",
       "Name: Resolution, dtype: int64"
      ]
     },
     "execution_count": 19,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_train.Resolution.value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 21,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Dates</th>\n",
       "      <th>Category</th>\n",
       "      <th>Descript</th>\n",
       "      <th>DayOfWeek</th>\n",
       "      <th>PdDistrict</th>\n",
       "      <th>Resolution</th>\n",
       "      <th>Address</th>\n",
       "      <th>X</th>\n",
       "      <th>Y</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>844995</th>\n",
       "      <td>2003-06-11 08:49:00</td>\n",
       "      <td>OTHER OFFENSES</td>\n",
       "      <td>DRIVERS LICENSE, SUSPENDED OR REVOKED</td>\n",
       "      <td>Wednesday</td>\n",
       "      <td>INGLESIDE</td>\n",
       "      <td>ARREST, CITED</td>\n",
       "      <td>JAMES LICK FREEWAY HY / CESAR CHAVEZ ST</td>\n",
       "      <td>-120.5</td>\n",
       "      <td>90</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>845842</th>\n",
       "      <td>2003-06-09 09:25:00</td>\n",
       "      <td>OTHER OFFENSES</td>\n",
       "      <td>DRIVERS LICENSE, SUSPENDED OR REVOKED</td>\n",
       "      <td>Monday</td>\n",
       "      <td>INGLESIDE</td>\n",
       "      <td>ARREST, CITED</td>\n",
       "      <td>JAMES LICK FREEWAY HY / CESAR CHAVEZ ST</td>\n",
       "      <td>-120.5</td>\n",
       "      <td>90</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>852880</th>\n",
       "      <td>2003-05-02 01:00:00</td>\n",
       "      <td>SEX OFFENSES FORCIBLE</td>\n",
       "      <td>FORCIBLE RAPE, BODILY FORCE</td>\n",
       "      <td>Friday</td>\n",
       "      <td>SOUTHERN</td>\n",
       "      <td>COMPLAINANT REFUSES TO PROSECUTE</td>\n",
       "      <td>3RD ST / JAMES LICK FREEWAY HY</td>\n",
       "      <td>-120.5</td>\n",
       "      <td>90</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>857248</th>\n",
       "      <td>2003-04-14 16:30:00</td>\n",
       "      <td>ROBBERY</td>\n",
       "      <td>ROBBERY ON THE STREET, STRONGARM</td>\n",
       "      <td>Monday</td>\n",
       "      <td>BAYVIEW</td>\n",
       "      <td>COMPLAINANT REFUSES TO PROSECUTE</td>\n",
       "      <td>GILMAN AV / FITCH ST</td>\n",
       "      <td>-120.5</td>\n",
       "      <td>90</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>871198</th>\n",
       "      <td>2003-02-05 12:00:00</td>\n",
       "      <td>LARCENY/THEFT</td>\n",
       "      <td>PETTY THEFT FROM LOCKED AUTO</td>\n",
       "      <td>Wednesday</td>\n",
       "      <td>SOUTHERN</td>\n",
       "      <td>NONE</td>\n",
       "      <td>SPEAR ST / THE EMBARCADERO SOUTH ST</td>\n",
       "      <td>-120.5</td>\n",
       "      <td>90</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                     Dates               Category  \\\n",
       "844995 2003-06-11 08:49:00         OTHER OFFENSES   \n",
       "845842 2003-06-09 09:25:00         OTHER OFFENSES   \n",
       "852880 2003-05-02 01:00:00  SEX OFFENSES FORCIBLE   \n",
       "857248 2003-04-14 16:30:00                ROBBERY   \n",
       "871198 2003-02-05 12:00:00          LARCENY/THEFT   \n",
       "\n",
       "                                     Descript  DayOfWeek PdDistrict  \\\n",
       "844995  DRIVERS LICENSE, SUSPENDED OR REVOKED  Wednesday  INGLESIDE   \n",
       "845842  DRIVERS LICENSE, SUSPENDED OR REVOKED     Monday  INGLESIDE   \n",
       "852880            FORCIBLE RAPE, BODILY FORCE     Friday   SOUTHERN   \n",
       "857248       ROBBERY ON THE STREET, STRONGARM     Monday    BAYVIEW   \n",
       "871198           PETTY THEFT FROM LOCKED AUTO  Wednesday   SOUTHERN   \n",
       "\n",
       "                              Resolution  \\\n",
       "844995                     ARREST, CITED   \n",
       "845842                     ARREST, CITED   \n",
       "852880  COMPLAINANT REFUSES TO PROSECUTE   \n",
       "857248  COMPLAINANT REFUSES TO PROSECUTE   \n",
       "871198                              NONE   \n",
       "\n",
       "                                        Address      X   Y  \n",
       "844995  JAMES LICK FREEWAY HY / CESAR CHAVEZ ST -120.5  90  \n",
       "845842  JAMES LICK FREEWAY HY / CESAR CHAVEZ ST -120.5  90  \n",
       "852880           3RD ST / JAMES LICK FREEWAY HY -120.5  90  \n",
       "857248                     GILMAN AV / FITCH ST -120.5  90  \n",
       "871198      SPEAR ST / THE EMBARCADERO SOUTH ST -120.5  90  "
      ]
     },
     "execution_count": 21,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df_train[(df_train.Y>45)|(df_train.Y<35)].tail()"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 2",
   "language": "python",
   "name": "python2"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 2
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython2",
   "version": "2.7.10"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 0
}
