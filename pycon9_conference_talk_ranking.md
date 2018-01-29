
<div> 
    <img src='https://raw.githubusercontent.com/ernestoarbitrio/pyconit-community-voting/pycon9/logos/pycon9.png' width='50%' />
</div>


```python
import pandas as pd
import numpy as np
```

<a name="absolute_rank"></a>
# Community Voting Results

### Absolute Ranking


```python
rankings = pd.read_csv('./ranking.txt', sep='~', skiprows=1, header=0)
rankings.drop('TID', axis=1, inplace=True)
#rankings.drop('Idx', axis=1, inplace=True)

union_jack = '\U0001F1EC\U0001F1E7'
tricolore = '\U0001F1EE\U0001F1F9'

rankings.Gender = rankings.Gender.apply(lambda g: '+'.join('\U0001f469\u200d\U0001f4bb' if l=='female' else '\U0001f468\u200d\U0001f4bb' 
                                         for l in g.split(',')))
rankings.Lang = rankings.Lang.apply(lambda l: union_jack if l=='en' else tricolore)
pd.set_option('display.max_rows', rankings.index.size)
pd.set_option('display.max_colwidth', 200)
rankings
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Type</th>
      <th>Duration</th>
      <th>Title</th>
      <th>Track</th>
      <th>Level</th>
      <th>Lang</th>
      <th>Speakers</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Talk</td>
      <td>45</td>
      <td>How to use Web-Sockets in Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Anton Caceres</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Talk</td>
      <td>45</td>
      <td>Testing, then once you got there?</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Alessandro Molina</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Training</td>
      <td>240</td>
      <td>Modern time series analysis in Python</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Aileen Nielsen</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Talk</td>
      <td>60</td>
      <td>Resurrecting the dead with deep learning</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Aditthya Ramakrishnan</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Talk</td>
      <td>45</td>
      <td>Thinking functionally: Introduction to Functional Programming in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alisha Aneja</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Talk</td>
      <td>45</td>
      <td>Writing and deploying serverless Python applications</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Cesar Cardenas Desales</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Talk</td>
      <td>60</td>
      <td>Bokeh: Using python for interactive data visualization</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Ernesto Arbitrio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scaling your Data infrastructure</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Christian Barra</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Talk</td>
      <td>45</td>
      <td>TDD nella pratica: tips&amp;tricks</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Antonio Cuni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Talk</td>
      <td>45</td>
      <td>The practice of TDD: tips&amp;tricks</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Antonio Cuni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Talk</td>
      <td>60</td>
      <td>How to make your model happy again</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alessia Marcolini</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Talk</td>
      <td>60</td>
      <td>Databases for Data Science</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alexander Hendorf</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Talk</td>
      <td>45</td>
      <td>Everyday security issues and how to avoid them</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Christian Heimes</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Talk</td>
      <td>45</td>
      <td>Practical Machine Learning with Python and scikit-learn</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Andrea Grandi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Training</td>
      <td>240</td>
      <td>Algorithmic fairness in data discovery, processing, and prediction: a full tutorial</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Aileen Nielsen</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Talk</td>
      <td>60</td>
      <td>Reproducibility, and Selection Bias in Learning: when just Cross Validation is not enough!</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Valerio Maggio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Training</td>
      <td>240</td>
      <td>PyTorch from the ground up</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Daniele Ciriello,Luca Antiga</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Talk</td>
      <td>45</td>
      <td>Data Visualization in Mixed Reality with Python</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Anna Nicanorova</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Talk</td>
      <td>60</td>
      <td>Deep Learning from zero to hero</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Gianluca Carucci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scientific computing con PyPy</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Antonio Cuni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Talk</td>
      <td>45</td>
      <td>Getting an Edge: Network Analysis in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alon Nir</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Talk</td>
      <td>60</td>
      <td>Bokeh: Usare python per creare grafici interattivi</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Ernesto Arbitrio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pandas Tips and Tricks - Getting the Data to Confess with Python</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alon Nir</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Talk</td>
      <td>45</td>
      <td>In git we trust</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Simone Basso</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pachettizzare applicazioni python in un singolo file binario</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Gabriele Franch</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Talk</td>
      <td>90</td>
      <td>Image Generation with Tensorflow (GANs)</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Cenk Bircanoğlu</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Training</td>
      <td>240</td>
      <td>Real-time transcription and sentiment analysis of audio streams; on the phone and in the browser</td>
      <td>PyBusiness</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Aaron Bassett</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Talk</td>
      <td>45</td>
      <td>Il rasoio dei generatori di Python per semplificare il codice e ridurre l'uso di memoria</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Brunato</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python 3. Fight for non-blocking IO</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Denis Makogon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Talk</td>
      <td>45</td>
      <td>Creating Part Of Speech Tagger with Hidden Markov Model and Viterbi Algorithm</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Albertus Kelvin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Talk</td>
      <td>45</td>
      <td>Source Code Generation Based On User Intention Using LSTM Networks</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Albertus Kelvin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Talk</td>
      <td>45</td>
      <td>Property-based testing with Hypothesis</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Aniello Barletta</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Talk</td>
      <td>45</td>
      <td>Automatic Multiple-Choice Question Generator by Using Machine Learning</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Albertus Kelvin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Talk</td>
      <td>60</td>
      <td>Building chatbots using Facebook Messenger API and Python-NLP packages</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Akilesh Lakshminarayanan</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Talk</td>
      <td>45</td>
      <td>Reproducibility in Data Science</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Andrea Gigli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Talk</td>
      <td>90</td>
      <td>Pygame torna a scuola</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Maurizio Boscaini,Alessandro Marchioro</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Training</td>
      <td>240</td>
      <td>Learning to fetch data for fun and profit</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Arsh .</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Talk</td>
      <td>45</td>
      <td>Costruire applicazioni web realtime con Django</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Iacopo Spalletti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Talk</td>
      <td>45</td>
      <td>PyTest e Page Object: come scrivere facilmente test UI mantenibili</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Damiano Iannelli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Talk</td>
      <td>45</td>
      <td>PyTest and Page Object: how to easily write maintainable UI tests</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Damiano Iannelli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Talk</td>
      <td>45</td>
      <td>When your wetware has too many threads - Tips from an ADHDer on how to improve your focus</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Aaron Bassett</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Talk</td>
      <td>45</td>
      <td>Packaging binary stand alone applications in python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Gabriele Franch</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Talk</td>
      <td>60</td>
      <td>What's going on there? Understanding cities with location data.</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Gianni Barlacchi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Talk</td>
      <td>45</td>
      <td>GraphQL in Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Patrick Guido Arminio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Talk</td>
      <td>60</td>
      <td>Python on Web Browsers</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Roberto Alsina</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Talk</td>
      <td>45</td>
      <td>The forgotten Coders - The History of Women Coders</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alicia Carr</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Talk</td>
      <td>90</td>
      <td>Computer Vision and Machine Learning for Self-Driving Cars with OpenCV and Keras</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Lou Marvin Caraig</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Talk</td>
      <td>60</td>
      <td>Applying serverless architecture pattern to distributed data processing</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Denis Makogon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Talk</td>
      <td>45</td>
      <td>Serverless SQL queries from Python with AWS Athena...or power to Data Scientists!</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Daniela Scardi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Talk</td>
      <td>45</td>
      <td>GraphQL in Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Patrick Guido Arminio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Talk</td>
      <td>60</td>
      <td>Una zuppa di Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Alessandro Re</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>51</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monitoraggio di applicazioni Django con Prometheus (e Grafana)</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Setti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Training</td>
      <td>240</td>
      <td>Crea da zero un clone di Bitcoin in Python</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Rigel Di Scala</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>53</th>
      <td>Talk</td>
      <td>45</td>
      <td>Using Python to bring democracy to the A.I. age</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Felipe Cabral</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Training</td>
      <td>240</td>
      <td>Codice più efficiente? Restate cythonizzati</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Training</td>
      <td>240</td>
      <td>Building a Data Science pipeline</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Manoj Pandey</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Talk</td>
      <td>45</td>
      <td>Hacking Your Way Into Machine Learning</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Laksh Arora</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Talk</td>
      <td>45</td>
      <td>House Price Prediction with Distributed Keras</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Cenk Bircanoğlu</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Talk</td>
      <td>60</td>
      <td>A primer on the Ethereum Blockchain and Smart Contracts using Python and Serpent</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Stefano Fioravanzo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Talk</td>
      <td>45</td>
      <td>SSLError, now what?</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Christian Heimes</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>60</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monitoring Django applications with Prometheus (and Grafana)</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Davide Setti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Talk</td>
      <td>45</td>
      <td>IoT con Python: si può fare! dall'ESP8266 alla casa domotica</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Lelio Campanile</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Training</td>
      <td>240</td>
      <td>TDD in Python with pytest</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Talk</td>
      <td>45</td>
      <td>PostgreSQL &amp; Python: La coppia perfetta.</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Giulio Calacoci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Talk</td>
      <td>60</td>
      <td>Continuous Delivery starts at your Development Environment</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>65</th>
      <td>Talk</td>
      <td>60</td>
      <td>PaaS per tutti i gusti: CI/CD sotto controllo con Kubernetes e Dokku</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Claudio Mignanti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>66</th>
      <td>Talk</td>
      <td>45</td>
      <td>Managed ML in the Cloud: Data Science The Right Way</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alex Casalboni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>67</th>
      <td>Talk</td>
      <td>60</td>
      <td>Sports performance evaluation: from cognitive mechanisms to data-driven algorithms</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Luca Pappalardo,Paolo Cintia</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>68</th>
      <td>Talk</td>
      <td>45</td>
      <td>How to approach a Machine Learning Problem ? : YouTube Like Count Predictor</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Ayush Kumar Singh</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>69</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python e Elasticsearch:  dal Text Search a NLP e oltre</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Dario Balinzo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>70</th>
      <td>Talk</td>
      <td>45</td>
      <td>Visualising the world of competitive programming with Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Anuj Menta</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>71</th>
      <td>Talk</td>
      <td>45</td>
      <td>Go and Debug your Python!</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Stéphane Wirtel</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>72</th>
      <td>Talk</td>
      <td>60</td>
      <td>Vim your Python, Python your Vim</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Miroslav Šedivý</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Talk</td>
      <td>45</td>
      <td>Choose Your Own Adventure for Client Web Services with Graphql</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>David Anderson</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>74</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lies, damned lies, and statistics</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marco Bonzanini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>75</th>
      <td>Talk</td>
      <td>45</td>
      <td>Insegnare la matematica con Python: percorsi suggeriti per le Scuole Superiori</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Poggiali</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>76</th>
      <td>Talk</td>
      <td>45</td>
      <td>Networks in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>77</th>
      <td>Talk</td>
      <td>45</td>
      <td>The Spectre and the Meltdown: a modern fable</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Thierry Carrez</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>78</th>
      <td>Talk</td>
      <td>60</td>
      <td>A journey into the Chinese language with Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Ezio Melotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>79</th>
      <td>Talk</td>
      <td>45</td>
      <td>Evolution or stagnation programming languages</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Daniele Esposti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>80</th>
      <td>Talk</td>
      <td>45</td>
      <td>Understanding Natural Language with Word Vectors</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marco Bonzanini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>81</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monads and functional python</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Przemyslaw Pietrzak</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>82</th>
      <td>Talk</td>
      <td>60</td>
      <td>Python for testing</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Davide Moro</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>83</th>
      <td>Training</td>
      <td>240</td>
      <td>Build your own chatbot using the Facebook Messenger API and Python-NLP packages</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Akilesh Lakshminarayanan</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>84</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python &amp; Industry 4.0: a real world case</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Gianluca Emireni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>85</th>
      <td>Talk</td>
      <td>45</td>
      <td>Query SQL  e serverless da Python con AWS Athena...o meglio potere ai Data Scientist!</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Daniela Scardi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>86</th>
      <td>Talk</td>
      <td>60</td>
      <td>Dalla User Story al test automatico in Django: un percorso step by step per dormire sonni tranquilli</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Filippo Morelli,Gabriele Giaccari</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>87</th>
      <td>Talk</td>
      <td>45</td>
      <td>Location, location, location:  Data Visualisation and Analysis of Geospatial data in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Michele Ferretti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>88</th>
      <td>Talk</td>
      <td>60</td>
      <td>Recent advancements in NLP and Deep Learning: A Quant's Perspective</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Umit Mert Cakmak</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>89</th>
      <td>Talk</td>
      <td>45</td>
      <td>Evoluzione o stagnazione dei linguaggi di programmazione</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Daniele Esposti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>90</th>
      <td>Talk</td>
      <td>45</td>
      <td>Testing Python Security</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Jose Manuel Ortega</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>91</th>
      <td>Training</td>
      <td>240</td>
      <td>Build your own CV (as in Computer Vision) with Keras and Tensorflow.</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Rodolfo Bonnin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>92</th>
      <td>Talk</td>
      <td>45</td>
      <td>Unveiling the potential of graph databases with Python and Neo4j</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>93</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scoprire le potenzialità del database a grafo con Python e Neo4j</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>94</th>
      <td>Talk</td>
      <td>45</td>
      <td>Don't reinvent the wheel: integrating command-line tools into your Python project</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Michael Penkov</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>95</th>
      <td>Talk</td>
      <td>45</td>
      <td>Test di applicazioni Django riutilizzabili</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Iacopo Spalletti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>96</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scientific computing using Cython: Best of both Worlds!</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Simmi LNU</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>97</th>
      <td>Training</td>
      <td>240</td>
      <td>DATA PLUMBING 101: Building Data Pipelines for fun and profit</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Michele De Simoni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>98</th>
      <td>Talk</td>
      <td>45</td>
      <td>Integration tests ready to use with pytest-play</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Serena Martinetti</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>99</th>
      <td>Talk</td>
      <td>60</td>
      <td>Sentiment analysis of emotions via word embeddings: from data collection &amp; analysis to visualization</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Mirko Mazzoleni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>100</th>
      <td>Talk</td>
      <td>90</td>
      <td>Clean architectures in Python: why, what, how</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>101</th>
      <td>Talk</td>
      <td>45</td>
      <td>Celery with Python: The way to distribute and schedule millions of processes</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Kushagra Bhargava</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>102</th>
      <td>Talk</td>
      <td>60</td>
      <td>Analisi statica e Python</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Leonardo Cecchi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>103</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lessons learned while analysing 30 million news articles</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leif Uwe Vogelsang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>104</th>
      <td>Talk</td>
      <td>60</td>
      <td>Refactoring con i test in Python: un esempio pratico</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>105</th>
      <td>Talk</td>
      <td>60</td>
      <td>Google loves Python 2.0</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Simone Dalla</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>106</th>
      <td>Talk</td>
      <td>60</td>
      <td>Deploy di un'applicazione Python con Kubernetes</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Marco Santamaria</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>107</th>
      <td>Talk</td>
      <td>60</td>
      <td>How I teach Agile at school using Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>108</th>
      <td>Talk</td>
      <td>60</td>
      <td>Creare un servizio rest asincrono con Sanic in TDD</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Lorenzo Mele</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>109</th>
      <td>Talk</td>
      <td>45</td>
      <td>From the language of the tweet to immigration in cities: Python and its "Language Detectors"</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>110</th>
      <td>Talk</td>
      <td>45</td>
      <td>A software robotics platform for enhancing human-robot interaction</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Enrico Carbognani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>111</th>
      <td>Talk</td>
      <td>60</td>
      <td>Deep Learning in Computer Vision: state of the art techniques and applications in industry</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Rocco Michele Lancellotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>112</th>
      <td>Talk</td>
      <td>45</td>
      <td>Securing Python Web Applications</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Jose Manuel Ortega</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>113</th>
      <td>Talk</td>
      <td>45</td>
      <td>Voting-based Ranking Combination using Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Ferran Muiños</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>114</th>
      <td>Talk</td>
      <td>45</td>
      <td>Data Engineering for Data Scientists</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Max Humber</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>115</th>
      <td>Talk</td>
      <td>60</td>
      <td>Continuous Delivery comincia già dal tuo ambiente di sviluppo</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>116</th>
      <td>Talk</td>
      <td>45</td>
      <td>Dalla lingua del tweet all'immigrazione nelle città: Python ed i "Language Detectors"</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>117</th>
      <td>Talk</td>
      <td>60</td>
      <td>Python per attività di test</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Moro</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>118</th>
      <td>Talk</td>
      <td>45</td>
      <td>Predicting future states using High Order Markov Chains</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Mascolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>119</th>
      <td>Training</td>
      <td>240</td>
      <td>Python for Habitable Planets Hunting</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Maha Mdini</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>120</th>
      <td>Talk</td>
      <td>45</td>
      <td>Test di integrazione pronti all'uso con pytest-play</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Serena Martinetti</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>121</th>
      <td>Talk</td>
      <td>45</td>
      <td>Network in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>122</th>
      <td>Talk</td>
      <td>45</td>
      <td>Recommendation Model for Ranking Matching Houses</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Chiara Basei</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>123</th>
      <td>Talk</td>
      <td>60</td>
      <td>Training of Hybrid Recommender for Product Recommendation</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Cenk Bircanoğlu</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>124</th>
      <td>Talk</td>
      <td>60</td>
      <td>Come insegno l'Agile a scuola con Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>125</th>
      <td>Talk</td>
      <td>45</td>
      <td>Continuous Delivery for Agile teams</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Francesco Bruni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>126</th>
      <td>Talk</td>
      <td>60</td>
      <td>DevOps di applicazioni Python (e non solo) su OpenShift</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Francesco Fiore</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>127</th>
      <td>Talk</td>
      <td>45</td>
      <td>A Reinforcement Learning powered Recommender Engine</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>128</th>
      <td>Talk</td>
      <td>45</td>
      <td>Beyond XML: fast communication with Protocol Buffers</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Francesco Della Vedova</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>129</th>
      <td>Talk</td>
      <td>45</td>
      <td>Getting started with HDF5 and PyTables</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Giacomo Debidda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>130</th>
      <td>Talk</td>
      <td>60</td>
      <td>GPU-accelerated data analysis in Python: a study case in Material Sciences</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Giuseppe Di Bernardo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>131</th>
      <td>Training</td>
      <td>240</td>
      <td>Insegnare la matematica con Python: laboratori didattici e verifiche per le Scuole Superiori</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Poggiali</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>132</th>
      <td>Talk</td>
      <td>45</td>
      <td>Introduzione a HDF5 e PyTables</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Giacomo Debidda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>133</th>
      <td>Talk</td>
      <td>45</td>
      <td>Active Learning for Training Set Building</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Valerio Nicosia</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>134</th>
      <td>Talk</td>
      <td>60</td>
      <td>Valutazione delle prestazioni sportive: dai meccanismi cognitivi agli algoritmi data driven</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luca Pappalardo,Paolo Cintia</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>135</th>
      <td>Training</td>
      <td>240</td>
      <td>Real-Time Auto-Tagging of Chat Dialogues for Efficient Client Relations and Support Operations</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Kathleen Siminyu</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>136</th>
      <td>Training</td>
      <td>240</td>
      <td>Machine Learning for Programmers</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Oliver Zeigermann</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>137</th>
      <td>Talk</td>
      <td>60</td>
      <td>Refactoring with tests in Python: a practical example</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>138</th>
      <td>Talk</td>
      <td>45</td>
      <td>Django-freeradius</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Fiorella De Luca</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>139</th>
      <td>Talk</td>
      <td>45</td>
      <td>CPython loves your Pull Requests</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Stéphane Wirtel</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>140</th>
      <td>Talk</td>
      <td>60</td>
      <td>Un viaggio alla scoperta della lingua Cinese con Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Ezio Melotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>141</th>
      <td>Talk</td>
      <td>90</td>
      <td>Clean architectures in Python: perché, cosa, come</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>142</th>
      <td>Talk</td>
      <td>60</td>
      <td>Replica logica in PostgreSQL: il futuro è adesso</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Marco Nenciarini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>143</th>
      <td>Talk</td>
      <td>45</td>
      <td>Forge signatures with a GAN</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>meng shang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>144</th>
      <td>Talk</td>
      <td>60</td>
      <td>Everything I always wanted to know about crypto, but never thought I'd understand</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>145</th>
      <td>Talk</td>
      <td>45</td>
      <td>Selinon - dynamic distributed task flows</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Fridolín Pokorný</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>146</th>
      <td>Training</td>
      <td>240</td>
      <td>Dive into Object-oriented Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>147</th>
      <td>Training</td>
      <td>240</td>
      <td>Dive into Object-oriented Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>148</th>
      <td>Talk</td>
      <td>45</td>
      <td>TDD in Python con pytest</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>149</th>
      <td>Talk</td>
      <td>45</td>
      <td>7 Steps to a Clean Issue Tracker</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Lasse Schuirmann</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>150</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lessons Learned from Working Remote</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Nick Lang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>151</th>
      <td>Talk</td>
      <td>45</td>
      <td>Rain + dragon = Electricity: Unravelling the mysteries of ideograms with Python.</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Michael Penkov</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>152</th>
      <td>Talk</td>
      <td>90</td>
      <td>Computer Vision e Machine Learning per Macchine Autonome con OpenCV e Keras</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Lou Marvin Caraig</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>153</th>
      <td>Talk</td>
      <td>60</td>
      <td>Analisi dati in Python accelerata con GPU: uno study case in Scienze dei Materiali</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Giuseppe Di Bernardo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>154</th>
      <td>Talk</td>
      <td>45</td>
      <td>Asynchronous Multi Agent Systems</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Mascolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>155</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lessons from a massive, openly-developed project</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Thierry Carrez</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>156</th>
      <td>Talk</td>
      <td>45</td>
      <td>Working for FOSS can make you a better programmer: Insights into my Outreachy internship with Fedora</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alisha Aneja</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>157</th>
      <td>Talk</td>
      <td>45</td>
      <td>Django Girls Italia: entrare in contatto con le donne tecnologiche, davvero</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Laura Bartoli</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>158</th>
      <td>Talk</td>
      <td>45</td>
      <td>The Python Software Foundation and The Growth of Python in Africa</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marlene Mhangami</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>159</th>
      <td>Talk</td>
      <td>45</td>
      <td>Non ti servono n dimensioni quando hai pandas</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>160</th>
      <td>Talk</td>
      <td>60</td>
      <td>Introduzione a Django REST Framework</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Rigel Di Scala</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>161</th>
      <td>Talk</td>
      <td>60</td>
      <td>Together We Stand</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alicia Carr</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>162</th>
      <td>Talk</td>
      <td>45</td>
      <td>Virtual environments and dependency management in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Piotr Grzesik</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>163</th>
      <td>Talk</td>
      <td>45</td>
      <td>Going Isomorphic with Django and React</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Mattia Larentis</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>164</th>
      <td>Talk</td>
      <td>60</td>
      <td>Dall'IoT agli opendata: costruiamo un prototipo con Python, Sigfox e AWS</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Francesco Cabras</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>165</th>
      <td>Talk</td>
      <td>60</td>
      <td>Serverless Computing con Python e AWS: Redux</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Francesco Cabras</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>166</th>
      <td>Talk</td>
      <td>60</td>
      <td>Testing Thousands of Python Projects Every Day</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Monty Taylor</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>167</th>
      <td>Talk</td>
      <td>45</td>
      <td>DjangoProject.com - Ricerca Full-Text con PostgreSQL</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Paolo Melchiorre</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>168</th>
      <td>Talk</td>
      <td>45</td>
      <td>Da applicativi Desktop a Web</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luigi Renna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>169</th>
      <td>Talk</td>
      <td>60</td>
      <td>ROS per sviluppare Applicazioni Robotiche in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Ludovico Orlando Russo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>170</th>
      <td>Talk</td>
      <td>45</td>
      <td>DjangoProject.com - Full-Text Search with PostgreSQL</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Paolo Melchiorre</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>171</th>
      <td>Talk</td>
      <td>45</td>
      <td>My story with Python and Open Source</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Nicola Iarocci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>172</th>
      <td>Talk</td>
      <td>45</td>
      <td>Introduction to Distributed Tracing</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Mykola Novik</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>173</th>
      <td>Talk</td>
      <td>45</td>
      <td>La mia storia con Python e l'Open Source</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Nicola Iarocci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>174</th>
      <td>Talk</td>
      <td>90</td>
      <td>Idraulici di Dati?! - Costruire Data Pipelines con Airflow</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Michele De Simoni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>175</th>
      <td>Talk</td>
      <td>45</td>
      <td>Come vanno gli affari? Visualizziamolo con Superset</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Riccardo Magliocchetti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>176</th>
      <td>Talk</td>
      <td>45</td>
      <td>AN OPEN-SOURCE PROCESSING PIPELINE FOR TEXTUAL INFORMATION EXTRACTION FROM RECEIPTS</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Peter Engerer</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>177</th>
      <td>Talk</td>
      <td>45</td>
      <td>Next generation of word embeddings in gensim</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Parul Sethi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>178</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monitora le performance della tua applicazione Python Flask con Elasticsearch e Kibana</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Zuccon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>179</th>
      <td>Talk</td>
      <td>45</td>
      <td>Cyber Security auditing with python tools</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Jose Manuel Ortega</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>180</th>
      <td>Training</td>
      <td>240</td>
      <td>Digging into MicroPython</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Riccardo Magliocchetti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>181</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pelican e perchè generare siti statici</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Scarpa</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>182</th>
      <td>Talk</td>
      <td>45</td>
      <td>Applicazioni isomorfe con Django e React</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Mattia Larentis</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>183</th>
      <td>Talk</td>
      <td>60</td>
      <td>Sentiment analysis di emozioni con word embeddings: dall'analisi dei dati alla visualizzazione</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Mirko Mazzoleni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>184</th>
      <td>Talk</td>
      <td>45</td>
      <td>You don't need n dimensions when you have pandas</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>185</th>
      <td>Talk</td>
      <td>45</td>
      <td>Understanding Google SyntaxNet to build your own word taggers</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Massimo Nicosia</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>186</th>
      <td>Talk</td>
      <td>45</td>
      <td>Quando Django incontra PostgreSQL!</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Cecchi,Tamara Nocentini</td>
      <td>👨‍💻+👩‍💻</td>
    </tr>
    <tr>
      <th>187</th>
      <td>Talk</td>
      <td>45</td>
      <td>Sviluppare un linguaggio di programmazione usando Python da autodidatti</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Niccolo' "Veggero" Venerandi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>188</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pythonic management of the ATLAS computing farm</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marco Pernigotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>189</th>
      <td>Training</td>
      <td>240</td>
      <td>Come programmare i microcontrollori in Python: dal “blink” di un LED alla connessione al Cloud</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luigi Francesco Cerfeda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>190</th>
      <td>Talk</td>
      <td>60</td>
      <td>pg_chameleon MySQL to PostgreSQL replica made easy</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Federico Campoli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>191</th>
      <td>Talk</td>
      <td>45</td>
      <td>Healthy Minds in a Healthy Community</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>192</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python, patents and standards - An algorithm to classify and relate formal knowledge</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Maddalena Agnoli</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>193</th>
      <td>Talk</td>
      <td>45</td>
      <td>Heroku: come deployare un'app Django in 10 minuti!</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Sabatino Severino</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>194</th>
      <td>Talk</td>
      <td>45</td>
      <td>Taking care of PostgreSQL with Ansible</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Rubens Souza</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>195</th>
      <td>Talk</td>
      <td>60</td>
      <td>Introduzione a Zerynth: Python per Microcontrollori e Applicazioni IoT</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luigi Francesco Cerfeda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>196</th>
      <td>Talk</td>
      <td>45</td>
      <td>Understanding the production line dynamics: data science for manufacturing processes</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>197</th>
      <td>Talk</td>
      <td>60</td>
      <td>From PyData Padawan to Jedi: a journey through libraries, concepts and MOOCS</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Michele De Simoni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>198</th>
      <td>Talk</td>
      <td>60</td>
      <td>Social Network and External Communication Data analysis using NLP with industrial applications</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Rocco Michele Lancellotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>199</th>
      <td>Talk</td>
      <td>90</td>
      <td>IOT, Cloud, Big Data &amp; Django: Trueverit, uno sguardo da vicino</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Per Esperti</td>
      <td>🇮🇹</td>
      <td>Simone Fardella</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>200</th>
      <td>Talk</td>
      <td>45</td>
      <td>Reinforcement Learning applicato a Sistemi di Raccomandazione</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>201</th>
      <td>Talk</td>
      <td>60</td>
      <td>Helping communities &amp; products thrive by fostering empathy</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>202</th>
      <td>Talk</td>
      <td>45</td>
      <td>The Code of Conduct is here for you</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>203</th>
      <td>Talk</td>
      <td>60</td>
      <td>Usare Odoo come framework (Presentatori: Luigi Di Naro e Eliumara López)</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Eliumara López</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>204</th>
      <td>Talk</td>
      <td>45</td>
      <td>Developing a home-made programming language with python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Niccolo' "Veggero" Venerandi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>205</th>
      <td>Talk</td>
      <td>60</td>
      <td>Automating OpenShift-on-Openstack: from Heat to Ansible</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Roberto Polli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>206</th>
      <td>Talk</td>
      <td>60</td>
      <td>Django: Up and Running</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Simone Dalla</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>207</th>
      <td>Talk</td>
      <td>60</td>
      <td>Painless testing</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Max Kharandziuk</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>208</th>
      <td>Talk</td>
      <td>45</td>
      <td>Visualizing Topic Models</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Parul Sethi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>209</th>
      <td>Talk</td>
      <td>60</td>
      <td>Topic Modelling with Gensim</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Parul Sethi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>210</th>
      <td>Talk</td>
      <td>60</td>
      <td>test e bushido</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Brunetti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>211</th>
      <td>Talk</td>
      <td>45</td>
      <td>Perché dovresti iniziare a programmare con Python?</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Marzio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>212</th>
      <td>Training</td>
      <td>240</td>
      <td>Usiamo Genropy come GUI per realizzare programmi di utilità</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Francesco Porcari</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>213</th>
      <td>Talk</td>
      <td>60</td>
      <td>Business Intelligence con Genropy</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Francesco Porcari</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>214</th>
      <td>Talk</td>
      <td>45</td>
      <td>Anche la ricerca farmacologica ha bisogno di gestionali</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Giovanni Porcari</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>215</th>
      <td>Talk</td>
      <td>45</td>
      <td>AWSome infrastructure-as-code (IaC)</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Mark Fink</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>216</th>
      <td>Talk</td>
      <td>45</td>
      <td>microkanrenpy: an exercise in logic programming</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Massimo Nocentini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>217</th>
      <td>Talk</td>
      <td>45</td>
      <td>Building an IDE for Django in Django</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Paris Kasidiaris</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>218</th>
      <td>Talk</td>
      <td>45</td>
      <td>Deploy Django su ECS - Lessons learned</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Martino Pizzol</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>219</th>
      <td>Talk</td>
      <td>60</td>
      <td>La sicurezza dei database MySQL in ottica GDPR</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Marco Carlessi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>220</th>
      <td>Talk</td>
      <td>45</td>
      <td>Modellare la dinamica della linea di produzione: Data Science per i processi manifatturieri</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>221</th>
      <td>Talk</td>
      <td>45</td>
      <td>Estendere ed utilizzare FreeCAD con python</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Boscolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>222</th>
      <td>Talk</td>
      <td>45</td>
      <td>Automatizzare OpenShift on OpenStack: da Heat ad Ansible</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Roberto Polli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>223</th>
      <td>Talk</td>
      <td>45</td>
      <td>Intro to solit - An integration test framework for testing Logstash Configs</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Nick Lang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>224</th>
      <td>Talk</td>
      <td>45</td>
      <td>Gestione e integrazione di un centralino voip Wildix con il Crm sviluppato in Genropy</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Silvano Valleferro</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>225</th>
      <td>Talk</td>
      <td>60</td>
      <td>Erpy visto dal commercialista</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Riccardo Sclavi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>226</th>
      <td>Talk</td>
      <td>60</td>
      <td>OdooPLM un progetto in continua evoluzione</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Boscolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>227</th>
      <td>Talk</td>
      <td>90</td>
      <td>Il nuovo MySQL 8 per applicazioni moderne e performanti</td>
      <td>PyDatabase</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Marco Carlessi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>228</th>
      <td>Talk</td>
      <td>90</td>
      <td>Strumenti per il DevOps con MySQL</td>
      <td>PyDatabase</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Marco Carlessi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>229</th>
      <td>Talk</td>
      <td>45</td>
      <td>PyBeacon: Eddystone Protocol implementation in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Prabhanshu Attri</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>230</th>
      <td>Talk</td>
      <td>60</td>
      <td>OpenUpgrade migrare odoo con pochi problemi</td>
      <td>PyBusiness</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Matteo Boscolo</td>
      <td>👨‍💻</td>
    </tr>
  </tbody>
</table>
</div>




```python
trainings = rankings[rankings['Type'].values == 'Training']
talks = rankings[rankings['Type'].values == 'Talk']
```

<a name="stats"></a>
# Stats

## Speakers Stats


```python
from collections import defaultdict
speakers = defaultdict(set)
```


```python
for i, speaker in enumerate(rankings.Speakers.values):
    for j, name in enumerate(speaker.split(',')):
        gender = rankings.Gender[i].split('+')[j]
        speakers[gender].add(name)
