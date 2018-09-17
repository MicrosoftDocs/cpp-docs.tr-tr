---
title: Önceden tanımlanmış kurallar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a34d3d0a601b2e160f988e0fed34a630612d839
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719257"
---
# <a name="predefined-rules"></a>Önceden Tanımlanmış Kurallar

Önceden tanımlanmış çıkarım kuralları NMAKE sağlanan komutlar ve Seçenekler makroları kullanın.

|Kural|Komut|Varsayılan<br /><br /> Eylem|Batch<br /><br /> Kural|Üzerinde çalıştığı platforma nmake|
|----------|-------------|------------------------|--------------------|----------------------------|
|. asm.exe|$(AS) $(AFLAGS) $&LT;|ML $<|Yok|x86|
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML /c $<|Evet|x86|
|. asm.exe|$(AS) $(AFLAGS) $&LT;|ml64 $<|Yok|X64|
|. asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|Evet|X64|
|. c.exe|$(CC) $(CFLAGS) $&LT;|cl $<|Yok|tüm|
|. c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|Evet|tüm|
|. cc.exe|$(CC) $(CFLAGS) $&LT;|cl $<|Yok|tüm|
|. cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|Evet|tüm|
|. cpp.exe|$(CPP) $(CPPFLAGS) $&LT;|cl $<|Yok|tüm|
|. cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|Evet|tüm|
|. cxx.exe|$(CXX) $(CXXFLAGS) $&LT;|cl $<|Yok|tüm|
|. cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|Evet|tüm|
|. rc.res|$(RC) $(RFLAGS) /r $<|RC /r $<|Yok|tüm|

## <a name="see-also"></a>Ayrıca Bkz.

[Çıkarım Kuralları](../build/inference-rules.md)