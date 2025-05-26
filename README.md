# Instalacija
```
git init   
git clone git@github.com:ognjenMagicni/Project001.git   
git pull origin main   
```

```
cd clicker-project
python3 -m venv venv_p
source venv_p/bin/activate
pip3 install -r requirements.txt
python3 -m ipykernel install --user --name=venv_p
```

Postoji mogućnost da se zadnja komanda ne pokrene zbog nedostatka "ipykernel". U tom slučaju raditi sledeće:
```
pip3 install ipykernel
python3 -m ipykernel install --user --name=venv_p
```

Odabrati kernel venv_v

U clicker-project kreirati .env fajl u kojem treba napisati
```
HUGGING_FACE_TOKEN='Ovjde_ide_token'
```

# Kodovi
## clusterisation_without_labels.ipynb
Kod koji klasteriše audio snimke koji nemaju labele. Kao primjer napravljen je folder "audio_snimci" u kojem se nalaze audio snimci koje će algoritam klasterizovati. 

**Input** : u drugoj ćeliji pod nazivom "directory" može da se da putanja do foldera koji sadrži audio snimke.

**Output** : poslednja ćelija vraća klasterizovane audio snimke za više algoritama.

## segmentation_of_audio.ipynb
Ovaj kod se koristi da se automatski segmentira jedan veliki audio snimak pomoću pyannote/speaker-diarization, takođe ima veliku preciznost u klasterizuji audio snimaka.

**Input** : u drugoj ćeliji je "file_path_audio" koja predstavlja putanju do audio fajla koji treba da se segmentira.

**Output** : Generiše folder "speaker", u kojima su govornici "SPEAKER_00", "SPEAKER_01",.... sa odgovarajućim klasterizovanim audio snimcima.

## clusterisation.ipynb
Kod klasteriše audio snimke koji imaju labele na osnovu segmentation_of_audio.ipynb. Dodatno, ovim pristupom može da se provjeri tačnost algoritma. Prije klasterizacije, audio snimci su pomiješani.

**Input** : u drugoj ćeliji je promenjiva "folder", putanja gdje su smješteni folderi govornika, koji sadrže odgovarajuće audio snimke. Putanja do foldera svakog posebnog govornika treba da se sačuva u listi "dictionaries".

**Output** : poslednja ćelija vraća klasterizovane audio snimke i ocjenu za više algoritama.
