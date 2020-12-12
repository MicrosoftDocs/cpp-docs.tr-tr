---
description: 'Daha fazla bilgi edinin: Compiler-Controlled bağlantı seçenekleri'
title: Derleyici Denetimindeki LINK Seçenekleri
ms.date: 11/04/2016
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: 86f03f53fe19f6788528dca421fb6030289fca99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178985"
---
# <a name="compiler-controlled-link-options"></a>Derleyici Denetimindeki LINK Seçenekleri

,/C seçeneğini belirtmediğiniz takdirde CL derleyicisi bağlantıyı otomatik olarak çağırır. CL, bağlayıcı üzerinde komut satırı seçenekleri ve bağımsız değişkenler aracılığıyla bir denetim sağlar. Aşağıdaki tablo, bağlamayı etkileyen CL 'deki özellikleri özetler.

|CL belirtimi|BAĞLANTıYı etkileyen CL eylemi|
|----------------------|---------------------------------|
|. C,. cxx,. cpp veya. def dışında herhangi bir dosya adı uzantısı|Bir dosya adını bağlamak için girdi olarak geçirir|
|*filename*. def|/DEF:*filename*. def geçirir|
|/F *numarası*|/STACK:*numara* geçirir|
|/FD *dosya adı*|/PDB:*filename* komutunu geçirir|
|/Fe *dosya adı*|/OUT:*filename* geçişlerini yapar|
|/FM *dosya adı*|Geçirir/MAP:*filename*|
|/GY|Paketlenmiş işlevler (Combats) oluşturur; işlev düzeyinde bağlamayı etkinleştirilir|
|/LD|/DLL geçirir|
|/LDd|/DLL geçirir|
|/link|Komut satırının geri kalanını BAĞLANTıYA geçirir|
|/MD veya/MT|. Obj dosyasına varsayılan bir kitaplık adı koyar|
|/MDd veya/MTd|. Obj dosyasına varsayılan bir kitaplık adı koyar. Sembol **_DEBUG** tanımlar|
|/nologo|,/NOLOGO geçirir|
|/ZD|Geçirilir|
|/Zi veya/Z7|Geçirilir|
|/Zl|Varsayılan kitaplık adını. obj dosyasından atlar|

Daha fazla bilgi için bkz. [MSVC derleyici seçenekleri](compiler-options.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
