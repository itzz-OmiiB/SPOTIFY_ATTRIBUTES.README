# SPOTIFY_ATTRIBUTES.README
The basic and advance EDA on a dataset named SPOTIFY_ATTRIBUTES_DATASET.

EDA ON 'SPOTIFY SONGS ATTRIBUTES' DATASET 

Spotify is a digital music service that gives you access to millions of songs.
download_sp.png
The Spotify Song Attributes Dataset is a comprehensive collection of music tracks, encompassing various genres and artist names. This dataset provides valuable insights into the world of music, allowing enthusiasts, researchers, and data scientists to delve into the characteristics and nuances of each track.

The dataset includes key features such as danceability, energy, loudness, speechiness, acousticness, instrumentalness, liveness, valence, tempo, duration, and time signature. These attributes provide a holistic view of the songs, enabling users to analyze and interpret different aspects of their musical composition.
------------------------------------------------------------------------------------------------------------------------------------------------------------------
explore_data.png
                                                      [BASIC EDA]
#to print the first 5 entries of a dataset
​
data.head()
trackName	artistName	msPlayed	genre	danceability	energy	key	loudness	mode	speechiness	...	liveness	valence	tempo	type	id	uri	track_href	analysis_url	duration_ms	time_signature
0	"Honest"	Nico Collins	191772	NaN	0.476	0.799	4.0	-4.939	0.0	0.2120	...	0.2570	0.577	162.139	audio_features	7dTxqsaFGHOXwtzHINjfHv	spotify:track:7dTxqsaFGHOXwtzHINjfHv	https://api.spotify.com/v1/tracks/7dTxqsaFGHOX...	https://api.spotify.com/v1/audio-analysis/7dTx...	191948.0	4.0
1	"In The Hall Of The Mountain King" from Peer G...	London Symphony Orchestra	1806234	british orchestra	0.475	0.130	7.0	-17.719	1.0	0.0510	...	0.1010	0.122	112.241	audio_features	14Qcrx6Dfjvcj0H8oV8oUW	spotify:track:14Qcrx6Dfjvcj0H8oV8oUW	https://api.spotify.com/v1/tracks/14Qcrx6Dfjvc...	https://api.spotify.com/v1/audio-analysis/14Qc...	150827.0	4.0
2	#BrooklynBloodPop!	SyKo	145610	glitchcore	0.691	0.814	1.0	-3.788	0.0	0.1170	...	0.3660	0.509	132.012	audio_features	7K9Z3yFNNLv5kwTjQYGjnu	spotify:track:7K9Z3yFNNLv5kwTjQYGjnu	https://api.spotify.com/v1/tracks/7K9Z3yFNNLv5...	https://api.spotify.com/v1/audio-analysis/7K9Z...	145611.0	4.0
3	$10	Good Morning	25058	experimental pop	0.624	0.596	4.0	-9.804	1.0	0.0314	...	0.1190	0.896	120.969	audio_features	3koAwrM1RO0TGMeQJ3qt9J	spotify:track:3koAwrM1RO0TGMeQJ3qt9J	https://api.spotify.com/v1/tracks/3koAwrM1RO0T...	https://api.spotify.com/v1/audio-analysis/3koA...	89509.0	4.0
4	(I Just) Died In Your Arms	Cutting Crew	5504949	album rock	0.625	0.726	11.0	-11.402	0.0	0.0444	...	0.0625	0.507	124.945	audio_features	4ByEFOBuLXpCqvO1kw8Wdm	spotify:track:4ByEFOBuLXpCqvO1kw8Wdm	https://api.spotify.com/v1/tracks/4ByEFOBuLXpC...	https://api.spotify.com/v1/audio-analysis/4ByE...	280400.0	4.0
5 rows × 22 columns

