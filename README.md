using System;
using System.Web.UI;

public partial class JobGridPage : Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
    }

    protected void btnGetKeyValue_Click(object sender, EventArgs e)
    {
        if (int.TryParse(txtRegistryKey.Text, out int si_registryKey))
        {
            JobGridDAL dal = new JobGridDAL();
            string keyValue = dal.GetKeyValue(si_registryKey);
            lblKeyValue.Text = keyValue;
        }
        else
        {
            lblKeyValue.Text = "Invalid Registry Key.";
        }
    }
}
