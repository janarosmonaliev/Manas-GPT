# Manas-GPT

This is a personal project aimed to build an LLM based on [Epic of Manas (Sayakbai Karalaev's version)](<https://en.wikipedia.org/wiki/Epic_of_Manas#:~:text=The%20Epic%20of%20Manas%20(Kyrgyz,it%20to%20be%20much%20older)>).

### Pre-processing

We need to prepare our dataset first. There is an openly available Epic of Manas book (Sayakbai Karalaev's version) in PDF format that I was able to find. Before we begin training, we need our dataset to be in text format:

1. `preprocessing.ipynb` is a simple script that converts `epic-of-manas.pdf` into text using `PyPDF2`.
2. Manual formatting was done to some extent to remove double line issues.
3. `prepare.py` is a forked text to `.bin` format train-test dataset converter taken from Andrej Karpathy's [nanoGPT](https://github.com/karpathy/nanoGPT) repository. This will be needed for more in-depth training.

### Simple Training

If you don't have a powerful GPU and using a laptop/Macbook like I did in the beginning, you can run `model_training_v1.py` to train Manas-GPT with limited number of hyperparameters (10.7 M). It took about ~5 hours on Macbook Air M2.

```
python model_training_v1.py
# outputs 500 tokens to manas_synthetic_text.txt
```

### In-depth Training

For this task, I used Google Colab Pro+, as it offers more powerful GPUs with background execution. Since Google Colab VMs flush all of its working directory after session timeouts, `colab_runtime` has the files that need to be uploaded to Google Colab file directory for training. Note that you have to connect it to your GDrive for training models to be saved.

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
