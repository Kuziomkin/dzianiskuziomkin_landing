# Plan: Update BA to Data Analyst Skills Roadmap

This plan outlines the changes required to refine the "BA to Data Analyst" skills roadmap on `ba-to-data.html`. It includes adding a seventh skill group for Data Governance & MDM, de-duplicating modeling terminology, and incorporating strategic skills like KPI storytelling and environment strategy.

## 1. Content & Terminology Updates
- **Data Requirements & Mapping** (formerly BA Artifacts):
    - Rename "Data Modeling" to **"Conceptual Data Models"** to distinguish from analytical modeling.
- **Analytical Data Modeling** (formerly Data Modeling):
    - Update group name to clarify the focus on warehouse design.
- **SQL & Analytics**:
    - Add **"KPI Documentation & Storytelling"**.
    - Add **"Statistical Thinking"** to the visual mind map.
- **Data Platforms**:
    - Add **"Environment Strategy (Dev/Prod)"**.
- **ETL & ELT**:
    - Add **"Data Quality & Testing"** to the visual mind map.
- **Data Governance & MDM** (New Group):
    - Items: Master Data Management (MDM), Reference Data, Data Quality Framework, Data Privacy & Ethics, Data Stewardship, Metadata Management.

## 2. Visual Mind Map Re-design (SVG & CSS)
- **Layout Change**: Shift from a 3/3 balanced layout to a **3-left / 4-right** layout to accommodate the 7th branch.
- **Coordinates (Right Side)**:
    - **Analytical Data Modeling (⑤)**: Move to `top: 80px`.
    - **Data Requirements & Mapping (①)**: Move to `top: 300px`.
    - **Data Governance & MDM (⑦)**: Add at `top: 520px` (Color: `#A855F7`).
    - **SQL & Analytics (②)**: Move to `top: 740px`.
- **Sub-node Spacing**: Adjust vertical spacing from 40px to 35px to fit more items within the height constraints.
- **SVG Paths**: Update cubic bezier paths to connect the center node to the 4 right-side branches.

## 3. Section Descriptions (HTML)
- Update all existing `<div class="branch-section">` headers and bullet points.
- Add the new **Data Governance & MDM** section with detailed descriptions of MDM, Reference Data, and Stewardship.
- Refine the **SQL & Analytics** section to include the importance of KPI storytelling and statistical significance.

## 4. Verification Plan
- **Visual Check**: Open the updated HTML in a browser to ensure the mind map lines connect correctly and text does not overlap.
- **Content Check**: Verify that "Data Modeling" is now clearly split into "Conceptual" (BA side) and "Analytical" (Engineering side).
- **Responsive Check**: Ensure the horizontal scroll on mobile still functions correctly with the 7 branches.
