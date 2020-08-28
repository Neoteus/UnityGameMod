# Guide

## Contents

1. [Unlimited Energy](#unlimited-energy)
2. [Unlimited Drone Station Battery](#unlimited-drone-station-battery)

## Unlimited Energy

Find the method `SpendEnergy` at:

    MonomiPark.SlimeRancher.DataModel/PlayerModel/SpendEnergy

After modifying:

```C#
public void SpendEnergy(float energy)
{
	this.energyRecoverAfter = this.worldModel.worldTime + 10.0;
}
```

## Unlimited Drone Station Battery

Find the method `Update` at:

    {} -/DroneStationBattery/Update

After modifying:

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
