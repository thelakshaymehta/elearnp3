CREATE PROCEDURE sp_GetJobGroupTypes
AS
BEGIN
    SELECT 
        i_grouptype, 
        ch_groupname, 
        ti_priority, 
        ch_ReportAssemblyLocation, 
        b_active
    FROM 
        JobGrid.dbo.JOBGROUPTYPES
END
