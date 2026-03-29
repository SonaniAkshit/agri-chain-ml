# **"Agri-Mitra AI Chatbot"**

---

### 1. Chatbot Logic: Ye Kaam Kaise Karega? (The "Brain")

Hum isme **RAG (Retrieval-Augmented Generation)** technique use karenge. 
* **Database:** Humare system ke paas pichle 10 saal ka price data, weather report, aur crop disease ki jankari hogi.
* **The Model:** Hum **Google Gemini API** (jo tumhare liye best hai) ya **OpenAI** use karenge.
* **Translation:** User Hindi mein poochega, model use process karega, aur wapis Hindi/Hinglish mein hi jawab dega.



---

### 2. Chatbot UI Design (Markdown Blueprint)

Chatbot ko hum sidebar mein ek alag option ki tarah ya fir screen ke corner mein ek **"Floating Bubble"** ki tarah rakh sakte hain.

```text
+-------------------------------------------------------+
|              🤖 AGRI-MITRA: AI SAHAYAK               |
|-------------------------------------------------------|
|  [Bot]: Namaste Harshil! Main aapki kya madad kar     |
|         sakta hoon?                                   |
|                                                       |
|  [User]: Kya agle mahine Gehu ka bhav badhega?        |
|                                                       |
|  [Bot]: 📊 Mere data ke hisaab se, Rajkot mandi mein  |
|         agle 15 dino mein Gehu 5-8% mehenga ho sakta  |
|         hai kyunki supply kam hai. Aap rukk sakte hain.|
|                                                       |
|  [User]: Barish ka kya anuman hai?                    |
|                                                       |
|  [Input]: [ Type your question in Hindi...      ] [SAY]|
+-------------------------------------------------------+
```

---

### 3. Extra "Smart" Features (Google Level Insights)

Chatbot sirf baat nahi karega, wo ye bhi kar sakta hai:
* **Voice-to-Text:** Kisan ko type karne ki zaroorat nahi, wo bol kar pooch sake (Speech Recognition).
* **Multi-lingual:** Hindi ke saath-saath **Gujarati** support bhi dalenge (Kyunki hum Gujarat APMC focus kar rahe hain).
* **Direct Action:** User bol sake "Mujhe Jasdan ka graph dikhao," aur chatbot dashboard par wo graph load kar de.

---

### 4. Logic Building: Streamlit Implementation

Streamlit mein Chatbot banana bahut asaan hai `st.chat_message` ka use karke.

```python
if app_mode == "Agri-Mitra Bot":
    st.header("🤖 Agri-Mitra: Aapka AI Dost")
    
    # Initialize chat history
    if "messages" not in st.session_state:
        st.session_state.messages = []

    # Display chat messages from history on app rerun
    for message in st.session_state.messages:
        with st.chat_message(message["role"]):
            st.markdown(message["content"])

    # React to user input
    if prompt := st.chat_input("Hindi mein poochiye (e.g. Aaj ka bhav kya hai?)"):
        # Display user message in chat message container
        with st.chat_message("user"):
            st.markdown(prompt)
        
        # Add user message to chat history
        st.session_state.messages.append({"role": "user", "content": prompt})

        # Logic: Yahan tumhara ML model ya Gemini API response dega
        response = f"Agri-Mitra: Aapne poocha '{prompt}'. Iska anuman hai ki..."
        
        with st.chat_message("assistant"):
            st.markdown(response)
        st.session_state.messages.append({"role": "assistant", "content": response})
```

---

### 5. Google Interview Perspective: "Accessibility"
Interviewer puchega: *"Why did you build a chatbot instead of just showing tables?"*

**Tera Answer:**
> "Bhai, Bharat ke rural sectors mein **'Conversational UI'** zyada effective hai. Bahut se kisan complex dashboards se darr sakte hain, lekin unhe WhatsApp par chat karna aata hai. Ek AI chatbot unhe wahi simple experience deta hai aur complex ML data ko asaan bhasha mein samjhata hai."

---

### Action Plan:
Bhai, **Agri-Chain** ab ek complete product ban chuka hai! 
1. **Dashboard** | 2. **Yield Predict** | 3. **Future Price** | 4. **Geo-Impact** | 5. **AI Chatbot**

Ab hamara **Planning Phase 100% Finish** ho gaya hai. Ab aur design nahi, ab **Asli Kaam (Coding)** shuru karte hain. 

**Bhai, kya main ab tumhe ek poori `app.py` ki file likh kar doon jisme ye saara UI aur Menu Logic ek saath ho?** Phir hum dheere-dheere har page mein ML model fit karenge. Bolo, shuru karein?