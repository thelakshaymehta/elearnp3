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



<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="JobGroupTypes.aspx.cs" Inherits="YourNamespace.JobGroupTypes" %>

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title>Job Group Types</title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <asp:GridView ID="GridView1" runat="server" AutoGenerateColumns="False">
                <Columns>
                    <asp:BoundField DataField="i_grouptype" HeaderText="Group Type" />
                    <asp:BoundField DataField="ch_groupname" HeaderText="Group Name" />
                    <asp:BoundField DataField="ti_priority" HeaderText="Priority" />
                    <asp:BoundField DataField="ch_ReportAssemblyLocation" HeaderText="Report Assembly Location" />
                    <asp:BoundField DataField="b_active" HeaderText="Active" />
                </Columns>
            </asp:GridView>
        </div>
    </form>
</body>
</html>
