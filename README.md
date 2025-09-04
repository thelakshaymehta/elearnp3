using (var reader = await command.ExecuteReaderAsync())
{
    if (await reader.ReadAsync())
    {
        charge = reader.GetDecimal(reader.GetOrdinal("CHARGE"));
    }
}

Console.WriteLine($"CHARGE = {charge}");