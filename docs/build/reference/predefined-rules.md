---
description: 'Daha fazla bilgi edinin: önceden tanımlanmış kurallar'
title: Önceden Tanımlanmış Kurallar
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 302c649980050764d1bb2f0e9a43b785d0175a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225836"
---
# <a name="predefined-rules"></a>Önceden Tanımlanmış Kurallar

Önceden tanımlanmış çıkarım kuralları NMAKE tarafından sağlanan komut ve seçenek makrolarını kullanır.

|Kural|Komut|Varsayılan<br /><br /> eylem|Batch<br /><br /> Kural|Platform NMAKE üzerinde çalışır|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$ (AS) $ (AFLAGS) $<|ml $<|hayır|x86|
|. asm. obj|$ (AS) $ (AFLAGS)/c $<|ml/c $<|evet|x86|
|.asm.exe|$ (AS) $ (AFLAGS) $<|ML64 $<|hayır|x64|
|. asm. obj|$ (AS) $ (AFLAGS)/c $<|ML64/c $<|evet|x64|
|.c.exe|$ (CC) $ (CFLAGS) $<|CL $<|hayır|tümü|
|. c. obj|$ (CC) $ (CFLAGS)/c $<|cl/c $<|evet|tümü|
|.cc.exe|$ (CC) $ (CFLAGS) $<|CL $<|hayır|tümü|
|. CC. obj|$ (CC) $ (CFLAGS)/c $<|cl/c $<|evet|tümü|
|.cpp.exe|$ (CPP) $ (CPPFLAGS) $<|CL $<|hayır|tümü|
|. cpp. obj|$ (CPP) $ (CPPFLAGS)/c $<|cl/c $<|evet|tümü|
|.cxx.exe|$ (CXX) $ (CXXFLAGS) $<|CL $<|hayır|tümü|
|. cxx. obj|$ (CXX) $ (CXXFLAGS)/c $<|cl/c $<|evet|tümü|
|. rc. res|$ (RC) $ (RFLAGS)/r $<|RC/r $<|hayır|tümü|

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarım kuralları](inference-rules.md)
