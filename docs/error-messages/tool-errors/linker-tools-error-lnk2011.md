---
title: Bağlayıcı Araçları Hatası LNK2011
ms.date: 11/04/2016
f1_keywords:
- LNK2011
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
ms.openlocfilehash: c8c62da6c1b4ea856f7a0854b998946893f2be63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299100"
---
# <a name="linker-tools-error-lnk2011"></a>Bağlayıcı Araçları Hatası LNK2011

önceden derlenen nesne bağlanmadı; Görüntü çalışmayabilir

Önceden derlenmiş üst bilgiler kullanırsanız, tüm önceden derlenmiş üst bilgileri ile oluşturulan nesne dosyaları içinde bağlanmalıdır bağlantı gerektirir. Diğer kaynak dosyalarla kullanım için önceden derlenmiş bir üst bilgi oluşturmak için kullandığınız bir kaynak dosyası varsa, önceden derlenmiş üst bilgi ile birlikte oluşturulan nesne dosyası artık eklemeniz gerekir.

Örneğin, diğer kaynak dosyalarla kullanım için önceden derlenmiş bir üst bilgi oluşturulacak STUB.cpp adlı bir dosya derlerseniz STUB.obj ile bağlanmanız gerekir veya bu hatayı alırsınız. Aşağıdaki komut satırları, bir satırı PROG2.cpp PROG1.cpp ile iki ve üç satır içinde kullanılan COMMON.pch önceden derlenmiş üst bilgi oluşturmak için kullanılır. STUB.cpp içeren yalnızca dosyanın `#include` satırları (aynı `#include` PROG1.cpp ve PROG2.cpp olduğu gibi) ve yalnızca önceden derlenmiş üstbilgileri oluşturmak için kullanılır. Son satırında STUB.obj içinde LNK2011 önlemek için bağlı olmalıdır.

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```