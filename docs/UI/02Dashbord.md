# Agri-Chain System Architecture (The Big Picture)

---

### 1. Dashboard Visual Layout (Markdown Diagram)

Ye raha tumhare dashboard ka ek **Blueprint** jo tumne describe kiya hai:

```text
+-----------------------------------------------------------------------------------+
| [≡] AGRI-CHAIN: GUJARAT DASHBOARD                                  👤 Harshil     |
+-----------------------------------------------------------------------------------+
|                   |                                                               |
|   SIDEBAR MENU    |   [ SECTION 1: HISTORICAL TREND ]                             |
|                   |   +---------------------------+   +---------------------------+
|  🏠 Dashboard     |   | Select Jilla: [ Rajkot ]  |   | Select Crop: [ Gehu ]     |
|                   |   +---------------------------+   +---------------------------+
|  🌾 Yield Predict |                                                               |
|                   |   [~~~~~~~~~~~~~~~~~~ Interactive Line Graph ~~~~~~~~~~~~~~~~~]
|  📈 Future Price  |   [          (Price changes over last 1 month)                ]
|                   |                                                               |
|  🌍 Geo-Impact    |   +-----------------------------------------------------------+
|                   |                                                               |
|  ---------------- |   [ SECTION 2: TODAY'S MARKET ANALYSIS ]                      |
|                   |   +---------------------------+                               |
|  ⚙️ Settings      |   | Select Jilla: [ Jasdan ]  |                               |
|                   |   +---------------------------+                               |
|  ❓ Help/Support  |                                                               |
|                   |   +---------------------------+   +---------------------------+
|                   |   |   TABLE: ALL CROPS TODAY  |   |   TOP GAINER (HIGHLIGHT)  |
|                   |   | Crop   | Price  | Change  |   |    JEERA (Cumin)         |
|                   |   |--------|--------|---------|   |    ₹6,500 (+₹150)        |
|                   |   | Gehu   | ₹2,300 | +₹10    |   |    [ High Demand Alert ] |
|                   |   +---------------------------+   +---------------------------+
|                   |                                                               |
|                   |   [ SECTION 3: MONTHLY HIGH-PRICE INSIGHTS ]                  |
|                   |   [========== Static Bar Chart: Last Month Highs =============]
|                   |                                                               |
+-----------------------------------------------------------------------------------+
```
---

### 3. Logic Summary (Zero to Google Level)

* **Layer 1 (The Bot):** GitHub Action (Har raat data fetch karega).
* **Layer 2 (The Vault):** CSV File/SQL Database (Data store karega).
* **Layer 3 (The Brain):** Python + Pandas (Data filter karega).
* **Layer 4 (The Face):** Streamlit + Plotly (Ye sundar dashboard dikhayega).



---

### Google Interview Tip: "Edge Cases"
Interviewer tumse puchega: *"Agar kisan ke paas internet slow ho toh?"*
**Tera Answer:** > "I will use **Streamlit's Caching (`st.cache_data`)** and **Arrow format** for data transmission. Isse data compress ho jata hai aur slow internet par bhi graph jaldi load hota hai."

---

### Action Plan:
Bhai, visualization toh set ho gaya. Ab ye **"Jasdan"** wala data fetch karne ke liye humein script likhni hai.

**Kya main tumhe woh `fetch_data.py` script likh kar doon jo Gujarat APMC website se real prices nikaal sake?** (Isse tumhara pehla automatic step shuru ho jayega).