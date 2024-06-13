BIM Аналитика
=============

## Установка редактора

1. Python - https://www.python.org
2. VSCode - https://code.visualstudio.com
3. Git - https://git-scm.com/downloads

Здесь и далее для запуска команд нужна командная строка `cmd`.
Чтобы ее открыть, нажмите `Win + R`, введите `cmd` и нажмите `Enter`.

4. Скачать репозиторий:
```bash
git clone https://github.com/greendwin/bim_stats.git
```

Либо выбрать `Clone reposotory` в `VSCode` и вставить ссылку https://github.com/greendwin/bim_stats.git. (В этом случае п.5 не нужен)

5. Открыть папку `bim_stats` в `vscode`


## Установка окружения и библиотек

1. Установить `poetry` и `pipx`

Если `pipx` не находится, то можно попробовать перезапустить `cmd.exe`

```bash
# install pipx
pip install --user pipx
python -m pipx ensurepath

# install poetry
pipx install poetry
poetry --version
```

2. Установить библиотеки

```bash
cd bim_stats
poetry install
```

3. Активировать виртуальное окружение

В `VSCode` внизу справа выбрать `Select Interpreter` и выбрать venv созданный `poetry`.


## Анализ данных

### Очистка данных

1. Скачиваем в папку `data` файл `IFC_2000_300_Columns.csv` с [сайта kaggle.com](https://www.kaggle.com/code/artemboiko/5000-projects-ifc-rvt-datadrivenconstruction-io/notebook)

2. Открываем в `VSCode` jupyter notebook `notebooks/data_cleanup.ipynb`
Ядром `kernel` следует выбрать окружение `bim_stats`, созаднное `poetry`.
Если оно не появляется в списке, то путь к `python.exe` из установленного окружения можно получить выполнив команду

   ```bash
   poetry env info --executable
   ```

3. Запускаем все ячейки в `notebook` и генерируем файлы:
   * `data/IFC_2000_300_Columns_Beams.csv` 
   * `data/IFC_2000_300_Columns_Windows.csv` 
   * ???