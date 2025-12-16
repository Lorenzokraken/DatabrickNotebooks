# 🚀 Guida Databricks/Spark

---

## 📖 Come Usare Questa Guida

Questa cartella contiene appunti organizzati per imparare Databricks e Spark passo passo.

### 🎯 Percorso di Apprendimento Consigliato

#### 1️⃣ **Inizia qui: Capire i Big Data**
📂 [SPARK/1) Introduzione ai Big Datas.ipynb](SPARK/1)%20Introduzione%20ai%20Big%20Datas.ipynb)
- Cos'è un Big Data problem
- Quando serve Spark invece di Pandas
- Cluster, scalabilità, cloud
- **Tempo**: 15 minuti

#### 2️⃣ **Da Pandas a Spark: Il Ponte**
📂 [DOCS/PANDAS_TO_SPARK.ipynb](DOCS/PANDAS_TO_SPARK.ipynb)
- **INIZIA SEMPRE DA QUI SE CONOSCI PANDAS** ⭐
- Equivalenze Pandas ↔ Spark
- Esempi pratici affiancati
- Errori comuni da evitare
- **Tempo**: 30 minuti

#### 3️⃣ **ETL in Databricks: Pratica Base**
📂 [LEZIONI/LEZIONE 1 APPUNTI.IPYNB](LEZIONI/LEZIONE%201%20APPUNTI.IPYNB)
- Extract-Transform-Load completo
- Leggere da file e tabelle
- Trasformazioni, aggregazioni, join
- Salvare risultati
- Pipeline ETL completa
- **Tempo**: 45 minuti

#### 4️⃣ **Cheatsheet: Riferimento Rapido**
📂 [DOCS/databricks_cheatsheet.ipynb](DOCS/databricks_cheatsheet.ipynb)
- Comandi ordinati per complessità
- Snippet pronti all'uso
- Template per esercizi
- **Uso**: Tieni aperto mentre lavori

#### 5️⃣ **Architettura Lakehouse** (Opzionale - Teoria)
📂 [LEZIONI/LEZIONE 2 APPUNTI.IPYNB](LEZIONI/LEZIONE%202%20APPUNTI.IPYNB)
- Cos'è l'architettura Lakehouse
- Unity Catalog
- Governance e best practices
- **Tempo**: 20 minuti

#### 6️⃣ **Integrazione Cloud** (Opzionale - Avanzato)
📂 [LEZIONI/LEZIONE 3 APPUNTI.IPYNB](LEZIONI/LEZIONE%203%20APPUNTI.IPYNB)
- Azure Data Lake Storage (ADLS)
- Mounting cloud storage
- Volumi e cataloghi
- **Tempo**: 30 minuti

#### 7️⃣ **Esercizi Pratici**
📂 [PRATICA.ipynb](PRATICA.ipynb) e [PRATICA 2.ipynb](PRATICA%202.ipynb)
- Delta Live Tables
- Pipeline complete
- Esempi reali
- **Fai dopo aver completato i punti 1-4**

---

## 🎓 Percorso Veloce (2 Ore)

Se hai poco tempo, segui questo percorso minimo:

1. ⚡ [PANDAS_TO_SPARK.ipynb](DOCS/PANDAS_TO_SPARK.ipynb) - **30 min**
2. ⚡ [LEZIONE 1 APPUNTI.IPYNB](LEZIONI/LEZIONE%201%20APPUNTI.IPYNB) - **45 min**
3. ⚡ [databricks_cheatsheet.ipynb](DOCS/databricks_cheatsheet.ipynb) - **15 min lettura**
4. ⚡ [PRATICA.ipynb](PRATICA.ipynb) - **30 min esercizio**

Dopo questo sei pronta per iniziare a lavorare!

---

## 💡 Concetti Chiave da Ricordare

### Pandas vs Spark
```python
# ❌ Pandas: Tutto in RAM su 1 macchina (limite ~10GB)
df = pd.read_csv("data.csv")
df.groupby('col').sum()

# ✅ Spark: Distribuito su cluster (scala a TB/PB)
df = spark.read.csv("data.csv", header=True, inferSchema=True)
df.groupBy('col').sum().show()
```

