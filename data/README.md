# Dataset source

**FIFA 22 complete player dataset**, published by Stefano Leone on [Kaggle](https://www.kaggle.com/datasets/stefanoleone992/fifa-22-complete-player-dataset).

- Original file: `players_22.csv`, containing 19,239 male players and 110 columns
- Included file: `argentina_players_22.csv`, containing 960 Argentina players and 14 relevant source columns
- Source snapshot: FIFA 22 Career Mode ratings, collected from SoFIFA
- Kaggle license: **CC0: Public Domain**
- Dataset retrieved: 31 October 2026
- [Official dataset metadata](https://www.kaggle.com/api/v1/datasets/view/stefanoleone992/fifa-22-complete-player-dataset)
- [Single-file download](https://www.kaggle.com/api/v1/datasets/download/stefanoleone992/fifa-22-complete-player-dataset/players_22.csv)

The included CSV is an extract, not an additional dataset. It keeps rows where `nationality_name == "Argentina"` from the single FIFA 22 male-player snapshot. It preserves the following original columns:

`sofifa_id`, `short_name`, `nationality_name`, `player_positions`, `age`, `height_cm`, `weight_kg`, `preferred_foot`, `pace`, `shooting`, `passing`, `dribbling`, `defending`, `physic`.

The notebook removes 96 players whose first listed position is goalkeeper, leaving 864 outfield players. It maps the first listed position to three broad role groups:

| Group | Position codes |
| --- | --- |
| Defender | CB, LB, RB, LWB, RWB |
| Midfielder | CDM, CM, CAM, LM, RM |
| Forward | ST, CF, LW, RW |

This ordering is taken directly from the position string. It is not a claim that the publisher certified a single primary position. Players can have several listed positions.

The model inputs are age, height, weight, preferred foot, and the six broad skill ratings. Names, IDs, nationality, and position fields are excluded from the inputs. Overall ratings, potential, team positions, and position-specific ratings are not included in the extract.

Height is in centimetres and weight is in kilograms. These are historical game ratings, not live match statistics, future performance, or a real scouting assessment. No missing values or duplicate players were artificially introduced.
