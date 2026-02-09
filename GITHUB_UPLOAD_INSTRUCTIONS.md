# 🎯 STEP-BY-STEP: Upload Files to New Repository

## 📋 WHAT YOU HAVE:

All files ready in the `NEW_REPO` folder:

```
NEW_REPO/
├── .github/
│   └── workflows/
│       └── complete_pipeline_orchestrator.yml  ← Main workflow
├── input/
│   └── input_chemicals_template.csv            ← Template
├── scripts/                                     ← Helper scripts
│   ├── extract_top_pdbs.py
│   ├── batch_modeling_parallel.py
│   ├── reverse_screening_batch.py
│   └── generate_summary_report.py
├── .gitignore                                   ← Git config
├── README.md                                    ← Documentation
└── UPLOAD_GUIDE.md                             ← This file
```

---

## 🚀 METHOD 1: Upload via GitHub Website (EASIEST!)

### Step 1: Create Repository

1. Go to: https://github.com/new
2. Fill in:
   - Repository name: `integrated-drug-discovery`
   - Description: `Automated Trac + PharmacoNet Pipeline`
   - Public: ✅
   - Add README: ✅
   - Add .gitignore: Python ✅
3. Click: **"Create repository"**

### Step 2: Upload Workflow File

1. In your new repo, click: **"Add file"** → **"Create new file"**
2. In the filename box, type: `.github/workflows/complete_pipeline_orchestrator.yml`
   - GitHub will create the folders automatically!
3. Open `NEW_REPO/.github/workflows/complete_pipeline_orchestrator.yml` on your computer
4. Copy ALL the contents
5. Paste into GitHub's editor
6. Scroll down
7. Click: **"Commit new file"**

✅ **Workflow added!**

### Step 3: Upload Input Template

1. Click: **"Add file"** → **"Create new file"**
2. Type filename: `input/input_chemicals_template.csv`
3. Open `NEW_REPO/input/input_chemicals_template.csv` on your computer
4. Copy contents and paste
5. Click: **"Commit new file"**

✅ **Input folder created!**

### Step 4: Create Your Actual Input File

1. Click: **"Add file"** → **"Create new file"**
2. Type filename: `input/input_chemicals.csv`
3. Paste your cannabinoid data:

```csv
Name,SMILES,Plant,Category
THC,CCCCCC1=CC(=C2[C@@H]3C=C(CC[C@H]3C(OC2=C1)(C)C)C)O,Cannabis sativa,Cannabinoid
CBD,CCCCCC1=CC(=C(C(=C1)O)[C@@H]2C=C(CC[C@H]2C(=C)C)C)O,Cannabis sativa,Cannabinoid
delta9-Tetrahydrocannabinolic acid,CCCCCC1=CC2=C([C@@H]3C=C(CC[C@H]3C(O2)(C)C)C)C(=C1C(=O)O)O,Cannabis sativa,Cannabinoid
```

4. Click: **"Commit new file"**

✅ **Ready to run!**

### Step 5: (Optional) Upload Scripts

**Only if you want the helper scripts:**

1. Click: **"Add file"** → **"Upload files"**
2. Navigate to `NEW_REPO/scripts/` on your computer
3. Select all 4 `.py` files
4. Drag and drop into GitHub
5. Make sure it says: `scripts/` in the path
6. Click: **"Commit changes"**

✅ **Scripts added!**

---

## 🎯 METHOD 2: Drag and Drop All at Once

### Step 1: Create Repository (same as Method 1)

### Step 2: Upload Everything

1. Go to your new repo
2. Click: **"uploading an existing file"** link
3. Open the `NEW_REPO` folder on your computer
4. Select ALL files and folders
5. Drag into GitHub's upload area
6. Wait for upload (should be quick, ~100KB total)
7. Scroll down
8. Click: **"Commit changes"**

✅ **Everything uploaded at once!**

---

## ✅ VERIFY YOUR UPLOAD:

After uploading, your repository should show:

```
Repository Files:
✅ .github/workflows/complete_pipeline_orchestrator.yml
✅ input/input_chemicals.csv
✅ input/input_chemicals_template.csv
✅ README.md
✅ .gitignore
✅ scripts/ (4 Python files) - Optional
```

---

## 🚀 NOW RUN THE WORKFLOW:

1. Click: **"Actions"** tab
2. You should see: **"Complete Drug Discovery Pipeline (Trac → PharmacoNet)"**
3. Click on it
4. Click: **"Run workflow"** button (right side)
5. Configure:
   - Branch: `main`
   - Input chemicals file: `input_chemicals.csv`
   - Number of targets: `10`
6. Click: **"Run workflow"** (green button)

**Wait ~1 hour 10 minutes for results!** ⏱️

---

## 📥 DOWNLOAD RESULTS:

After completion:

1. Go to the completed workflow run
2. Scroll down to **"Artifacts"**
3. Download: `complete-pipeline-results-XX`
4. Extract the ZIP file
5. Review your results!

---

## 🎉 YOU'RE DONE!

Your complete integrated drug discovery pipeline is ready to use!

**Inputs**: Cannabinoid SMILES  
**Outputs**: PDB targets + Pharmacophore models + Screening predictions  
**Runtime**: ~1 hour  
**Automation**: 100% ✅

---

## 💡 TIPS:

### Tip 1: Test Run
First time? Use just 2-3 chemicals to test the pipeline.

### Tip 2: Multiple Runs
The workflow can be run multiple times with different inputs.

### Tip 3: Results Storage
Download artifacts before they expire (default: 90 days).

### Tip 4: Check Individual Workflows
While running, you can monitor:
- Trac: https://github.com/sakeermr/Trac/actions
- PharmacoNet: https://github.com/sakeermr/Tracmypdb_pharmaconet_new/actions

---

## 🆘 NEED HELP?

If you get stuck:

1. **Workflow not appearing?**
   - Wait 10 seconds after upload
   - Refresh the Actions page
   - Make sure file is in `.github/workflows/`

2. **Workflow fails?**
   - Check that both Trac and PharmacoNet repos work independently
   - Verify workflow names are correct
   - Review error logs in the failed run

3. **No results?**
   - Make sure workflow completed successfully
   - Check Artifacts section at bottom of run page
   - Artifacts expire after retention period

---

**Happy Drug Discovery!** 🧬🔬✨
