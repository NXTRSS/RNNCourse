# Natural Language Processing

Link do repozytorium: https://github.com/NXTRSS/NLPCourse

Poniżej przedstawiam instrukcję niezbędnych kroków do wykonania przed zajęciami

## Praca z VirtualEnv
Osobiście polecam skorzystać z Anacondy (instrukcja poniżej) jednak jeśli ktoś chce wykorzystywać venv oraz pip poniżej podaję komendy:
```bash
pip install virtualenv

virtualenv ml_nlp

source ml_nlp/venv/bin/activate

pip install -r requirements.txt

python -m ipykernel install --user --name ml_nlp --display-name "Python (ml_nlp)"

jupyter notebook
```

## Zainstalowanie Minicondy
Pomoże nam ona w zarządzaniu środowiskami pythonowymi oraz w ściaganiu niezbędnych paczek (np. Tensor Flow)
```bash
sudo apt-get update

sudo apt-get install curl
```
Wymagane jest ściagnięcie odpowiedniej wersji Minicondy -  odpowiadającej systemowi operacyjnemu (Linux w naszym przypadku) oraz architekturze procesora.\
\
**Proszę sprawdzić, który link będzie dla państwa odpowiedni pod tym adresem**: https://docs.conda.io/en/latest/miniconda.html#linux-installers\
Załóżmy, że będzie to procesor Intela 64-bit. W takiej sytuacji korzystamy z linku: *https://repo.anaconda.com/miniconda/Miniconda3-py38_4.11.0-Linux-x86_64.sh*
```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-py38_4.11.0-Linux-x86_64.sh
```
W przypadku procesorów Mac od Appla M1 byłoby to:
```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-py38_4.11.0-Linux-aarch64.sh
```
Następnie, po ściągnięciu plików do instalacji Minicondy, wystarczy uruchomić proces instalacji\ *(P.S. Najprawdopodobniej jeśli dziwne krzaczki ściagały się podczas wywołania powyższej lini, zły link został podany)*
```bash
# Oczywiście poniższy plik musi się zgadzać z tym, który został ściagnięty
# czyli dla procesora M1 końcówka byłaby Linux-aarch64.sh
bash Miniconda3-py38_4.11.0-Linux-x86_64.sh
```
Następnie trzeba przejść przez instalację podając Enter i/lub *yes* w terminalu.\
**Ważne: Po powyższych krokach proszę zrestartować terminal**

### Problemy z zainstalowaniem Minicondy
Jeśli będą jakieś problemy z zainstalowaniem Minicondy zgodnie z powyższą instrukcją bardzo proszę odnieść się do dokumentacji: [Miniconda documentation](https://docs.conda.io/en/latest/miniconda.html#miniconda)\
Jeśli nadal występują problemy, w krytycznej sytuacji, proszę sprobować ściągnąć Anacondę zgodnie z dokumentacją: [Anaconda Linux](https://docs.anaconda.com/anaconda/install/linux/), w takiej sytuacji trzeba nadal zwrócić uwagę na architekturę procesora.
## Ściągnięcie plików z kodami
Jeśli zainstalowanie Minicondy przebiegło pomyślę oraz **zrestartowali państwo terminal** powinno być widoczne słówko *base* w nawiasach w naszym terminalu (przykład):
```bash
(base) kamil@ubuntu:~$
```
Ta nazwa w nawiasie to właśnie nazwa naszego środowiska python - w tej sytuacji domyślnie jest to *base*.\
Stwórzmy nowe foldery aby łatwiej poruszać się po plikach:
```bash
cd ~
mkdir SDA/ml_nlp -p
cd SDA/ml_nlp
```
Teraz do folderu ściągnijmy pliki z GitHub potrzebne podczas zajęć
```bash
git clone https://github.com/NXTRSS/NLPCourse
```
*P.S. Można też wejść w dostarczony link i ściągnąć dane przez wygenerowanie archiwum .zip a następnie wypakowanie go w naszym folderze*
## Stworzenie środowiska python
Jeśli ściągnięcie plików przebiegło poprawnie w naszym folderze powinien znajdować się plik *environment.yaml* i za jego pomocą stworzymy nowe środowisko pythonowe o nazwie **ml**:
```bash
cd NLPCourse

conda env create -f environment.yaml

conda activate ml_nlp
```
Po aktywacji nowego środowiska zamiast *base* powinno być widoczne *ml* w naszym terminalu (przykład):
```bash
(ml_nlp) kamil@ubuntu:~$
```
**Proszę pamiętać aby zawsze aktywować to środowisko po wznowieniu pracy na komputerze!**\
Proszę wywołać poniższe linijki aby aktywować kilka dodatkowych ustawień:
```bash
pip install svgling==0.3.1
python -m ipykernel install --user --name ml_nlp --display-name "Python (ml_nlp)"
```
## Rozpoczęcie (oraz wznowienie pracy)
Przy każdym wznowieniu pracy (ponownym odpaleniu komputera i maszyny wirtualnej) proszę wejście do odpowiedniego folderu:
```bash
cd SDA/ml_nlp/NLPCourse
```
 zaktywować środowisko o nazwie *ml*:
```bash
conda activate ml_nlp
```
A następnie wywołać narzędzie **Jupyter Notebook**, które jest webową aplikacją, na której będziemy pracować na naszych zajęciach:
```bash
jupyter notebook
```
Po aktywacji powyższej komendy otworzy się przeglądarka a w niej nasze pliki.\
**Ważne: w narzędziu Jupyter Notebook do uruchamiania przygotowanych skryptów trzeba będzie "wyklikać" kernel *Python (ml_nlp)* - będzie to pokazane na zajęciach.**\

