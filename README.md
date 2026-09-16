# ag2 planovac

Verejne repo, ktore len spusta workflowy v sukromnom repe `mizitean/ag2_data`
(`zber.yml` 48x denne, `kontrola.yml` o 07:13 UTC). Retaz:

    cron-job.org (5 jobov, UTC)  --token planovac-dispatch-->  planovac.yml (tu)
                                 --token AG2_TOKEN-->           ag2_data: zber.yml / kontrola.yml

Preco takto: GitHub `schedule` nespustal ani na sukromnom (Free), ani na tomto verejnom repe
(16.9.2026). cron-job.org drzi len token na toto repo, kde nie su ziadne data ani hesla.

Tokeny, oba fine-grained PAT s platnostou 1 rok (obnovit ~september 2027):
- `planovac-dispatch` (Actions na ag2_planovac) -- ulozeny v cron-job.org v hlavicke jobov
- `AG2_TOKEN` (Actions na ag2_data) -- secret tohto repa

`tik.yml` je kanarik: keby GitHub cron niekedy nabehol, bude to vidiet v Actions.