```


```python
count_speakers = sum(len(s) for s in speakers.values())
print(count_speakers)
```

    153



```python
for k in speakers:
    print('{} --> {}'.format(k, len(speakers[k])))
```

    👨‍💻 --> 136
    👩‍💻 --> 17


## Talks Stats


```python
print('Talks --> {}'.format(talks.index.size))
print('Trainings --> {}'.format(trainings.index.size))
```

    Talks --> 210
    Trainings --> 21


### Lang


```python
rankings.Lang.value_counts()
```




    🇬🇧    140
    🇮🇹     91
    Name: Lang, dtype: int64



### Level


```python
rankings.Level.value_counts()
```




    Introduttivo       146
    Approfondimento     84
    Per Esperti          1
    Name: Level, dtype: int64



<a name="trainings"></a>
# Trainings Ranking


```python
trainings
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Type</th>
      <th>Duration</th>
      <th>Title</th>
      <th>Track</th>
      <th>Level</th>
      <th>Lang</th>
      <th>Speakers</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>Training</td>
      <td>240</td>
      <td>Modern time series analysis in Python</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Aileen Nielsen</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Training</td>
      <td>240</td>
      <td>Algorithmic fairness in data discovery, processing, and prediction: a full tutorial</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Aileen Nielsen</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Training</td>
      <td>240</td>
      <td>PyTorch from the ground up</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Daniele Ciriello,Luca Antiga</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Training</td>
      <td>240</td>
      <td>Real-time transcription and sentiment analysis of audio streams; on the phone and in the browser</td>
      <td>PyBusiness</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Aaron Bassett</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Training</td>
      <td>240</td>
      <td>Learning to fetch data for fun and profit</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Arsh .</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Training</td>
      <td>240</td>
      <td>Crea da zero un clone di Bitcoin in Python</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Rigel Di Scala</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Training</td>
      <td>240</td>
      <td>Codice più efficiente? Restate cythonizzati</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Training</td>
      <td>240</td>
      <td>Building a Data Science pipeline</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Manoj Pandey</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Training</td>
      <td>240</td>
      <td>TDD in Python with pytest</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>83</th>
      <td>Training</td>
      <td>240</td>
      <td>Build your own chatbot using the Facebook Messenger API and Python-NLP packages</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Akilesh Lakshminarayanan</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>91</th>
      <td>Training</td>
      <td>240</td>
      <td>Build your own CV (as in Computer Vision) with Keras and Tensorflow.</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Rodolfo Bonnin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>97</th>
      <td>Training</td>
      <td>240</td>
      <td>DATA PLUMBING 101: Building Data Pipelines for fun and profit</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Michele De Simoni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>119</th>
      <td>Training</td>
      <td>240</td>
      <td>Python for Habitable Planets Hunting</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Maha Mdini</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>131</th>
      <td>Training</td>
      <td>240</td>
      <td>Insegnare la matematica con Python: laboratori didattici e verifiche per le Scuole Superiori</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Poggiali</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>135</th>
      <td>Training</td>
      <td>240</td>
      <td>Real-Time Auto-Tagging of Chat Dialogues for Efficient Client Relations and Support Operations</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Kathleen Siminyu</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>136</th>
      <td>Training</td>
      <td>240</td>
      <td>Machine Learning for Programmers</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Oliver Zeigermann</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>146</th>
      <td>Training</td>
      <td>240</td>
      <td>Dive into Object-oriented Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>147</th>
      <td>Training</td>
      <td>240</td>
      <td>Dive into Object-oriented Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>180</th>
      <td>Training</td>
      <td>240</td>
      <td>Digging into MicroPython</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Riccardo Magliocchetti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>189</th>
      <td>Training</td>
      <td>240</td>
      <td>Come programmare i microcontrollori in Python: dal “blink” di un LED alla connessione al Cloud</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luigi Francesco Cerfeda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>212</th>
      <td>Training</td>
      <td>240</td>
      <td>Usiamo Genropy come GUI per realizzare programmi di utilità</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Francesco Porcari</td>
      <td>👨‍💻</td>
    </tr>
  </tbody>
