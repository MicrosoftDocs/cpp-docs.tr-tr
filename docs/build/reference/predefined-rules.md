---
title: Önceden Tanımlanmış Kurallar
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 7a922a239306f10121791caa8f9f088cea88c019
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824004"
---
# <a name="predefined-rules"></a>Önceden Tanımlanmış Kurallar

Önceden tanımlanmış çıkarım kuralları NMAKE sağlanan komutlar ve Seçenekler makroları kullanın.

|Kural|Komut|Varsayılan<br /><br /> Eylem|Batch<br /><br /> Kural|Üzerinde çalıştığı platforma nmake|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$(AS) $(AFLAGS) $<|ML $<|Yok|x86|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ML /c $<|evet|x86|
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Yok|X64|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|evet|X64|
|.c.exe|$(CC) $(CFLAGS) $<|cl $<|Yok|tüm|
|.c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|evet|tüm|
|. cc.exe|$(CC) $(CFLAGS) $<|cl $<|Yok|tüm|
|. cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|evet|tüm|
|.cpp.exe|$(CPP) $(CPPFLAGS) $&LT;|cl $<|Yok|tüm|
|. cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|evet|tüm|
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|Yok|tüm|
|. cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|evet|tüm|
|. rc.res|$(RC) $(RFLAGS) /r $<|RC /r $<|Yok|tüm|

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarım Kuralları](inference-rules.md)
