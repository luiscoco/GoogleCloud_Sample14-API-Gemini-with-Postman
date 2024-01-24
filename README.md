# Google Cloud API Gemini quickstart with Postman

## 1. Prerequisites

**Commands summary**

```
gcloud init
gcloud config set project extreme-axon-381209
gcloud auth login
gcloud auth list
gcloud auth print-access-token
gcloud ai endpoints list --region=us-central1
```

We first log in to **Google Cloud CLI**

```
gcloud init
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/32d4bb7e-d10e-4559-822c-1205aa7eb666)

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/0cda8f2e-6108-4156-9636-e3cad669bf21)

We select the **Google Cloud Project**

```
gcloud config set project extreme-axon-381209
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/a8cf66e6-3c07-4056-b18e-93e44cd1c1e5)

We log in with the authorization 

```
gcloud auth login
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/46801ae1-9e83-4a9a-a9ba-10192573c8cc)

We can list the **authorizations** with the following command

```
gcloud auth list
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/2498f6fb-b906-4993-b451-b301a09fe574)

We print the **Access Token**, and in the following section we teach you how to set the Postman authorization request

```
gcloud auth print-access-token
```

We type the following command to retrieve the **Gemini Endpoint**

```
gcloud ai endpoints list --region=us-central1
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/2b37b266-08f2-418c-a382-27078c20aa8a)

## 2. Gemini API Reference documentation

We recomend you to visit the following web pages to start working with **Gemini**

https://cloud.google.com/vertex-ai/docs/generative-ai/start/quickstarts/quickstart-multimodal

https://cloud.google.com/vertex-ai/docs/generative-ai/model-reference/gemini

## 3. First sample with Postman

We run **Postman** and we create a new **POST** request pressing on the **+** button

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/b94dcdb5-b967-4bd5-9dc4-08b57972e3f3)

We select the **POST** request

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/2ac534e7-e479-41a9-b516-dfb5f2435dce)

We navigate to **Gemini Sample** URL: https://cloud.google.com/vertex-ai/docs/generative-ai/model-reference/gemini

and we copy the **Gemini URL** in Postman

https://**us-central1**-aiplatform.googleapis.com/v1/projects/**PROJECT_ID**/locations/**us-central1**/publishers/google/models/gemini-pro:streamGenerateContent?alt=sse

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/e39d5d49-1a4d-4f04-b951-cea69ac42007)

We can also obtain the Gemini URL running this command

```
gcloud ai endpoints list --region=us-central1
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/8dac5cb4-7f5a-40d8-a035-3a4207405c32)

We obtain the **PROJECT_ID** we press on the project drop-down list

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/3d26e2e6-7f7a-4fa7-a23f-7a07380ee720)

And we copy the **PROJECT_ID** in postman

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/396ac1f9-46f1-4257-8ab9-91c68438cffb)

We input the **PROJECT_ID** in postman

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/8eec0683-65c8-478f-9a7f-4d5076109026)

We obtain the **Access Token** running this command

```
gcloud auth print-access-token
```

We input the **Access Token in Postman**

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/b1c8ff06-7569-4a41-8c1d-c2e91306de45)

We select the Body request format **JSON**

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/49305cca-678c-473b-92dd-81a51cf0b39c)

We input the input **Body** request

```json
{
  "contents": {
    "role": "user",
    "parts": {
        "text": "Give me a recipe for banana bread."
    },
  },
  "safety_settings": {
    "category": "HARM_CATEGORY_SEXUALLY_EXPLICIT",
    "threshold": "BLOCK_LOW_AND_ABOVE"
  },
  "generation_config": {
    "temperature": 0.2,
    "topP": 0.8,
    "topK": 40
  }
}
```