</table>
</div>



<a name="talks"></a>
# Talks Ranking (per single Track)

<a name="pylang"></a>
##  Track `Python&Friends` 


```python
pylang = talks[talks['Track'].values == 'Python & Friends']
pylang.index = np.arange(1, pylang.index.size+1)
pylang
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Type</th>
      <th>Duration</th>
      <th>Title</th>
      <th>Track</th>
      <th>Level</th>
      <th>Lang</th>
      <th>Speakers</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Talk</td>
      <td>45</td>
      <td>Testing, then once you got there?</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Alessandro Molina</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Talk</td>
      <td>45</td>
      <td>Thinking functionally: Introduction to Functional Programming in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alisha Aneja</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Talk</td>
      <td>45</td>
      <td>TDD nella pratica: tips&amp;tricks</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Antonio Cuni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Talk</td>
      <td>45</td>
      <td>The practice of TDD: tips&amp;tricks</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Antonio Cuni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Talk</td>
      <td>45</td>
      <td>Everyday security issues and how to avoid them</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Christian Heimes</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Talk</td>
      <td>45</td>
      <td>In git we trust</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Simone Basso</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pachettizzare applicazioni python in un singolo file binario</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Gabriele Franch</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Talk</td>
      <td>45</td>
      <td>Il rasoio dei generatori di Python per semplificare il codice e ridurre l'uso di memoria</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Brunato</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python 3. Fight for non-blocking IO</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Denis Makogon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Talk</td>
      <td>45</td>
      <td>Property-based testing with Hypothesis</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Aniello Barletta</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Talk</td>
      <td>90</td>
      <td>Pygame torna a scuola</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Maurizio Boscaini,Alessandro Marchioro</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Talk</td>
      <td>45</td>
      <td>PyTest e Page Object: come scrivere facilmente test UI mantenibili</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Damiano Iannelli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Talk</td>
      <td>45</td>
      <td>PyTest and Page Object: how to easily write maintainable UI tests</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Damiano Iannelli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Talk</td>
      <td>45</td>
      <td>When your wetware has too many threads - Tips from an ADHDer on how to improve your focus</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Aaron Bassett</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Talk</td>
      <td>45</td>
      <td>Packaging binary stand alone applications in python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Gabriele Franch</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Talk</td>
      <td>45</td>
      <td>The forgotten Coders - The History of Women Coders</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alicia Carr</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Talk</td>
      <td>60</td>
      <td>Una zuppa di Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Alessandro Re</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Talk</td>
      <td>60</td>
      <td>A primer on the Ethereum Blockchain and Smart Contracts using Python and Serpent</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Stefano Fioravanzo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Talk</td>
      <td>45</td>
      <td>SSLError, now what?</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Christian Heimes</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Talk</td>
      <td>45</td>
      <td>IoT con Python: si può fare! dall'ESP8266 alla casa domotica</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Lelio Campanile</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Talk</td>
      <td>45</td>
      <td>Go and Debug your Python!</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Stéphane Wirtel</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Talk</td>
      <td>60</td>
      <td>Vim your Python, Python your Vim</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Miroslav Šedivý</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Talk</td>
      <td>45</td>
      <td>The Spectre and the Meltdown: a modern fable</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Thierry Carrez</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Talk</td>
      <td>60</td>
      <td>A journey into the Chinese language with Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Ezio Melotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Talk</td>
      <td>45</td>
      <td>Evolution or stagnation programming languages</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Daniele Esposti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monads and functional python</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Przemyslaw Pietrzak</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Talk</td>
      <td>60</td>
      <td>Python for testing</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Davide Moro</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Talk</td>
      <td>45</td>
      <td>Evoluzione o stagnazione dei linguaggi di programmazione</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Daniele Esposti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Talk</td>
      <td>45</td>
      <td>Testing Python Security</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Jose Manuel Ortega</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Talk</td>
      <td>45</td>
      <td>Don't reinvent the wheel: integrating command-line tools into your Python project</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Michael Penkov</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Talk</td>
      <td>45</td>
      <td>Integration tests ready to use with pytest-play</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Serena Martinetti</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Talk</td>
      <td>90</td>
      <td>Clean architectures in Python: why, what, how</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Talk</td>
      <td>45</td>
      <td>Celery with Python: The way to distribute and schedule millions of processes</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Kushagra Bhargava</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Talk</td>
      <td>60</td>
      <td>Analisi statica e Python</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Leonardo Cecchi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Talk</td>
      <td>60</td>
      <td>Refactoring con i test in Python: un esempio pratico</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Talk</td>
      <td>60</td>
      <td>Google loves Python 2.0</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Simone Dalla</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Talk</td>
      <td>60</td>
      <td>Creare un servizio rest asincrono con Sanic in TDD</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Lorenzo Mele</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Talk</td>
      <td>45</td>
      <td>A software robotics platform for enhancing human-robot interaction</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Enrico Carbognani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Talk</td>
      <td>45</td>
      <td>Securing Python Web Applications</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Jose Manuel Ortega</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Talk</td>
      <td>60</td>
      <td>Python per attività di test</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Moro</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Talk</td>
      <td>45</td>
      <td>Test di integrazione pronti all'uso con pytest-play</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Serena Martinetti</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Talk</td>
      <td>45</td>
      <td>Continuous Delivery for Agile teams</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Francesco Bruni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Talk</td>
      <td>45</td>
      <td>Beyond XML: fast communication with Protocol Buffers</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Francesco Della Vedova</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Talk</td>
      <td>60</td>
      <td>Refactoring with tests in Python: a practical example</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Talk</td>
      <td>45</td>
      <td>CPython loves your Pull Requests</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Stéphane Wirtel</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Talk</td>
      <td>60</td>
      <td>Un viaggio alla scoperta della lingua Cinese con Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Ezio Melotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Talk</td>
      <td>90</td>
      <td>Clean architectures in Python: perché, cosa, come</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Talk</td>
      <td>60</td>
      <td>Everything I always wanted to know about crypto, but never thought I'd understand</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Talk</td>
      <td>45</td>
      <td>TDD in Python con pytest</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Giordani</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Talk</td>
      <td>45</td>
      <td>7 Steps to a Clean Issue Tracker</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Lasse Schuirmann</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>51</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lessons Learned from Working Remote</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Nick Lang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Talk</td>
      <td>45</td>
      <td>Working for FOSS can make you a better programmer: Insights into my Outreachy internship with Fedora</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alisha Aneja</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>53</th>
      <td>Talk</td>
      <td>45</td>
      <td>Django Girls Italia: entrare in contatto con le donne tecnologiche, davvero</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Laura Bartoli</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Talk</td>
      <td>45</td>
      <td>The Python Software Foundation and The Growth of Python in Africa</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marlene Mhangami</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Talk</td>
      <td>60</td>
      <td>Together We Stand</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alicia Carr</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Talk</td>
      <td>45</td>
      <td>Virtual environments and dependency management in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Piotr Grzesik</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Talk</td>
      <td>60</td>
      <td>Dall'IoT agli opendata: costruiamo un prototipo con Python, Sigfox e AWS</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Francesco Cabras</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Talk</td>
      <td>60</td>
      <td>Testing Thousands of Python Projects Every Day</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Monty Taylor</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Talk</td>
      <td>60</td>
      <td>ROS per sviluppare Applicazioni Robotiche in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Ludovico Orlando Russo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>60</th>
      <td>Talk</td>
      <td>45</td>
      <td>My story with Python and Open Source</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Nicola Iarocci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Talk</td>
      <td>45</td>
      <td>Introduction to Distributed Tracing</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Mykola Novik</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Talk</td>
      <td>45</td>
      <td>La mia storia con Python e l'Open Source</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Nicola Iarocci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Talk</td>
      <td>45</td>
      <td>Cyber Security auditing with python tools</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Jose Manuel Ortega</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Talk</td>
      <td>45</td>
      <td>Sviluppare un linguaggio di programmazione usando Python da autodidatti</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Niccolo' "Veggero" Venerandi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>65</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pythonic management of the ATLAS computing farm</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marco Pernigotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>66</th>
      <td>Talk</td>
      <td>45</td>
      <td>Healthy Minds in a Healthy Community</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>67</th>
      <td>Talk</td>
      <td>60</td>
      <td>Helping communities &amp; products thrive by fostering empathy</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>68</th>
      <td>Talk</td>
      <td>45</td>
      <td>The Code of Conduct is here for you</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Sasha Romijn</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>69</th>
      <td>Talk</td>
      <td>45</td>
      <td>Developing a home-made programming language with python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Niccolo' "Veggero" Venerandi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>70</th>
      <td>Talk</td>
      <td>60</td>
      <td>test e bushido</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Brunetti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>71</th>
      <td>Talk</td>
      <td>45</td>
      <td>Perché dovresti iniziare a programmare con Python?</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Marzio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>72</th>
      <td>Talk</td>
      <td>45</td>
      <td>microkanrenpy: an exercise in logic programming</td>
      <td>Python &amp; Friends</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Massimo Nocentini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Talk</td>
      <td>45</td>
      <td>Intro to solit - An integration test framework for testing Logstash Configs</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Nick Lang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>74</th>
      <td>Talk</td>
      <td>45</td>
      <td>PyBeacon: Eddystone Protocol implementation in Python</td>
      <td>Python &amp; Friends</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Prabhanshu Attri</td>
      <td>👨‍💻</td>
    </tr>
  </tbody>
</table>
</div>




```python
print('Number of Talks Proposed: ', pylang.index.size, end='\n\n')

