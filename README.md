# Google Cloud API Gemini quickstart with Postman

## 1. Prerequisites

**Commands summary**

```
gcloud init
gcloud config set project xxxxxxxxxxxxxxxx
gcloud auth login
gcloud auth list
gcloud auth print-access-token
gcloud ai endpoints list --region=us-central1
```

We first log in to **Google Cloud CLI**

```
gcloud init
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/fd12f35b-1da5-45e4-9f34-c51b359b37d1)

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/6ecbca48-e210-4ba4-a777-3576cae1dae9)

We select the **Google Cloud Project**

```
gcloud config set project xxxxxxxxxxxxxx
```

We log in with the authorization 

```
gcloud auth login
```

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

## 3. First sample with Postman (Text)

We run these commands and then we copy the Access Token 

```
gcloud init
gcloud config set project xxxxxxxxxxxxxxxxx
gcloud auth login
gcloud auth list
gcloud auth print-access-token
gcloud ai endpoints list --region=us-central1
```

We are going to test the samples in this URL: **https://cloud.google.com/vertex-ai/docs/generative-ai/model-reference/gemini**

We run **Postman** and we create a new **POST** request pressing on the **+** button

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/b94dcdb5-b967-4bd5-9dc4-08b57972e3f3)

We select the **POST** request

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/2ac534e7-e479-41a9-b516-dfb5f2435dce)

We navigate to **Gemini Sample** URL: https://cloud.google.com/vertex-ai/docs/generative-ai/model-reference/gemini

and we copy the **Gemini URL** in Postman

**https://us-central1-aiplatform.googleapis.com/v1/projects/PROJECT_ID/locations/us-central1/publishers/google/models/gemini-pro:streamGenerateContent?alt=sse**

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

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/8625087b-c7b1-47b2-964e-e789ef4151a5)

We select the Body request format **JSON**

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/1f24d8be-98b7-446c-ba9a-de2b4549b804)

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

See the input body in Postman

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/46c79a5e-ff60-470d-a2c0-bda6718f8bf9)

After pressing the **Send** button we get the following response

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/cf9f70e8-f34f-4db9-bf70-115cfe89ab94)

## 4. Second sample with Postman (Multimodal)

We run these commands and then we copy the Access Token 

```
gcloud init
gcloud config set project xxxxxxxxxxxxxxxxxx
gcloud auth login
gcloud auth list
gcloud auth print-access-token
gcloud ai endpoints list --region=us-central1
```

We input the Access Toke in Postman

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/7513c572-4809-4010-863e-182a71563111)

We are going to test the samples in this URL: **https://cloud.google.com/vertex-ai/docs/generative-ai/model-reference/gemini**

We copy from the sample the **Gemini URL**:

https://us-central1-aiplatform.googleapis.com/v1/projects/PROJECT_ID/locations/us-central1/publishers/google/models/gemini-pro-vision:streamGenerateContent

We get the **PROJECT_ID** from Google Cloud Console

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/3d26e2e6-7f7a-4fa7-a23f-7a07380ee720)

We input the **PROJECT_ID** in postman

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/6b25d13b-4315-4ff0-acb4-deef434130a3)

We select the Body request format **JSON**

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/45f4f8db-fe7c-4679-9ed4-ae8aede7b6a6)

We input the input **Body** request

```json
{
  "contents": {
    "role": "user",
    "parts": [
      {
        "fileData": {
          "mimeType": "image/png",
          "fileUri": "gs://cloud-samples-data/ai-platform/flowers/daisy/10559679065_50d2b16f6d.jpg"
        }
      },
      {
        "text": "Describe this picture."
      }
    ]
  },
  "safety_settings": {
    "category": "HARM_CATEGORY_SEXUALLY_EXPLICIT",
    "threshold": "BLOCK_LOW_AND_ABOVE"
  },
  "generation_config": {
    "temperature": 0.4,
    "topP": 1.0,
    "topK": 32,
    "maxOutputTokens": 2048
  }
}
```

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/6909eaaa-472b-41a1-8c8b-ba1767584d07)

We navigate to **Gemini Sample** URL: https://cloud.google.com/vertex-ai/docs/generative-ai/model-reference/gemini

and we copy the **Gemini URL** in Postman

**https://us-central1-aiplatform.googleapis.com/v1/projects/PROJECT_ID/locations/us-central1/publishers/google/models/gemini-pro-vision:streamGenerateContent**

This is the response we get

![image](https://github.com/luiscoco/GoogleCloud_Sample14-API-Gemini-with-Postman/assets/32194879/e25480cf-8876-4194-a2cd-2f2427f90a5e)

```json
[{
  "candidates": [
    {
      "content": {
        "role": "model",
        "parts": [
          {
            "text": " A daisy is growing up through a pile of brown and yellow fall leaves. The daisy has white petals with a yellow center. The leaves are all different shapes"
          }
        ]
      },
      "safetyRatings": [
        {
          "category": "HARM_CATEGORY_HARASSMENT",
          "probability": "NEGLIGIBLE"
        },
        {
          "category": "HARM_CATEGORY_HATE_SPEECH",
          "probability": "NEGLIGIBLE"
        },
        {
          "category": "HARM_CATEGORY_SEXUALLY_EXPLICIT",
          "probability": "NEGLIGIBLE"
        },
        {
          "category": "HARM_CATEGORY_DANGEROUS_CONTENT",
          "probability": "NEGLIGIBLE"
        }
      ]
    }
  ]
}
,
{
  "candidates": [
    {
      "content": {
        "role": "model",
        "parts": [
          {
            "text": " and sizes. The daisy is the only thing that is not brown or yellow in the picture."
          }
        ]
      },
      "finishReason": "STOP",
      "safetyRatings": [
        {
          "category": "HARM_CATEGORY_HARASSMENT",
          "probability": "NEGLIGIBLE"
        },
        {
          "category": "HARM_CATEGORY_HATE_SPEECH",
          "probability": "NEGLIGIBLE"
        },
        {
          "category": "HARM_CATEGORY_SEXUALLY_EXPLICIT",
          "probability": "NEGLIGIBLE"
        },
        {
          "category": "HARM_CATEGORY_DANGEROUS_CONTENT",
          "probability": "NEGLIGIBLE"
        }
      ]
    }
  ],
  "usageMetadata": {
    "promptTokenCount": 262,
    "candidatesTokenCount": 50,
    "totalTokenCount": 312
  }
}
]
```

