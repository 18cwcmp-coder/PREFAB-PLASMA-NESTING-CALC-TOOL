# Pipe Nesting Planner v18 - Complete Feature List

## 📦 v18.2 - Current Version (December 6, 2025)

### ✅ Core Features (from v17)
- **Project Management** - Create and manage multiple projects
- **Material Segregation** - CS SCH40, SS SCH10, HDG, CS Med Fire
- **Cut Piece Entry** - Add pipe pieces with full specifications
- **Nesting Engine** - Optimize cutting sequences with 25mm gap
- **CSV Export** - DTPS-compatible export format
- **Data Backup** - JSON import/export
- **Spool Images** - Upload/paste images for each spool
- **Piece Filtering** - Filter table by spool, size, material, type
- **Edit Pieces** - Click to edit, delete functionality

### ✨ NEW in v18.0 - Image Zoom
- **Click to Enlarge** - Click spool preview image for full-screen view
- **Modal Overlay** - Dark background, clean presentation
- **Easy Close** - Click × or outside image to close
- **Hover Effects** - Visual feedback on clickable images

### ✨ NEW in v18.1 - Multi-Branch System
- **Multiple Branches per Piece** - Add unlimited branch connections
- **Distance Tracking** - Each branch measured from same end point
- **Branch Sizes** - DN25 to DN300 support
- **Rotational Angles**:
  - **Preset:** 0° (top), 90° (right), 180° (bottom), 270° (left)
  - **Custom:** Any angle 0-360° (e.g., 45°, 135°, 225°)
- **Branch List Management** - Add, view, delete individual branches
- **Auto-Sort** - Branches sorted by distance (closest first)
- **Table Display**:
  - Single branch: `DN65@245mm/0°`
  - Multiple: `3 branches` (compact)
- **CSV Export Format** - Semicolon-separated: `DN65@245/0°;DN50@890/90°`
- **Legacy Support** - Old single-branch format still works

### ✨ NEW in v18.2 - Logo & Branding
- **Larger Logo** - 20% increase (60px → 72px)
- **Clean Display** - Removed white padding around logo
- **Fixed Title** - Removed corrupted "â€"" character
- **Professional Look** - Logo displays with clean black border only

---

## 📊 Complete Workflow

### 1. Project Setup
```
Create Project → Set stock length → Select materials → Save
```

### 2. Add Pieces
```
Select Project → Enter spool details → Set dimensions
  ↓
  If main piece + straight:
    → Add branch connections (optional)
    → Distance + Size + Angle for each branch
  ↓
Upload/paste spool image (optional) → Save piece
```

### 3. Generate Nests
```
Select Project → Filter by material/size → Generate nests
  ↓
View optimization results → See stock requirements
```

### 4. Export
```
Download CSV → Import to DTPS/Steel Cut Generator
  ↓
All piece data + branch connections exported
```

---

## 🎯 Technical Specifications

### Data Structure
```javascript
piece = {
  id: "abc123",
  projectCode: "DC-001",
  spoolNo: "SP-003",
  spoolSubNo: "SP-003A",
  isMainSpool: true,
  pieceLength: 2500,
  pipeSize: "DN125",
  materialFamily: "CS_SCH40",
  pipeworkType: "Straight",
  branchConnections: [
    { distance: 245, size: "DN65", angle: 0 },
    { distance: 890, size: "DN50", angle: 90 },
    { distance: 1200, size: "DN40", angle: 180 }
  ],
  endPrepStart: "Bevel",
  endPrepEnd: "RollGroove",
  weldPriority: 3,
  paintRequired: false,
  imageData: "data:image/png;base64,..."
}
```

### Nesting Algorithm
- **Grouping:** Project → Material → Size
- **Sorting:** Priority → Date → Spool number
- **Placement:** Best-fit decreasing with 25mm gap enforcement
- **Optimization:** Minimizes offcuts per 6m stock length

### CSV Export Columns
```
NestId, Project, Material, PipeSize, StockLength_mm,
PieceOrder, Spool, Sub, DrawingRef, PieceLength_mm,
Start_mm, End_mm, WeldPriority, PipeType, 
EndPrepStart, EndPrepEnd, BranchConnections
```

---

## 🎨 User Interface

### Tabs
1. **Project Setup** - Define projects and materials
2. **Cut Piece Entry** - Add and edit pipe pieces
3. **Nesting** - Generate and view optimization results
4. **Data View / Export** - Backup and restore data

### Key UI Elements
- **Dark Theme** - Easy on the eyes for long sessions
- **Grid Layouts** - Responsive, clean organization
- **Filter Inputs** - Quick search in tables
- **Visual Feedback** - Hover states, active indicators
- **Modal Dialogs** - Image zoom, confirmations

---

## 📱 Browser Support
- **Chrome/Edge** - Full support ✅
- **Firefox** - Full support ✅
- **Safari** - Full support ✅
- **Mobile** - Responsive, touch-friendly ✅

---

## 💾 Data Storage
- **localStorage** - Browser-based, no backend needed
- **Storage Key:** `pipeNestingPlanner_v18`
- **Capacity:** ~10MB typical (thousands of pieces)
- **Backup:** JSON export/import for safety

---

## 🚀 Performance
- **File Size:** 89KB (single HTML file)
- **Load Time:** < 1 second
- **Dependencies:** None (standalone)
- **Offline:** Works without internet connection

---

## 🎓 User Training

### Basic User (10 minutes)
- Create project
- Add pieces
- Upload images
- Generate nests
- Export CSV

### Advanced User (20 minutes)
- Multi-branch connections
- Angle orientations
- Custom angles
- Filtering and editing
- Data backup/restore

---

## 📈 Statistics

### What Users Can Track
- Pieces per project
- Stock length requirements
- Total offcuts per material/size
- Branch connections per piece
- Utilization rates

### Example Dashboard Data
```
Project: DC-001
Pieces: 247
Stock Lengths Needed: 42
Total Offcuts: 3,840mm (15% waste)
Branches: 89 connections across 31 main pieces
```

---

## 🔮 Roadmap (Next Features)

### Planned for v18.3
- [ ] DTPS/Steel Cut Generator Tab
- [ ] Direct robot program (.csr) export
- [ ] Markdown (.md) export for documentation
- [ ] Branch data integration with robot programs

### Future Enhancements
- [ ] Visual nesting preview (graphical)
- [ ] 3D pipe visualization
- [ ] Cloud sync (optional)
- [ ] Multi-user collaboration
- [ ] Barcode/QR code generation
- [ ] Mobile app version

---

## 📞 Support & Documentation

### Available Docs
- ✅ Multi-Branch Implementation Summary
- ✅ Multi-Branch Quick Reference
- ✅ Logo Update Summary
- ✅ Backup Summary
- ✅ This Complete Feature List

### Quick Links
- **Latest Backup:** pipe_nesting_app_v18_BACKUP_logo_updated.html
- **Working File:** pipe_nesting_app_v18_FINAL.html
- **All Backups:** /mnt/user-data/outputs/*BACKUP*.html

---

**Version:** v18.2  
**Status:** ✅ Production Ready  
**Last Updated:** December 6, 2025  
**Total Features:** 25+ major features across 4 main tabs