print('Language of Talks Proposed: ')
print(pylang.Lang.value_counts(), end='\n\n')

print('Levels of Talks Proposed: ')
print(pylang.Level.value_counts())
```

    Number of Talks Proposed:  74
    
    Language of Talks Proposed: 
    🇬🇧    46
    🇮🇹    28
    Name: Lang, dtype: int64
    
    Levels of Talks Proposed: 
    Introduttivo       48
    Approfondimento    26
    Name: Level, dtype: int64

<a name="pydata"></a>
##  Track `PyData`


```python
pydataers = talks[talks['Track'].values == 'PyData']
pydataers.index = np.arange(1, pydataers.index.size+1)
pydataers
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Type</th>
      <th>Duration</th>
      <th>Title</th>
      <th>Track</th>
      <th>Level</th>
      <th>Lang</th>
      <th>Speakers</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Talk</td>
      <td>60</td>
      <td>Resurrecting the dead with deep learning</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Aditthya Ramakrishnan</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Talk</td>
      <td>60</td>
      <td>Bokeh: Using python for interactive data visualization</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Ernesto Arbitrio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scaling your Data infrastructure</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Christian Barra</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Talk</td>
      <td>60</td>
      <td>How to make your model happy again</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alessia Marcolini</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Talk</td>
      <td>60</td>
      <td>Databases for Data Science</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alexander Hendorf</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Talk</td>
      <td>45</td>
      <td>Practical Machine Learning with Python and scikit-learn</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Andrea Grandi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Talk</td>
      <td>60</td>
      <td>Reproducibility, and Selection Bias in Learning: when just Cross Validation is not enough!</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Valerio Maggio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Talk</td>
      <td>45</td>
      <td>Data Visualization in Mixed Reality with Python</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Anna Nicanorova</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Talk</td>
      <td>60</td>
      <td>Deep Learning from zero to hero</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Gianluca Carucci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scientific computing con PyPy</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Antonio Cuni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Talk</td>
      <td>45</td>
      <td>Getting an Edge: Network Analysis in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Alon Nir</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Talk</td>
      <td>60</td>
      <td>Bokeh: Usare python per creare grafici interattivi</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Ernesto Arbitrio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pandas Tips and Tricks - Getting the Data to Confess with Python</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alon Nir</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Talk</td>
      <td>90</td>
      <td>Image Generation with Tensorflow (GANs)</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Cenk Bircanoğlu</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Talk</td>
      <td>45</td>
      <td>Creating Part Of Speech Tagger with Hidden Markov Model and Viterbi Algorithm</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Albertus Kelvin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Talk</td>
      <td>45</td>
      <td>Source Code Generation Based On User Intention Using LSTM Networks</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Albertus Kelvin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Talk</td>
      <td>45</td>
      <td>Automatic Multiple-Choice Question Generator by Using Machine Learning</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Albertus Kelvin</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Talk</td>
      <td>60</td>
      <td>Building chatbots using Facebook Messenger API and Python-NLP packages</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Akilesh Lakshminarayanan</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Talk</td>
      <td>45</td>
      <td>Reproducibility in Data Science</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Andrea Gigli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Talk</td>
      <td>60</td>
      <td>What's going on there? Understanding cities with location data.</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Gianni Barlacchi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Talk</td>
      <td>90</td>
      <td>Computer Vision and Machine Learning for Self-Driving Cars with OpenCV and Keras</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Lou Marvin Caraig</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Talk</td>
      <td>45</td>
      <td>Serverless SQL queries from Python with AWS Athena...or power to Data Scientists!</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Daniela Scardi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Talk</td>
      <td>45</td>
      <td>Using Python to bring democracy to the A.I. age</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Felipe Cabral</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Talk</td>
      <td>45</td>
      <td>Hacking Your Way Into Machine Learning</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Laksh Arora</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Talk</td>
      <td>45</td>
      <td>House Price Prediction with Distributed Keras</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Cenk Bircanoğlu</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Talk</td>
      <td>45</td>
      <td>Managed ML in the Cloud: Data Science The Right Way</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Alex Casalboni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Talk</td>
      <td>60</td>
      <td>Sports performance evaluation: from cognitive mechanisms to data-driven algorithms</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Luca Pappalardo,Paolo Cintia</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Talk</td>
      <td>45</td>
      <td>How to approach a Machine Learning Problem ? : YouTube Like Count Predictor</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Ayush Kumar Singh</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python e Elasticsearch:  dal Text Search a NLP e oltre</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Dario Balinzo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Talk</td>
      <td>45</td>
      <td>Visualising the world of competitive programming with Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Anuj Menta</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lies, damned lies, and statistics</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marco Bonzanini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Talk</td>
      <td>45</td>
      <td>Insegnare la matematica con Python: percorsi suggeriti per le Scuole Superiori</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Poggiali</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Talk</td>
      <td>45</td>
      <td>Networks in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Talk</td>
      <td>45</td>
      <td>Understanding Natural Language with Word Vectors</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Marco Bonzanini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python &amp; Industry 4.0: a real world case</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Gianluca Emireni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Talk</td>
      <td>45</td>
      <td>Query SQL  e serverless da Python con AWS Athena...o meglio potere ai Data Scientist!</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Daniela Scardi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Talk</td>
      <td>45</td>
      <td>Location, location, location:  Data Visualisation and Analysis of Geospatial data in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Michele Ferretti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Talk</td>
      <td>60</td>
      <td>Recent advancements in NLP and Deep Learning: A Quant's Perspective</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Umit Mert Cakmak</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scientific computing using Cython: Best of both Worlds!</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Simmi LNU</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Talk</td>
      <td>60</td>
      <td>Sentiment analysis of emotions via word embeddings: from data collection &amp; analysis to visualization</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Mirko Mazzoleni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lessons learned while analysing 30 million news articles</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Leif Uwe Vogelsang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Talk</td>
      <td>45</td>
      <td>From the language of the tweet to immigration in cities: Python and its "Language Detectors"</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Talk</td>
      <td>60</td>
      <td>Deep Learning in Computer Vision: state of the art techniques and applications in industry</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Rocco Michele Lancellotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Talk</td>
      <td>45</td>
      <td>Voting-based Ranking Combination using Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Ferran Muiños</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Talk</td>
      <td>45</td>
      <td>Data Engineering for Data Scientists</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Max Humber</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Talk</td>
      <td>45</td>
      <td>Dalla lingua del tweet all'immigrazione nelle città: Python ed i "Language Detectors"</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Talk</td>
      <td>45</td>
      <td>Predicting future states using High Order Markov Chains</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Mascolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Talk</td>
      <td>45</td>
      <td>Network in Python</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Talk</td>
      <td>45</td>
      <td>Recommendation Model for Ranking Matching Houses</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Chiara Basei</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Talk</td>
      <td>60</td>
      <td>Training of Hybrid Recommender for Product Recommendation</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Cenk Bircanoğlu</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>51</th>
      <td>Talk</td>
      <td>45</td>
      <td>A Reinforcement Learning powered Recommender Engine</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Talk</td>
      <td>45</td>
      <td>Getting started with HDF5 and PyTables</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Giacomo Debidda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>53</th>
      <td>Talk</td>
      <td>60</td>
      <td>GPU-accelerated data analysis in Python: a study case in Material Sciences</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Giuseppe Di Bernardo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Talk</td>
      <td>45</td>
      <td>Introduzione a HDF5 e PyTables</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Giacomo Debidda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Talk</td>
      <td>45</td>
      <td>Active Learning for Training Set Building</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Valerio Nicosia</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Talk</td>
      <td>60</td>
      <td>Valutazione delle prestazioni sportive: dai meccanismi cognitivi agli algoritmi data driven</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luca Pappalardo,Paolo Cintia</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Talk</td>
      <td>45</td>
      <td>Forge signatures with a GAN</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>meng shang</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Talk</td>
      <td>45</td>
      <td>Selinon - dynamic distributed task flows</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Fridolín Pokorný</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Talk</td>
      <td>45</td>
      <td>Rain + dragon = Electricity: Unravelling the mysteries of ideograms with Python.</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Michael Penkov</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>60</th>
      <td>Talk</td>
      <td>90</td>
      <td>Computer Vision e Machine Learning per Macchine Autonome con OpenCV e Keras</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Lou Marvin Caraig</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Talk</td>
      <td>60</td>
      <td>Analisi dati in Python accelerata con GPU: uno study case in Scienze dei Materiali</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Giuseppe Di Bernardo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Talk</td>
      <td>45</td>
      <td>Asynchronous Multi Agent Systems</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Mascolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Talk</td>
      <td>45</td>
      <td>Non ti servono n dimensioni quando hai pandas</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Talk</td>
      <td>90</td>
      <td>Idraulici di Dati?! - Costruire Data Pipelines con Airflow</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Michele De Simoni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>65</th>
      <td>Talk</td>
      <td>45</td>
      <td>AN OPEN-SOURCE PROCESSING PIPELINE FOR TEXTUAL INFORMATION EXTRACTION FROM RECEIPTS</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Peter Engerer</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>66</th>
      <td>Talk</td>
      <td>45</td>
      <td>Next generation of word embeddings in gensim</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Parul Sethi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>67</th>
      <td>Talk</td>
      <td>60</td>
      <td>Sentiment analysis di emozioni con word embeddings: dall'analisi dei dati alla visualizzazione</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Mirko Mazzoleni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>68</th>
      <td>Talk</td>
      <td>45</td>
      <td>You don't need n dimensions when you have pandas</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Pietro Battiston</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>69</th>
      <td>Talk</td>
      <td>45</td>
      <td>Understanding Google SyntaxNet to build your own word taggers</td>
      <td>PyData</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Massimo Nicosia</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>70</th>
      <td>Talk</td>
      <td>45</td>
      <td>Python, patents and standards - An algorithm to classify and relate formal knowledge</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Maddalena Agnoli</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>71</th>
      <td>Talk</td>
      <td>45</td>
      <td>Understanding the production line dynamics: data science for manufacturing processes</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>72</th>
      <td>Talk</td>
      <td>60</td>
      <td>From PyData Padawan to Jedi: a journey through libraries, concepts and MOOCS</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Michele De Simoni</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Talk</td>
      <td>60</td>
      <td>Social Network and External Communication Data analysis using NLP with industrial applications</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Rocco Michele Lancellotti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>74</th>
      <td>Talk</td>
      <td>45</td>
      <td>Reinforcement Learning applicato a Sistemi di Raccomandazione</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>75</th>
      <td>Talk</td>
      <td>45</td>
      <td>Visualizing Topic Models</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Parul Sethi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>76</th>
      <td>Talk</td>
      <td>60</td>
      <td>Topic Modelling with Gensim</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Parul Sethi</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>77</th>
      <td>Talk</td>
      <td>45</td>
      <td>Modellare la dinamica della linea di produzione: Data Science per i processi manifatturieri</td>
      <td>PyData</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Riccardo Lorenzon</td>
      <td>👨‍💻</td>
    </tr>
  </tbody>
