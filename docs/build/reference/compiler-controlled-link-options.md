---
title: Derleyici Denetimindeki LINK Seçenekleri
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: 21d0baccaf74fc08bb110b0ae9f8b7dc108abd6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561583"
---
# <a name="compiler-controlled-link-options"></a>Derleyici Denetimindeki LINK Seçenekleri

/C seçeneğini belirtmediğiniz sürece CL derleyici bağlantı otomatik olarak çağırır. CL bağlayıcı komut satırı seçenekleri ve bağımsız değişkenler üzerinde bazı denetim sağlar. Bağlantılandırmayı etkileyen özellikler CL, aşağıdaki tabloda özetlenmiştir.

|CL belirtimi|BAĞLANTI etkiler CL eylemi|
|----------------------|---------------------------------|
|.C, .cxx, .cpp veya .def dışındaki herhangi bir dosya adı uzantısı|Bir dosya adı bağlantısına giriş olarak geçirir|
|*filename*.def|/ Def geçirir:*filename*.def|
|/F*numarası*|Geçişleri /STACK:*numarası*|
|/FD*dosya adı*|Başarılı/pdb:*dosya adı*|
|/FE*dosya adı*|Başarılı/OUT:*dosya adı*|
|/FM*dosya adı*|Geçişleri/Map:*dosya adı*|
|/Gy|Paketlenmiş işlevler (Comdat'lar); oluşturur etkinleştirir işlev düzeyi bağlamayı|
|/LD|/ DLL geçirir|
|/ LDd|/ DLL geçirir|
|/link|Komut satırı geri kalanında LINK'e geçirir.|
|/MD veya/MT|Varsayılan kitaplık adını .obj dosyasına yerleştirir.|
|/ MDd veya/mtd|Varsayılan kitaplık adını .obj dosyasına yerleştirir. Simgenin tanımlar **_DEBUG**|
|/nologo|/ Nologo geçirir|
|/ ZD|/ Debug geçişleri|
|/Zı veya/z7|/ Debug geçişleri|
|/Zl|Varsayılan kitaplık adını .obj dosyasından atlar|

Daha fazla bilgi için [derleyici seçenekleri](../../build/reference/compiler-options.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)