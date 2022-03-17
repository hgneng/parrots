# Parrots
Parrots, Automatic Speech Recognition(ASR), Text-To-Speech(TTS) engine.

## Install
```
pip3 install -r requirements.txt
sudo apt install python3-dev -y
sudo apt install portaudio19-dev python-all-dev
git clone https://github.com/shibing624/parrots.git
cd parrots
python3 setup.py install
```


## Usage
### Speech Recognition
打开 "tests/speech_reco_test.py"，运行


output:
```
北津科技过了(北京科技馆)
```

### TTS
```
env PYTHONPATH=. tests/tts_speak_test.py
play tests/tts_speak_test.py
```

## update

### 语音库
从SourceForge下载语音库[`syllables.zip`](https://sourceforge.net/projects/hantts/files/?source=navbar)，并解压到`parrots/data`目录下。这个语音库声音太小，效果不好。建议下载Ekho的：

https://sourceforge.net/projects/e-guidedog/files/Ekho-Voice-Data/0.2/

### 录制新的语音库
- 按阴平、阳平、上声、去声、轻声的顺序录下 mapping.json 里每一个音节的五个声调
- 按开头字母(letter)分组, 将文件存在 ./recording/{letter}.wav下
- 运行 `python process.py {letter}` 将{letter}.wav 完整的录音分成独立的拼音
- 检查核对`./pre`文件夹中的拼音.wav后导入文件夹`./syllables`