</table>
</div>




```python
print('Number of Talks Proposed: ', pydataers.index.size, end='\n\n')

print('Language of Talks Proposed: ')
print(pydataers.Lang.value_counts(), end='\n\n')

print('Levels of Talks Proposed: ')
print(pydataers.Level.value_counts())
```

    Number of Talks Proposed:  77
    
    Language of Talks Proposed: 
    🇬🇧    59
    🇮🇹    18
    Name: Lang, dtype: int64
    
    Levels of Talks Proposed: 
    Introduttivo       54
    Approfondimento    23
    Name: Level, dtype: int64


<a name="pyweb"></a>
## Track `PyWeb & Devops` 


```python
pyweb = talks[talks['Track'].values == 'PyWeb & DevOps']
pyweb.index = np.arange(1, pyweb.index.size+1)
pyweb
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Type</th>
      <th>Duration</th>
      <th>Title</th>
      <th>Track</th>
      <th>Level</th>
      <th>Lang</th>
      <th>Speakers</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Talk</td>
      <td>45</td>
      <td>How to use Web-Sockets in Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Anton Caceres</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Talk</td>
      <td>45</td>
      <td>Writing and deploying serverless Python applications</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Cesar Cardenas Desales</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Talk</td>
      <td>45</td>
      <td>Costruire applicazioni web realtime con Django</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Iacopo Spalletti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Talk</td>
      <td>45</td>
      <td>GraphQL in Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Patrick Guido Arminio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Talk</td>
      <td>60</td>
      <td>Python on Web Browsers</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Roberto Alsina</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Talk</td>
      <td>60</td>
      <td>Applying serverless architecture pattern to distributed data processing</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Denis Makogon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Talk</td>
      <td>45</td>
      <td>GraphQL in Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Patrick Guido Arminio</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monitoraggio di applicazioni Django con Prometheus (e Grafana)</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Davide Setti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monitoring Django applications with Prometheus (and Grafana)</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Davide Setti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Talk</td>
      <td>60</td>
      <td>Continuous Delivery starts at your Development Environment</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Talk</td>
      <td>60</td>
      <td>PaaS per tutti i gusti: CI/CD sotto controllo con Kubernetes e Dokku</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Claudio Mignanti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Talk</td>
      <td>45</td>
      <td>Choose Your Own Adventure for Client Web Services with Graphql</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>David Anderson</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Talk</td>
      <td>60</td>
      <td>Dalla User Story al test automatico in Django: un percorso step by step per dormire sonni tranquilli</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Filippo Morelli,Gabriele Giaccari</td>
      <td>👨‍💻+👨‍💻</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Talk</td>
      <td>45</td>
      <td>Test di applicazioni Django riutilizzabili</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Iacopo Spalletti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Talk</td>
      <td>60</td>
      <td>Deploy di un'applicazione Python con Kubernetes</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Marco Santamaria</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Talk</td>
      <td>60</td>
      <td>How I teach Agile at school using Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Talk</td>
      <td>60</td>
      <td>Continuous Delivery comincia già dal tuo ambiente di sviluppo</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Talk</td>
      <td>60</td>
      <td>Come insegno l'Agile a scuola con Python</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Peter Bittner</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Talk</td>
      <td>60</td>
      <td>DevOps di applicazioni Python (e non solo) su OpenShift</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Francesco Fiore</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Talk</td>
      <td>45</td>
      <td>Django-freeradius</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Fiorella De Luca</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Talk</td>
      <td>45</td>
      <td>Lessons from a massive, openly-developed project</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Thierry Carrez</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Talk</td>
      <td>60</td>
      <td>Introduzione a Django REST Framework</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Rigel Di Scala</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Talk</td>
      <td>45</td>
      <td>Going Isomorphic with Django and React</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Mattia Larentis</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Talk</td>
      <td>60</td>
      <td>Serverless Computing con Python e AWS: Redux</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Francesco Cabras</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Talk</td>
      <td>45</td>
      <td>DjangoProject.com - Ricerca Full-Text con PostgreSQL</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Paolo Melchiorre</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Talk</td>
      <td>45</td>
      <td>DjangoProject.com - Full-Text Search with PostgreSQL</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Paolo Melchiorre</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Talk</td>
      <td>45</td>
      <td>Monitora le performance della tua applicazione Python Flask con Elasticsearch e Kibana</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Zuccon</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Talk</td>
      <td>45</td>
      <td>Pelican e perchè generare siti statici</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Scarpa</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Talk</td>
      <td>45</td>
      <td>Applicazioni isomorfe con Django e React</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Mattia Larentis</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Talk</td>
      <td>45</td>
      <td>Quando Django incontra PostgreSQL!</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Leonardo Cecchi,Tamara Nocentini</td>
      <td>👨‍💻+👩‍💻</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Talk</td>
      <td>45</td>
      <td>Heroku: come deployare un'app Django in 10 minuti!</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Sabatino Severino</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Talk</td>
      <td>90</td>
      <td>IOT, Cloud, Big Data &amp; Django: Trueverit, uno sguardo da vicino</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Per Esperti</td>
      <td>🇮🇹</td>
      <td>Simone Fardella</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Talk</td>
      <td>60</td>
      <td>Automating OpenShift-on-Openstack: from Heat to Ansible</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇬🇧</td>
      <td>Roberto Polli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Talk</td>
      <td>60</td>
      <td>Django: Up and Running</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Simone Dalla</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Talk</td>
      <td>60</td>
      <td>Painless testing</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Max Kharandziuk</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Talk</td>
      <td>45</td>
      <td>AWSome infrastructure-as-code (IaC)</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Mark Fink</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Talk</td>
      <td>45</td>
      <td>Building an IDE for Django in Django</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Paris Kasidiaris</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Talk</td>
      <td>45</td>
      <td>Deploy Django su ECS - Lessons learned</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Martino Pizzol</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Talk</td>
      <td>45</td>
      <td>Automatizzare OpenShift on OpenStack: da Heat ad Ansible</td>
      <td>PyWeb &amp; DevOps</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Roberto Polli</td>
      <td>👨‍💻</td>
    </tr>
  </tbody>
</table>
</div>




```python
print('Number of Talks Proposed: ', pyweb.index.size, end='\n\n')

