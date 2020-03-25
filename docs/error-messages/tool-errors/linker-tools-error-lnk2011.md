---
title: Bağlayıcı Araçları Hatası LNK2011
ms.date: 11/04/2016
f1_keywords:
- LNK2011
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
ms.openlocfilehash: e08f068099af68375523eae0f0cc4d63960f3261
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194817"
---
# <a name="linker-tools-error-lnk2011"></a>Bağlayıcı Araçları Hatası LNK2011

önceden derlenmiş nesne bağlı değil; görüntü çalışmayabilir

Önceden derlenmiş üstbilgiler kullanıyorsanız bağlantı, önceden derlenmiş üst bilgilerle oluşturulan tüm nesne dosyalarının ile bağlantılı olması gerekir. Diğer kaynak dosyalarla kullanılmak üzere önceden derlenmiş bir üst bilgi oluşturmak için kullandığınız bir kaynak dosyanız varsa, artık önceden derlenmiş üst bilgiyle birlikte oluşturulan nesne dosyasını dahil etmeniz gerekir.

Örneğin, diğer kaynak dosyalarla kullanılmak üzere önceden derlenmiş bir üst bilgi oluşturmak için STUB. cpp adlı bir dosya derlerseniz, saplama. obj ile bağlantı oluşturmalısınız veya bu hatayı alırsınız. Aşağıdaki komut satırlarında, tek satır, iki ve üç satırlarda PROG1. cpp ve PROG2. cpp ile kullanılan ortak. pch üst bilgisini oluşturmak için kullanılır. SAPLAMA. cpp dosyası yalnızca `#include` satırları içerir (PROG1. cpp ve PROG2. cpp ile aynı `#include` satırları) ve yalnızca önceden derlenmiş üstbilgiler oluşturmak için kullanılır. Son satırda, LNK2011 kaçınmak için STUB. obj öğesine bağlanmalıdır.

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```