#to print the last 5 entries of a dataset 
​
data.tail()
trackName	artistName	msPlayed	genre	danceability	energy	key	loudness	mode	speechiness	...	liveness	valence	tempo	type	id	uri	track_href	analysis_url	duration_ms	time_signature
10075	Younger with Time.	Ben Zaidi	668478	folk-pop	0.537	0.143	2.0	-16.992	1.0	0.0331	...	0.110	0.245	131.118	audio_features	6o8pM5reLgjd5i8gDY3Irt	spotify:track:6o8pM5reLgjd5i8gDY3Irt	https://api.spotify.com/v1/tracks/6o8pM5reLgjd...	https://api.spotify.com/v1/audio-analysis/6o8p...	222827.0	3.0
10076	Your Latest Trick - Remastered 1996	Dire Straits	304382	NaN	NaN	NaN	NaN	NaN	NaN	NaN	...	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN
10077	Your Love Is My Drug (8 Bit Slowed)	just valery	97600	sad lo-fi	0.282	0.158	6.0	-7.783	1.0	0.0311	...	0.474	0.248	65.152	audio_features	1EoThnDm6kQfB2idIfR30n	spotify:track:1EoThnDm6kQfB2idIfR30n	https://api.spotify.com/v1/tracks/1EoThnDm6kQf...	https://api.spotify.com/v1/audio-analysis/1EoT...	112582.0	4.0
10078	Your Power	Billie Eilish	988224	art pop	0.632	0.284	9.0	-14.025	0.0	0.0801	...	0.233	0.208	129.642	audio_features	042Sl6Mn83JHyLEqdK7uI0	spotify:track:042Sl6Mn83JHyLEqdK7uI0	https://api.spotify.com/v1/tracks/042Sl6Mn83JH...	https://api.spotify.com/v1/audio-analysis/042S...	245897.0	4.0
10079	Your Voice / Bethel, NY	Jaden	213626	pop rap	0.560	0.344	3.0	-12.283	1.0	0.0306	...	0.111	0.428	115.393	audio_features	3BcN2Pcy0kTG1zm8Tz9MsB	spotify:track:3BcN2Pcy0kTG1zm8Tz9MsB	https://api.spotify.com/v1/tracks/3BcN2Pcy0kTG...	https://api.spotify.com/v1/audio-analysis/3BcN...	213627.0	3.0
5 rows × 22 columns

#to print the size of the dataset
​
data.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 10080 entries, 0 to 10079
Data columns (total 22 columns):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 0   trackName         10080 non-null  object 
 1   artistName        10080 non-null  object 
 2   msPlayed          10080 non-null  int64  
 3   genre             8580 non-null   object 
 4   danceability      9530 non-null   float64
 5   energy            9530 non-null   float64
 6   key               9530 non-null   float64
 7   loudness          9530 non-null   float64
 8   mode              9530 non-null   float64
 9   speechiness       9530 non-null   float64
 10  acousticness      9530 non-null   float64
 11  instrumentalness  9530 non-null   float64
 12  liveness          9530 non-null   float64
 13  valence           9530 non-null   float64
 14  tempo             9530 non-null   float64
 15  type              9530 non-null   object 
 16  id                9530 non-null   object 
 17  uri               9530 non-null   object 
 18  track_href        9530 non-null   object 
 19  analysis_url      9530 non-null   object 
 20  duration_ms       9530 non-null   float64
 21  time_signature    9530 non-null   float64
dtypes: float64(13), int64(1), object(8)
memory usage: 1.7+ MB
#to get the number ofrows and columns 
​
data.shape
(10080, 22)

data.columns
#to print the list of columns 
​
data.columns
Index(['trackName', 'artistName', 'msPlayed', 'genre', 'danceability',
       'energy', 'key', 'loudness', 'mode', 'speechiness', 'acousticness',
       'instrumentalness', 'liveness', 'valence', 'tempo', 'type', 'id', 'uri',
       'track_href', 'analysis_url', 'duration_ms', 'time_signature'],
      dtype='object')
# Check for Duplicate values
​
data.duplicated()
0        False
1        False
2        False
3        False
4        False
         ...  
