# ag2 planovac

Verejne repo, ktore len spusta workflowy v sukromnom repe `mizitean/ag2_data`
(`zber.yml`, `kontrola.yml` o 07:13 UTC). Retaz:

    cron-job.org (tik kazdych 10 min + kontrola, UTC)
        --token planovac-dispatch-->  planovac.yml (tu): brana
        --token AG2_TOKEN-->          ag2_data: zber.yml / kontrola.yml

Brana (od 11.10.2026): precita `stav.json` z ag2_data a spusti `zber.yml`, len ked
`dalsi_poll` uz nastal (pocita ho `poll.dalsi_poll` v ag2_data z cakajucich behov,
intervalu modelu a casov prichodu naucenych z logu). Minuty Actions sa uctuju za job,
takze sa plati len za dopyt, ktory ma co stiahnut. `vynutit=true` branu obide.

Preco takto: GitHub `schedule` nespustal ani na sukromnom (Free), ani na tomto verejnom repe
(16.9.2026). cron-job.org drzi len token na toto repo, kde nie su ziadne data ani hesla.
Rozvrh tikov je kod: `rozvrh.py` v ag2_data.

Tokeny, oba fine-grained PAT s platnostou 1 rok (obnovit ~september 2027):
- `planovac-dispatch` (Actions na ag2_planovac) -- ulozeny v cron-job.org v hlavicke jobov
- `AG2_TOKEN` (ag2_data: Actions read/write, Contents read) -- secret tohto repa

`tik.yml` je kanarik: keby GitHub cron niekedy nabehol, bude to vidiet v Actions.
