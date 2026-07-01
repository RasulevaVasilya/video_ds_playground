# Video DS Playground — Выполнение заданий

## Обзор

Данный документ содержит отчёт о выполнении всех 8 заданий по курсу "Video Data Science Playground". Работа выполнена в среде GitHub Codespace с использованием Python 3.12.1.

## Выполненные задания

| № | Задание | Результат |
|---|---------|-----------|
| 01 | Cloud Fetch | Видео загружено из локального хранилища |
| 02 | Audio Extract | Аудио извлечено в WAV (16kHz, моно) |
| 03 | Transcription | Транскрипция получена |
| 04 | Speaker Diarization | Определён 1 спикер |
| 05 | VAD | Доля речи: 18.7% |
| 06 | Quality Metrics | SNR: 12.62 дБ |
| 07 | Denoising | Улучшение SNR на 2.4 дБ |
| 08 | Postprocessing | Текст очищен от галлюцинаций |

## Результаты

| Параметр | Значение |
|----------|----------|
| Транскрипция | "Все, давай сделаем это еще раз...." |
| Количество спикеров | 1 |
| SNR | 12.62 дБ |
| Доля речи | 18.7% |
| Улучшение SNR | 2.4 дБ |

## Проблемы и решения

1. **ModuleNotFoundError: No module named 'src'** — добавлен путь в PYTHONPATH
2. **ffmpeg not found** — установлен ffmpeg
3. **ImportError: cannot import name 'compute_snr'** — добавлена функция в metrics.py
4. **ImportError: cannot import name 'SimpleDiarizerWrapper'** — добавлен класс в pyannote_wrapper.py
5. **HF_TOKEN не найден** — создан токен на Hugging Face
6. **403 Forbidden** — приняты условия использования моделей
7. **too many values to unpack** — исправлен код в pyannote_wrapper.py
8. **'dict object' has no attribute 'stoi'** — исправлен report_generator.py
9. **CUDA device error** — заменено device: cuda на device: cpu

## Структура проекта
video_ds_playground/
├── src/models/
│ ├── silero_vad.py
│ ├── pyannote_wrapper.py
│ └── denoise_wrappers.py
├── src/utils/
│ ├── metrics.py
│ └── report_generator.py
└── data/reports/
└── report_*.html