10075     True
10076     True
10077     True
10078     True
10079     True
Length: 10080, dtype: bool
#to print the statistical information about the data 
​
data.describe()
msPlayed	danceability	energy	key	loudness	mode	speechiness	acousticness	instrumentalness	liveness	valence	tempo	duration_ms	time_signature
count	1.008000e+04	9530.000000	9530.000000	9530.000000	9530.000000	9530.000000	9530.000000	9530.000000	9530.000000	9530.000000	9530.000000	9530.000000	9.530000e+03	9530.000000
mean	1.519657e+06	0.602469	0.563524	5.241973	-8.685077	0.612382	0.078468	0.362924	0.153215	0.174589	0.434113	119.374474	2.029311e+05	3.917524
std	5.317343e+06	0.157745	0.243548	3.570615	5.414814	0.487232	0.080101	0.334337	0.313132	0.130749	0.242761	28.993087	9.587253e+04	0.386189
min	0.000000e+00	0.000000	0.001080	0.000000	-42.044000	0.000000	0.000000	0.000002	0.000000	0.024900	0.000000	0.000000	1.002700e+04	0.000000
25%	1.367800e+05	0.509000	0.403000	2.000000	-10.189000	0.000000	0.036100	0.053800	0.000000	0.096200	0.237000	97.568000	1.616970e+05	4.000000
50%	2.662875e+05	0.623000	0.589000	5.000000	-7.218000	1.000000	0.047900	0.245000	0.000025	0.119000	0.409000	119.822000	1.942860e+05	4.000000
75%	1.186307e+06	0.714000	0.751000	8.000000	-5.336000	1.000000	0.081900	0.668000	0.027600	0.209000	0.614000	139.785000	2.295260e+05	4.000000
max	1.583671e+08	0.976000	0.999000	11.000000	3.010000	1.000000	0.966000	0.996000	0.993000	0.964000	0.986000	236.196000	4.581483e+06	5.000000
#to print the statistical information about data transforming the rows to columns 
​
data.describe().transpose()
count	mean	std	min	25%	50%	75%	max
msPlayed	10080.0	1.519657e+06	5.317343e+06	0.000000	136780.0000	266287.500000	1.186307e+06	1.583671e+08
danceability	9530.0	6.024687e-01	1.577448e-01	0.000000	0.5090	0.623000	7.140000e-01	9.760000e-01
energy	9530.0	5.635241e-01	2.435482e-01	0.001080	0.4030	0.589000	7.510000e-01	9.990000e-01
key	9530.0	5.241973e+00	3.570615e+00	0.000000	2.0000	5.000000	8.000000e+00	1.100000e+01
loudness	9530.0	-8.685077e+00	5.414814e+00	-42.044000	-10.1890	-7.218000	-5.336000e+00	3.010000e+00
mode	9530.0	6.123820e-01	4.872322e-01	0.000000	0.0000	1.000000	1.000000e+00	1.000000e+00
speechiness	9530.0	7.846768e-02	8.010093e-02	0.000000	0.0361	0.047900	8.190000e-02	9.660000e-01
acousticness	9530.0	3.629236e-01	3.343372e-01	0.000002	0.0538	0.245000	6.680000e-01	9.960000e-01
instrumentalness	9530.0	1.532150e-01	3.131324e-01	0.000000	0.0000	0.000025	2.760000e-02	9.930000e-01
liveness	9530.0	1.745891e-01	1.307488e-01	0.024900	0.0962	0.119000	2.090000e-01	9.640000e-01
valence	9530.0	4.341125e-01	2.427614e-01	0.000000	0.2370	0.409000	6.140000e-01	9.860000e-01
tempo	9530.0	1.193745e+02	2.899309e+01	0.000000	97.5680	119.822000	1.397850e+02	2.361960e+02
duration_ms	9530.0	2.029311e+05	9.587253e+04	10027.000000	161697.0000	194286.000000	2.295260e+05	4.581483e+06
time_signature	9530.0	3.917524e+00	3.861890e-01	0.000000	4.0000	4.000000	4.000000e+00	5.000000e+00
CLEANING THE DATA :-
#to Check for Null Value 
​
data.isnull().sum()
trackName           0
artistName          0
msPlayed            0
genre               0
danceability        0
energy              0
key                 0
loudness            0
mode                0
speechiness         0
acousticness        0
instrumentalness    0
liveness            0
valence             0
tempo               0
type                0
id                  0
uri                 0
track_href          0
analysis_url        0
duration_ms         0
time_signature      0
dtype: int64
#to Drop the rows with null values
​
data.dropna(inplace=True)
data
trackName	artistName	msPlayed	genre	danceability	energy	key	loudness	mode	speechiness	...	liveness	valence	tempo	type	id	uri	track_href	analysis_url	duration_ms	time_signature
1	"In The Hall Of The Mountain King" from Peer G...	London Symphony Orchestra	1806234	british orchestra	0.475	0.130	7.0	-17.719	1.0	0.0510	...	0.1010	0.122	112.241	audio_features	14Qcrx6Dfjvcj0H8oV8oUW	spotify:track:14Qcrx6Dfjvcj0H8oV8oUW	https://api.spotify.com/v1/tracks/14Qcrx6Dfjvc...	https://api.spotify.com/v1/audio-analysis/14Qc...	150827.0	4.0
2	#BrooklynBloodPop!	SyKo	145610	glitchcore	0.691	0.814	1.0	-3.788	0.0	0.1170	...	0.3660	0.509	132.012	audio_features	7K9Z3yFNNLv5kwTjQYGjnu	spotify:track:7K9Z3yFNNLv5kwTjQYGjnu	https://api.spotify.com/v1/tracks/7K9Z3yFNNLv5...	https://api.spotify.com/v1/audio-analysis/7K9Z...	145611.0	4.0
3	$10	Good Morning	25058	experimental pop	0.624	0.596	4.0	-9.804	1.0	0.0314	...	0.1190	0.896	120.969	audio_features	3koAwrM1RO0TGMeQJ3qt9J	spotify:track:3koAwrM1RO0TGMeQJ3qt9J	https://api.spotify.com/v1/tracks/3koAwrM1RO0T...	https://api.spotify.com/v1/audio-analysis/3koA...	89509.0	4.0
4	(I Just) Died In Your Arms	Cutting Crew	5504949	album rock	0.625	0.726	11.0	-11.402	0.0	0.0444	...	0.0625	0.507	124.945	audio_features	4ByEFOBuLXpCqvO1kw8Wdm	spotify:track:4ByEFOBuLXpCqvO1kw8Wdm	https://api.spotify.com/v1/tracks/4ByEFOBuLXpC...	https://api.spotify.com/v1/audio-analysis/4ByE...	280400.0	4.0
5	(L)only Child	salem ilese	2237969	alt z	0.645	0.611	8.0	-5.925	0.0	0.1370	...	0.2370	0.645	157.475	audio_features	22lJaG2yxlSjIwdUIddcFk	spotify:track:22lJaG2yxlSjIwdUIddcFk	https://api.spotify.com/v1/tracks/22lJaG2yxlSj...	https://api.spotify.com/v1/audio-analysis/22lJ...	144468.0	3.0
...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...
10074	Younger	Ruel	5272303	alt z	0.745	0.477	11.0	-7.706	0.0	0.0880	...	0.1200	0.454	136.055	audio_features	2qXicQG06oT0ijKBznpgQv	spotify:track:2qXicQG06oT0ijKBznpgQv	https://api.spotify.com/v1/tracks/2qXicQG06oT0...	https://api.spotify.com/v1/audio-analysis/2qXi...	222320.0	4.0
10075	Younger with Time.	Ben Zaidi	668478	folk-pop	0.537	0.143	2.0	-16.992	1.0	0.0331	...	0.1100	0.245	131.118	audio_features	6o8pM5reLgjd5i8gDY3Irt	spotify:track:6o8pM5reLgjd5i8gDY3Irt	https://api.spotify.com/v1/tracks/6o8pM5reLgjd...	https://api.spotify.com/v1/audio-analysis/6o8p...	222827.0	3.0
10077	Your Love Is My Drug (8 Bit Slowed)	just valery	97600	sad lo-fi	0.282	0.158	6.0	-7.783	1.0	0.0311	...	0.4740	0.248	65.152	audio_features	1EoThnDm6kQfB2idIfR30n	spotify:track:1EoThnDm6kQfB2idIfR30n	https://api.spotify.com/v1/tracks/1EoThnDm6kQf...	https://api.spotify.com/v1/audio-analysis/1EoT...	112582.0	4.0
10078	Your Power	Billie Eilish	988224	art pop	0.632	0.284	9.0	-14.025	0.0	0.0801	...	0.2330	0.208	129.642	audio_features	042Sl6Mn83JHyLEqdK7uI0	spotify:track:042Sl6Mn83JHyLEqdK7uI0	https://api.spotify.com/v1/tracks/042Sl6Mn83JH...	https://api.spotify.com/v1/audio-analysis/042S...	245897.0	4.0
10079	Your Voice / Bethel, NY	Jaden	213626	pop rap	0.560	0.344	3.0	-12.283	1.0	0.0306	...	0.1110	0.428	115.393	audio_features	3BcN2Pcy0kTG1zm8Tz9MsB	spotify:track:3BcN2Pcy0kTG1zm8Tz9MsB	https://api.spotify.com/v1/tracks/3BcN2Pcy0kTG...	https://api.spotify.com/v1/audio-analysis/3BcN...	213627.0	3.0
8580 rows × 22 columns

