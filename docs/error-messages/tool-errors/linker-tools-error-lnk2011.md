---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK2011'
title: Bağlayıcı Araçları Hatası LNK2011
ms.date: 11/04/2016
f1_keywords:
- LNK2011
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
ms.openlocfilehash: f149324a61d34333e8f29f70bf5fee4cd952ba8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338470"
---
# <a name="linker-tools-error-lnk2011"></a>Bağlayıcı Araçları Hatası LNK2011

önceden derlenmiş nesne bağlı değil; görüntü çalışmayabilir

Önceden derlenmiş üstbilgiler kullanıyorsanız bağlantı, önceden derlenmiş üst bilgilerle oluşturulan tüm nesne dosyalarının ile bağlantılı olması gerekir. Diğer kaynak dosyalarla kullanılmak üzere önceden derlenmiş bir üst bilgi oluşturmak için kullandığınız bir kaynak dosyanız varsa, artık önceden derlenmiş üst bilgiyle birlikte oluşturulan nesne dosyasını dahil etmeniz gerekir.

Örneğin, diğer kaynak dosyalarla kullanılmak üzere önceden derlenmiş bir üst bilgi oluşturmak için STUB. cpp adlı bir dosya derlerseniz, saplama. obj ile bağlantı oluşturmalısınız veya bu hatayı alırsınız. Aşağıdaki komut satırlarında, tek satır, iki ve üç satırlarda PROG1. cpp ve PROG2. cpp ile kullanılan ortak. pch üst bilgisini oluşturmak için kullanılır. SAPLAMA. cpp dosyası yalnızca `#include` satırlar ( `#include` PROG1. cpp ve PROG2. cpp ile aynı satırlar) içerir ve yalnızca önceden derlenmiş üstbilgiler oluşturmak için kullanılır. Son satırda, LNK2011 kaçınmak için STUB. obj öğesine bağlanmalıdır.

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```
