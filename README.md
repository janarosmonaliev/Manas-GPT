# Manas-GPT
This is a personal project aimed to build an LLM based on [Epic of Manas (Sayakbai Karalaev's version)](https://en.wikipedia.org/wiki/Epic_of_Manas#:~:text=The%20Epic%20of%20Manas%20(Kyrgyz,it%20to%20be%20much%20older)).

# Process
1. Openly available Epic of Manas (Sayakbai Karalaev's version) was downloaded as PDF
2. PDF file was converted into TXT using `PyPDF2`
3. Process of model training was learned from [Let's build GPT: from scratch, in code, spelled out](https://www.youtube.com/watch?v=kCc8FmEb1nY) by Andrej Karpathy, a founding member of Open AI

## Training Data
Here's a sample text from 263517 word long Epic of Manas:
```
Манастын туула элегиндеги бабалары  
Түп атасы Түгөл кан,  
үбүнөн Кыдыр даарыган,  
Башкы атасы баары кан,  
Башынан Кыдыр даарыган.  
Түнөп өткөн жерине  
Түптүү мазар орногон  
Муну түбүнөн кудай оңдогон.  
Басып өткөн жерине  
Базарлуу калаа орногон, 
```

## Generated Data
```
Күн экени билбеген,  
Кордукту коюп салыптыр.  
Күтөрүп абиз ит эле,  
Түнөрүп жерге кирген жок,  
Букту элдеп билгенин 
Өз рт экени билиптир.  
Астындагы калың кол  
Далай жолдон кармап токтоду,  
Казыналык чоң Дөөдүр  
Мойнунан чачымынып,  
```

# Other Notes
- Python 3.11.7
- Torch 2.4.0.dev20240414 (Nightly, supports M1/M2 Mac GPU processing)
- Conda 24.3.0
