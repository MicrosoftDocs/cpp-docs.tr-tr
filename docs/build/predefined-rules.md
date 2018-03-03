---
title: "Önceden tanımlanmış kurallar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3be1c8eea7b11f60e9ce9a7cbf5ebc0c2b99b698
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="predefined-rules"></a>Önceden Tanımlanmış Kurallar
Önceden tanımlanmış çıkarım kuralları NMAKE sağlanan komutu ve Seçenekler makroları kullanın.  
  
|Kural|Komut|Varsayılan<br /><br /> Eylem|Toplu işlem<br /><br /> Kural|Platform nmake çalışır|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|. asm.exe|$(AS) $(AFLAGS) $<|ML $<|Yok|x86|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML /c $<|Evet|x86|  
|. asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Yok|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|Evet|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. c.exe|$(CC) $(CFLAGS) $<|cl $<|Yok|tüm|  
|. c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|Evet|tüm|  
|. cc.exe|$(CC) $(CFLAGS) $<|cl $<|Yok|tüm|  
|. cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|Evet|tüm|  
|. cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|Yok|tüm|  
|. cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|Evet|tüm|  
|. cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|Yok|tüm|  
|. cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|Evet|tüm|  
|. rc.res|$(RC) $(RFLAGS) /r $<|RC /r $<|Yok|tüm|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım Kuralları](../build/inference-rules.md)