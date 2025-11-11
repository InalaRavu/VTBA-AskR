# Reset Customer360 (C360) Pipeline — Overview

Purpose
- Describe controlled steps to reset the Customer360 pipeline after failures or state corruption.

Scope
- Applies to pipeline components that maintain state. Does not cover full data reprocessing policies.

Impact
- Pipeline downtime for the target environment.
- Potential duplicate or missing records if reprocessing is not coordinated.
- Coordinate with teammates before proceeding.

Prerequisites
- Current ADF environment (prod/stage/dev) identified (e.g. Prod environment:adf-p-10007289-001-customer360)

Safety & rollback
- If reset fails, immediately notify da.dataengineeringteam@atlascopco.com.

Reset procedure (high level)
1. Logon to impacted ADF (incase PROD: adf-p-10007289-001-customer360).
2. Click on Author on left hand Menu
3. Expand "customer_360" folder
4. Click on pipeline "pipe_reset_orchestration_status"
5. Click on "Add Trigger" and the click "Trigger Now"
6. Monitor the pipeline for it's completion

```

Verification checklist
- Navigate to location on storage: 3_Refined/customer360/trigger/orchestration/trigger_file.csv
- Check if the status is changed to "fixed"
- Inform teammates.

Common issues & quick fixes
- Pipeline status cannot be reset using above procedure incase it is cancelled manually during the previous run.
- In such case, navigate to 3_Refined/customer360/trigger/orchestration/trigger_file.csv and manually change the status to "fixed"

Notes
- For learning, check the conditions added on pipeline activities.

Footer
- Keep this file updated with environment-specific commands and contact names.
