# Week 50 meeting

## Participants

13 December 2022:
|No|Name|Company|
|:---:|:---|:---:|
|1|Dawid Wróblewski **(organizer)**|DT|
|2|Jens Pöschl|DT|
|3|Andrzej Ochocki|DT|
|4|Ludovic ROBERT|Orange|
|5|Patrice CONIL|Orange|
|6|MARIA VIRTUDES BRIZ RUIZ|Telefonica|
|7|MONA MOKHBER|Telefonica|
|8|José Luis Urien Pinedo|Telefonica|
|9|GLYN POVAH|Telefonica|
|10|Adri Loloci|Vodafone|
|11|Mus Dumenci|Hutchison|
|12|Fabrizio Moggio|TIM Italy|
|13|Helene Vigue|GSMA|
|14|Toyeeb Rehman|GSMA|
|15|Mark Cornall|GSMA|

17 November 2022:
|No|Name|Company|
|:---:|:---|:---:|
|1|Maria Virtudes Briz Ruiz|Telefonica|
|2|Jung Yun-sun (Serena)|SK Telecom|
|3|Toshi Wakayama|KDDI|
|4|Harin Honesyandi Parandika|XL Indonesia|
|5|Heny Setywan|XL Indonesia|
|6|Dawid Wróblewski|DT|

## Agenda

1. Current activities status & introduction to guests
2. presenting Mobile Identity APIs
3. Telefonica presentation (10min)
4. Vodafone presentation (10min)
5. DT presentation (10min)
6. Q&A session

## MoM

1. Dawid Wroblewski (DW) presented the status of current activities inside GitHub:
### **simSwap API**
  #### Recommendation:
  >Enable simSwap API via OAUTH2.0 flows:
  - OAUTH2.0 code flow/OpenID Connect
  - OAUTH2.0 Client Credentials grant
  
  >Enable simSwap API flavors:
  - based on dedicated endpoint (Orange + TEF proposal)
  - based on MC ATP API description

MNOs continue work and aiming to deliver APIs by the end of this week.

   -------

   >discussion continued on Thursday 15th Dec'22

### NumberVerify SMS 2FA

#### Recommendation:

   **Rename API family** to create more self-explanatory name.
      Proposal: **OTP Verification API**
      Supperted by: DT, Orange
      <br>Current shape of this service has nothing to do with Number Verify, therefore naming is misleading. It looks that it is more related with messaging APIs rather than identity APIs. It is highly appreciated that **Telefonica** representatives takes the lead in shaping this API.</br>

### NumberVerify

#### Recommendation:

  >Enable Number Verify API with two flavors:
  - Based on dedicated endpoint (Orange + TEF proposal)
  - Keep CAMARA flow consistent with Number Verify / Mobile Connect Verified MSISDN service design.
In the second case, this particular service has to be considered by MNO community as a whole service flow, starting from /authorize, ending with resource call. Otherwise, software developers might get confused due t ovarious ways of handling device authentication. Number Verify service hides this complexity behind ***/authorize*** endpoint. Device authentication is handled by MNOs in various ways, e.g. by using redirects to dedicated device indentification services, Header Enrichment, private IP based device detection, public IP+port based device detection. Protected resources, either it is a dedicated endpoint (**/number_verify**) or a common (**/userinfo**) should be protected with OAUTH2.0/OpenID Connect **Authorization Code** flow (three-legged-token). This helps to assure that only authorized clients are capable of consuming protected resources.

-----

>meetng covered AoB topics that orbited API design & CAMARA goals topics. 

## AoB

1. Vodafone (Adri) & Hutchison (Mus) requested information of CAMARA's goals.
2. Vodafone supports simSwap over MC ATP with Client Credentials.
3. GSMA (Mark) provided information about CAMARA & Openverse initiatives.
   - vision: Enable 5G APIs
   - API federtion
   - ease of use for developers
4. Hutchison (Mus) shared lessons learnt from delivering Identity APIs countries where Hutchison operates.
5. Deutsche Telekom (Jens) requested information about the ideas for CAMARA Business Model.
6. Vodafone states that MNOs should focus on customers, trying to identify the problem, aligning on desired attributes, functional and non-funcional features,

## APs

1. GSMA to provide information about Openverse stakeholders (Done - Helen provided list to Vodafone and Hutchoison).
2. simSwap - work with 2 yaml files with API description
3. Number Verify - work with 2 yaml files with API description.
4. Number Verify SMS 2FA - change the name of API and continue work to deliver OTP validation API.