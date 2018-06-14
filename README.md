# bmp180-powershell

```
try
{
	Add-Type -Path "$(Resolve-Path .)/bmp180-netcore.dll"

	$bmp180 =  [bmp180_netcore.BMP180]::new()

	"$($bmp180.ReadTemperature() / 10)°C"
	"$($bmp180.ReadPressure()) bar"
	"$($bmp180.ReadAltitude().ToString("#.000")) mts"
	"$($bmp180.ReadSeaAltitude()) pa"
}
catch
{
	Write-OutPut $_.Exception.Message
}
```

