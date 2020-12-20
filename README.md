# CastleCrashes
Steam 



## Structs
```cpp

class ULocalPlayer
{
public:
	char pad_0000[4]; //0x0000
	class ULocalPointer *localPointer; //0x0004
	char pad_0008[120]; //0x0008
}; //Size: 0x0080

class ULocalPointer
{
public:
	class UPlayerController *playerController; //0x0000
	char pad_0004[64]; //0x0004
}; //Size: 0x0044

class UPlayerController
{
public:
	char pad_0000[188]; //0x0000
	class UPlayerStates *PlayerStats; //0x00BC
	char pad_00C0[68]; //0x00C0
}; //Size: 0x0104

class UPlayerStates
{
public:
	char pad_0000[12]; //0x0000
	class UPlayerStats *CharacterStats; //0x000C
	char pad_0010[24]; //0x0010
	class UStats *PlayerStats; //0x0028
	char pad_002C[4056]; //0x002C
}; //Size: 0x1004

class UStats
{
public:
	char pad_0000[1960]; //0x0000
	int32_t level; //0x07A8
	char pad_07AC[60]; //0x07AC
	uint32_t XP; //0x07E8
	char pad_07EC[188]; //0x07EC
	uint32_t gold; //0x08A8
	char pad_08AC[25175]; //0x08AC
}; //Size: 0x6B03

class UPlayerStats
{
public:
	char pad_0000[18344]; //0x0000
	uint32_t strength; //0x47A8
	char pad_47AC[60]; //0x47AC
	uint32_t magic; //0x47E8
	char pad_47EC[60]; //0x47EC
	uint32_t defense; //0x4828
	char pad_482C[92]; //0x482C
	uint32_t speed; //0x4888
	char pad_488C[120]; //0x488C
}; //Size: 0x4904
```
## Setup LocalPlayer
```cpp

void LocalPlayer_Start()
{
	DWORD Module;

	Module = Utils.Memory.ResolveImport(L"castle.exe");
	LocalPlayer = *(ULocalPlayer**)(Module + 0x026A7D8);
}

```
