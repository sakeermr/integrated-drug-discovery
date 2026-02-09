# 🧬 Integrated Drug Discovery Pipeline

**Automated Trac + PharmacoNet Integration for Cannabinoid-Protein Target Discovery**

---

## 🎯 Overview

This repository provides a complete automated workflow that integrates two drug discovery tools:

1. **Trac** - PDB ligand similarity screening
2. **PharmacoNet** - Pharmacophore modeling and reverse screening

The orchestrator workflow automatically:
- Triggers Trac screening to find top PDB targets
- Passes results to PharmacoNet for pharmacophore modeling
- Performs reverse screening
- Combines all results into a single downloadable package

---

## ⚡ Quick Start

### 1. Prepare Input File

Place your cannabinoid compounds in `input/input_chemicals.csv`:

```csv
Name,SMILES,Plant,Category
THC,CCCCCC1=CC(=C2[C@@H]3C=C(CC[C@H]3C(OC2=C1)(C)C)C)O,Cannabis sativa,Cannabinoid
CBD,CCCCCC1=CC(=C(C(=C1)O)[C@@H]2C=C(CC[C@H]2C(=C)C)C)O,Cannabis sativa,Cannabinoid
```

### 2. Run the Pipeline

1. Go to **Actions** tab
2. Select: **"Complete Drug Discovery Pipeline"**
3. Click: **"Run workflow"**
4. Configure:
   - Input file: `input_chemicals.csv`
   - Top targets: `10`
5. Click: **"Run workflow"**

### 3. Wait & Download

- **Runtime**: ~1 hour 10 minutes
- **Download**: `complete-pipeline-results-XX` artifact

---

## 📊 What You Get

```
complete-pipeline-results/
├── trac-screening/          # PDB screening results
├── pharmaconet-models/      # Pharmacophore models (.pm, .pse)
├── screening-results/       # Reverse screening predictions
├── logs/                    # Complete processing logs
└── PIPELINE_SUMMARY.md      # Summary report
```

---

## 🔗 Connected Repositories

This orchestrator integrates:

- **Trac**: https://github.com/sakeermr/Trac
  - Workflow: `molecular-similarity-workflow-final.yml`
  - Runtime: ~2 minutes
  
- **PharmacoNet**: https://github.com/sakeermr/Tracmypdb_pharmaconet_new
  - Workflow: `reverse_screening.yml`
  - Runtime: ~1 hour 7 minutes

---

## 📋 Requirements

- Active GitHub account
- Input chemicals in CSV format with SMILES
- Both Trac and PharmacoNet repositories accessible

---

## 🚀 How It Works

```
Input Chemicals (SMILES)
         ↓
    [TRAC SCREENING]
    Finds top 10 PDB targets per chemical
         ↓
    [PharmacoNet MODELING]
    Generates pharmacophore models
         ↓
    [REVERSE SCREENING]
    Screens chemicals vs models
         ↓
    Complete Results Package
```

---

## 📖 Documentation

- **Quick Start**: See above
- **Troubleshooting**: Check workflow logs
- **Results Guide**: See PIPELINE_SUMMARY.md in results

---

## 🎓 Citation

If you use this pipeline, please cite:

**Trac**: Standard Seed Corporation - Internal Tool

**PharmacoNet**:
```bibtex
@article{seo2024pharmaconet,
  title={PharmacoNet: deep learning-guided pharmacophore modeling 
         for ultra-large-scale virtual screening},
  author={Seo, Seonghwan and Kim, Woo Youn},
  journal={Chemical Science},
  year={2024},
  publisher={Royal Society of Chemistry}
}
```

---

## 📞 Support

For issues:
1. Check workflow logs in Actions tab
2. Verify both Trac and PharmacoNet workflows work independently
3. Review artifact names match expected values

---

## 📝 License

MIT License

---

**Version**: 1.0  
**Last Updated**: 2026-02-09  
**Status**: Production Ready ✅
