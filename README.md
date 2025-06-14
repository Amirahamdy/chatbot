Chatbot Intent Classification
This Space is a chatbot that predicts user intent and responds accordingly using a TensorFlow model.

How it works
Input: A user message (string).
Output: Predicted intent + chatbot response.
Example
Input:Hello Output:json { "intent": "greeting", "response": "Hello! How can I assist you today?" }

Deployment
This chatbot is deployed as an Inference API on Hugging Face Spaces. To use it programmatically, send a POST request to: https://amira9090-chattbot.hf.space/api/predict/

Example using JavaScript (Fetch): javascript
    fetch("https://amira9090-chattbot.hf.space/api/predict/", {  
    method: "POST",  
    headers: { "Content-Type": "application/json" },  
    body: JSON.stringify({ inputs: "What services do you offer?" })  
    })  
    .then(res => res.json())  
    .then(data => {  
    console.log("Intent:", data.intent);  
    console.log("Response:", data.response);  
    });  
Example Intents from FAQS.json
    {  
    "intents": [  
        {  
        "tag": "greeting",  
        "patterns": ["Hi", "Hello", "Is anyone there?"],  
        "responses": ["Hello!", "Hi there, how can I help you?", "Hi!"]  
        },  
        {  
        "tag": "working_hours",  
        "patterns": ["When do you open?", "Working hours?", "Opening times?"],  
        "responses": ["We work from 9 AM to 5 PM, Sunday to Thursday."]  
        }  
    ]  
    }