print('Language of Talks Proposed: ')
print(pyweb.Lang.value_counts(), end='\n\n')

print('Levels of Talks Proposed: ')
print(pyweb.Level.value_counts())
```

    Number of Talks Proposed:  39
    
    Language of Talks Proposed: 
    🇮🇹    23
    🇬🇧    16
    Name: Lang, dtype: int64
    
    Levels of Talks Proposed: 
    Approfondimento    23
    Introduttivo       15
    Per Esperti         1
    Name: Level, dtype: int64


<a name="pybusiness"></a>
##  Track `PyBusiness` 


```python
pybusiness = talks[talks['Track'].values == 'PyBusiness']
pybusiness.index = np.arange(1, pybusiness.index.size+1)
pybusiness
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Type</th>
      <th>Duration</th>
      <th>Title</th>
      <th>Track</th>
      <th>Level</th>
      <th>Lang</th>
      <th>Speakers</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Talk</td>
      <td>45</td>
      <td>Da applicativi Desktop a Web</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luigi Renna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Talk</td>
      <td>45</td>
      <td>Come vanno gli affari? Visualizziamolo con Superset</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Riccardo Magliocchetti</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Talk</td>
      <td>60</td>
      <td>Introduzione a Zerynth: Python per Microcontrollori e Applicazioni IoT</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Luigi Francesco Cerfeda</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Talk</td>
      <td>60</td>
      <td>Usare Odoo come framework (Presentatori: Luigi Di Naro e Eliumara López)</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Eliumara López</td>
      <td>👩‍💻</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Talk</td>
      <td>60</td>
      <td>Business Intelligence con Genropy</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Francesco Porcari</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Talk</td>
      <td>45</td>
      <td>Anche la ricerca farmacologica ha bisogno di gestionali</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Giovanni Porcari</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Talk</td>
      <td>45</td>
      <td>Estendere ed utilizzare FreeCAD con python</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Boscolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Talk</td>
      <td>45</td>
      <td>Gestione e integrazione di un centralino voip Wildix con il Crm sviluppato in Genropy</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Silvano Valleferro</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Talk</td>
      <td>60</td>
      <td>Erpy visto dal commercialista</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Riccardo Sclavi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Talk</td>
      <td>60</td>
      <td>OdooPLM un progetto in continua evoluzione</td>
      <td>PyBusiness</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Matteo Boscolo</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Talk</td>
      <td>60</td>
      <td>OpenUpgrade migrare odoo con pochi problemi</td>
      <td>PyBusiness</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Matteo Boscolo</td>
      <td>👨‍💻</td>
    </tr>
  </tbody>
