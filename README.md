# Name Entity Recognition for Indian Legal System

The solution is trained using large dataset of Judgments from Supreme Court of India and various High Court to extract named entities and their relatioship.

The solution uses Natural Language Processing Technique called Name Entity Recognition to extract Name Entities and has been trained on a Large Datasets.

The solution can be invoked using an API at a marginal cost. 

## This solution currently support the following Name Entities:

1. Court Name
2. Reportable
3. Judge Name
4. Petitioner
5. Appellant
6. Respondent
7. Appeal Number
8 Special Leave Petition
9. Public Witness
10. Statue
11. Sections
12. Acts
13. Article
14. Rule
15. Order
16. Citation


Expected Input: Judgment in PDF Format (Supports both Machine Readable and Images)

Example Output:
```
{
    "_id": "<pdf file Name>.pdf",
    "judgementDate": "DD-MM-YYYY",
    "judgementYear": "<Judgemnt Year>",
    "pages": [{
        "page_no": 1,
        "text": "<Page 1 Content>",
        "ila_ner": {
            "Reportable": ["NON - REPORTABLE"],
            "Court": ["THE SUPREME COURT OF INDIA", "High Court of Judicature at Rajasthan"],
            "Appeal_No": ["CRIMINAL APPEAL NO . XXX OF YYYY", "Appeal No . XXX of YYYY"],
            "Special_Leave_Petition": ["SLP ( Crl . ) No . XXX of YYYY"],
            "Appellant": ["The State of Rajasthan"],
            "Respondent": ["<Respondent Name>"],
            "Judge_Name": ["<Judge Name>"]
        }
    }, {
        "page_no": 2,
        "text": "<Page 2 Content>",
        "ila_ner": {
            "Section": ["Sections 325 and 323", "Section 325", "Section 323", "Sections 307", "326", "447", "323", "341"],
            "Statue": ["Indian Penal Code", "IPC"],
            "Court": ["<Court Name>"]
        }
    }, {
        "page_no": 3,
        "text": "<Page 3 Content>",
        "ila_ner": {
            "Section": ["Sections 307", "326", "Sections 325", "323"],
            "Statue": ["IPC"]
            "Act": ["<Act"],
            "Citation": [
              "<Party Name 1> vs <Party Name 2> ( 2010 ) 6 SCC XXX"
            ]
        }
    }
    ......
    , {
        "page_no": 10,
        "text": "<Page 10 Content>",
        "ila_ner": {
            "Citation": [
              "<Party Name 1> vs <Party Name 2>  AIR XXXX SC XX"
            ],
            "Judge_Name": ["<Judge Name>"]
        }
    }],
    "pdf_ner": {
        "Reportable": ["NON - REPORTABLE"],
        "Court": ["THE SUPREME COURT OF INDIA", "High Court of Judicature at Rajasthan", "Additional Sessions Judge , Sambharlake"],
        "Appeal_No": ["CRIMINAL APPEAL NO . XXX OF YYYY", "Appeal No . XXX of YYYY"],
        "Special_Leave_Petition": ["SLP ( Crl . ) No . XXXX of YYYY"],
        "Appellant": ["The State of Rajasthan"],
        "Respondent": ["<Respondent Name>"],
        "Judge_Name": ["<Judge Name>"],
        "Section": ["Sections 325 and 323", "Section 325", "Section 323", "Sections 307", "326", "447", "323", "341", "Sections 325"],
        "Statue": ["Indian Penal Code", "IPC"],
        "Citation": [
          "<Party Name 1> vs <Party Name 2> ( 2010 ) 6 SCC XXX", 
          "<Party Name 1> vs <Party Name 2>  AIR XXXX SC XX"
        ],
        Act": [
          "<Act Name 1>", 
          "<Act Name 2>"
        ],
        "Order": ["Order XXXX"],
        "Rule": ["Rule XX"],
    }
}
```
