# Slime Rancher

1. [Unlimited Energy](#unlimited-energy)
2. [Unlimited Drone Station Battery](#unlimited-drone-station-battery)

## Unlimited Energy

Path:

    MonomiPark.SlimeRancher.DataModel/PlayerModel/SpendEnergy

Code:

```C#
public void SpendEnergy(float energy)
{
	this.energyRecoverAfter = this.worldModel.worldTime + 10.0;
}
```

## Unlimited Drone Station Battery

Path:

    {} -/DroneStationBattery/Update

Code:

```C#
public void Update()
{
	this.percentage = 1f;
	bool? flag = this.previousHasAny;
	bool flag2 = this.HasAny();
	if (!(flag.GetValueOrDefault() == flag2 & flag != null))
	{
		this.previousHasAny = new bool?(this.HasAny());
		if (this.onHasAnyChanged != null)
		{
			this.onHasAnyChanged();
		}
	}
}
```
