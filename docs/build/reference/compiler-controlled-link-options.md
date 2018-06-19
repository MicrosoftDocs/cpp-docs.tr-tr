---
title: Derleyici denetimindeki bağlantı seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d99a05b5f9c4d97fd42328a41ad3fe054ab42cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372002"
---
# <a name="compiler-controlled-link-options"></a>Derleyici Denetimindeki LINK Seçenekleri
/C seçeneği belirtmediğiniz sürece CL derleyici bağlantı otomatik olarak çağırır. CL komut satırı seçenekleri ve bağımsız değişkenleri ile bağlayıcı üzerinde bazı denetim sağlar. CL içinde bağlantılandırmayı etkileyen özellikler aşağıdaki tabloda özetlenmiştir.  
  
|CL belirtimi|BAĞLANTI etkiler CL eylemi|  
|----------------------|---------------------------------|  
|.C, .cxx, .cpp veya .def dışındaki herhangi bir dosya adı uzantısına|BAĞLANTI için giriş olarak bir dosya adı geçirir|  
|*filename*.def|/ Def geçirir:*filename*.def|  
|/F*numarası*|Geçişleri /STACK:*numarası*|  
|/FD*dosya adı*|/ Pdb geçirir:*dosya adı*|  
|/FE*dosya adı*|Geçirir/OUT:*dosya adı*|  
|/FM*dosya adı*|/ Map geçişleri:*dosya adı*|  
|/Gy|Paketlenmiş işlevler (COMDATs); oluşturur etkinleştirir işlev düzeyi bağlantılandırma|  
|/LD|/ DLL geçirir|  
|/ LDd|/ DLL geçirir|  
|/link|Komut satırı geri kalanı bağlantı geçirir|  
|/MD veya/MT|Varsayılan kitaplık adını .obj dosyasına yerleştirir.|  
|/ MDd veya /MTd|Varsayılan kitaplık adını .obj dosyasına yerleştirir. Simgenin tanımlar **_DEBUG**|  
|/nologo|/ Nologo geçirir|  
|/ZD|/ Debug geçişleri|  
|/Zi veya /Z7|/ Debug geçişleri|  
|/Zl|Varsayılan kitaplık adını .obj dosyasından atlar|  
  
 Daha fazla bilgi için bkz: [derleyici seçenekleri](../../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)