</table>
</div>




```python
print('Number of Talks Proposed: ', pybusiness.index.size, end='\n\n')

print('Language of Talks Proposed: ')
print(pybusiness.Lang.value_counts(), end='\n\n')

print('Levels of Talks Proposed: ')
print(pybusiness.Level.value_counts())
```

    Number of Talks Proposed:  11
    
    Language of Talks Proposed: 
    🇮🇹    11
    Name: Lang, dtype: int64
    
    Levels of Talks Proposed: 
    Introduttivo       10
    Approfondimento     1
    Name: Level, dtype: int64


<a name="pydb"></a>
## Track `PyDatabase` 


```python
pydb = talks[talks['Track'].values == 'PyDatabase']
pydb.index = np.arange(1, pydb.index.size+1)
pydb
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Type</th>
      <th>Duration</th>
      <th>Title</th>
      <th>Track</th>
      <th>Level</th>
      <th>Lang</th>
      <th>Speakers</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Talk</td>
      <td>45</td>
      <td>PostgreSQL &amp; Python: La coppia perfetta.</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Giulio Calacoci</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Talk</td>
      <td>45</td>
      <td>Unveiling the potential of graph databases with Python and Neo4j</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Talk</td>
      <td>45</td>
      <td>Scoprire le potenzialità del database a grafo con Python e Neo4j</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Fabio Lamanna</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Talk</td>
      <td>60</td>
      <td>Replica logica in PostgreSQL: il futuro è adesso</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Marco Nenciarini</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Talk</td>
      <td>60</td>
      <td>pg_chameleon MySQL to PostgreSQL replica made easy</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Federico Campoli</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Talk</td>
      <td>45</td>
      <td>Taking care of PostgreSQL with Ansible</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇬🇧</td>
      <td>Rubens Souza</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Talk</td>
      <td>60</td>
      <td>La sicurezza dei database MySQL in ottica GDPR</td>
      <td>PyDatabase</td>
      <td>Introduttivo</td>
      <td>🇮🇹</td>
      <td>Marco Carlessi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Talk</td>
      <td>90</td>
      <td>Il nuovo MySQL 8 per applicazioni moderne e performanti</td>
      <td>PyDatabase</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Marco Carlessi</td>
      <td>👨‍💻</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Talk</td>
      <td>90</td>
      <td>Strumenti per il DevOps con MySQL</td>
      <td>PyDatabase</td>
      <td>Approfondimento</td>
      <td>🇮🇹</td>
      <td>Marco Carlessi</td>
      <td>👨‍💻</td>
    </tr>
  </tbody>
</table>
</div>




```python
print('Number of Talks Proposed: ', pydb.index.size, end='\n\n')

print('Language of Talks Proposed: ')
print(pydb.Lang.value_counts(), end='\n\n')

print('Levels of Talks Proposed: ')
print(pydb.Level.value_counts())
```

    Number of Talks Proposed:  9
    
    Language of Talks Proposed: 
    🇮🇹    6
    🇬🇧    3
    Name: Lang, dtype: int64
    
    Levels of Talks Proposed: 
    Introduttivo       7
    Approfondimento    2
    Name: Level, dtype: int64