# to display only the trackName with its danceability
​
data.groupby('trackName')['danceability'].sum().round().sort_values(ascending=True)
trackName
Don't Worry Be Happy                                                               0.0
Suite No. 3 in D Major, BWV 1068: II. Air                                          0.0
Suite Bergamasque, L. 75: 3. Claire de lune (Arranged for Violin and Orchestra)    0.0
Haruka Kanata (Naruto)                                                             0.0
Disappeared town                                                                   0.0
                                                                                  ... 
Forever                                                                            5.0
Demons                                                                             5.0
Lost                                                                               5.0
Bloom                                                                              5.0
Heaven                                                                             6.0
Name: danceability, Length: 4113, dtype: float64
# to create a bar graph
​
df=pd.DataFrame(data.tail())
x=list(df.iloc[:,1])
y=list(df.iloc[:,6])
plt.bar(x,y,color='g')
plt.title('BAR GRAPH')
plt.xlabel('trackName')
plt.ylabel('energy')
​
plt.show()
​

OBSERVATIONS :-
-> First and the last five entries are displayed using head and tail.

-> The total number of attributes in this dataset is 22 and the total number of entries are 10080.

-> No duplicate column is found in the dataset.

-> Rows and Columns were transposed using transform() function.

-> After dropping the null values the number of entries reduces to 8580.

-> The above bar graph shows the energy of 5 particular tracks from the bottom of the dataset.