### Quando usare cosa?
- **Pandas**: Dataset < 10GB, prototipazione veloce, notebook locali
- **Spark**: Dataset > 10GB, produzione, scalabilità, Big Data

### Regola d'oro
⛔ **MAI convertire a Pandas per operazioni su grandi dataset:**
```python
# ❌ SBAGLIATO
df.toPandas().groupby('col').sum()  # Porta tutto in memoria!

# ✅ CORRETTO
df.groupBy('col').sum()  # Rimane distribuito
```

---

## 🛠️ Setup Databricks

### Community Edition (Gratis)
1. Vai su https://community.cloud.databricks.com/
2. Registrati gratuitamente
3. Crea un cluster (single-node va bene per imparare)
4. Carica questi notebook

### Workspace Aziendale
Se hai accesso a Azure Databricks:
1. Importa questa cartella nel workspace
2. Crea un cluster (o usa uno esistente)
3. Inizia dal percorso consigliato

---

## 📚 Struttura Cartella

```
Databricks/
│
├── DOCS/                          # Riferimenti e guide
│   ├── PANDAS_TO_SPARK.ipynb     ⭐ INIZIA QUI se conosci Pandas
│   ├── databricks_cheatsheet.ipynb
│   └── code_docs_alternative.ipynb
│
├── LEZIONI/                       # Teoria ed esempi
│   ├── LEZIONE 1 APPUNTI.IPYNB   # ETL Base
│   ├── LEZIONE 2 APPUNTI.IPYNB   # Architettura Lakehouse
│   └── LEZIONE 3 APPUNTI.IPYNB   # Integrazione Cloud
│
├── SPARK/                         # Concetti Big Data
│   ├── 1) Introduzione ai Big Datas.ipynb
│   └── 2) Progetti di Big Data.ipynb
│
├── PRATICA.ipynb                  # Esercizi pratici
├── PRATICA 2.ipynb                # Pipeline avanzate
└── README.md                      # Questa guida
```

---

## 🎯 Obiettivi di Apprendimento

Dopo aver completato questo percorso saprai:

✅ Leggere dati da file e tabelle in Spark  
✅ Trasformare dati con filter, select, withColumn  
✅ Fare aggregazioni con groupBy  
✅ Join tra dataset  
✅ Salvare risultati come tabelle Delta  
✅ Creare pipeline ETL complete  
✅ Evitare errori comuni (toPandas, iterazioni, ecc.)  
✅ Usare Unity Catalog per organizzare dati  
✅ Differenza tra Batch e Streaming  

---

## 🆘 Risorse Esterne

- **Databricks Academy**: https://academy.databricks.com/ (corsi gratis)
- **PySpark Documentation**: https://spark.apache.org/docs/latest/api/python/
- **Delta Lake**: https://docs.delta.io/
- **Community Forums**: https://community.databricks.com/

---

## 💬 Suggerimenti

### Per imparare velocemente:
1. **Non leggere tutto**: Segui il percorso consigliato
2. **Pratica subito**: Dopo ogni concetto, prova su Databricks
3. **Usa il cheatsheet**: Copialo e modificalo per i tuoi casi
4. **Paragona con Pandas**: Ogni volta che vedi Spark, pensa "come lo farei in Pandas?"

### Per ricordare:
- Spark è **lazy**: pianifica ma esegue solo con `.show()`, `.count()`, `.write()`
- Spark è **immutabile**: ogni trasformazione crea un nuovo DataFrame
- **Cache** se riusi lo stesso DataFrame più volte: `.cache()`

### Errori comuni:
```python
# ❌ Non iterare riga per riga
for row in df.collect():  # Lento!
    process(row)

# ✅ Usa trasformazioni vettoriali
df.withColumn('new', process_udf(col('old')))
```

---

## ✨ Buono Studio!

Se hai domande o trovi errori negli appunti, contatta chi ti ha passato questi materiali.

**Ricorda**: Spark non è complicato, è solo diverso da Pandas. Una volta capito il mindset distribuito, tutto diventa naturale! 🚀
