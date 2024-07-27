using System;
using System.Data;
using System.Data.SqlClient;

public class JobGridDAL
{
    private string connectionString = "your_connection_string_here";

    public string GetKeyValue(int si_registryKey)
    {
        string keyValue = string.Empty;

        using (SqlConnection conn = new SqlConnection(connectionString))
        {
            using (SqlCommand cmd = new SqlCommand("sp_GetJobGridRegisteryAssesment", conn))
            {
                cmd.CommandType = CommandType.StoredProcedure;
                cmd.Parameters.AddWithValue("@si_registryKey", si_registryKey);

                conn.Open();

                using (SqlDataReader reader = cmd.ExecuteReader())
                {
                    if (reader.Read())
                    {
                        keyValue = reader["vch_keyvalue"].ToString();
                    }
                }
            }
        }

        return keyValue;
    }
}
