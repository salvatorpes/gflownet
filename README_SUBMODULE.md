# GFlowNet (forked submodule)

This directory is a **git submodule** pointing to a fork of:
https://github.com/alexhernandezgarcia/gflownet

Fork:
https://github.com/salvatorpes/gflownet

It is installed into the main Neurosynth project's Python environment.

The forked repository has a branch `neurosynth_fin` where my edits are and changes specific to this project are kept.

---

## One-time setup (already done - don't redo)
```bash
cd NeuroSynth-Fin

mkdir -p external
git submodule add https://github.com/salvatorpes/gflownet.git external/gflownet
git submodule update --init --recursive

git commit -m "Add gflownet as submodule"

cd external/gflownet
git remote add upstream https://github.com/alexhernandezgarcia/gflownet.git
git fetch upstream

git checkout -b neurosynth_fin
git push -u origin neurosynth_fin
```

## Pulling in upstream changes
```bash
cd external/gflownet
git checkout main
git fetch upstream
git merge upstream/main
git push origin main
```

## Pushing changes to my fork (neurosynth_fin branch)
```bash
cd external/gflownet
git checkout neurosynth_fin
# edit files
git commit -am "Describe changes"
git push origin neurosynth_fin
```

## Updating my branch with upstream changes
```bash
cd external/gflownet
git checkout neurosynth_fin
git fetch upstream
git merge upstream/main
# resolve conflicts if necessary
git push origin neurosynth_fin
```

## Updating this submodule reference in the main project
```bash
cd NeuroSynth-Fin
git add external/gflownet
git commit -m "Update gflownet submodule"
git push
```