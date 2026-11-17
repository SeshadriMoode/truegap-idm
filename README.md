# Equilibrium gap inflation and string stability of a true-gap cooperative intelligent driver model

Code for the manuscript of that title. Run the commands from this folder, so that `idm_truegap` is the package on the path.

```text
pip install -r requirements.txt
python -m idm_truegap.experiments
python -m idm_truegap.figures
python -m idm_truegap.revision
python -m idm_truegap.author_checks
python -m idm_truegap.openacc
```

`experiments` writes the controlled tables under `results/truegap/` and does not write every figure. `figures` draws the figures that read those tables. The later modules write the remaining figures named below.

| Output | Module |
|---|---|
| Controlled tables, and the figures drawn from them | `experiments`, then `figures` |
| `fig9_openacc` | `openacc` |
| `fig10_delay_margin`, wave comfort numbers, barrier values at braking ratio 0.4, six-vehicle tail ratio | `revision` |
| `fig11_barrier`, `fig12_blend_relax`, root stability | `author_checks` |

The parameter set of the controlled experiments is the default in `idm_truegap/params.py`.

The OpenACC calculation fits only the classical intelligent-driver acceleration and time gap. The odd-numbered runs are held out before the fit and do not enter the loss. It reads `data/openacc/part7.csv` from the Ispra–Casale campaign in OpenACC, DOI `10.2905/JRC.KMH3D00`: <https://jeodpp.jrc.ec.europa.eu/ftp/jrc-opendata/TransportExpData/JRCDBT0001/LATEST/Casale/part7.csv>. That file is not in this folder. Place the csv at `data/openacc/part7.csv` before running `openacc`.
