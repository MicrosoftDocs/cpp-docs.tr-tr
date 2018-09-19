---
title: Önemli hata C1004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a284de510fde49602a06fb9282c0ddd59eeb0ac1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020296"
---
# <a name="fatal-error-c1004"></a>Önemli hata C1004

beklenmeyen dosya sonu bulundu

Derleyici, bir yapı çözmeden bir kaynak dosya sonuna ulaşıldı. Kod aşağıdaki öğelerden biri eksik olabilir:

- Bir kapanış ayracı

- Bir kapatma ayracı

- Kapanış açıklama işareti (* /)

- Noktalı virgül

Bu hatayı gidermek için aşağıdakileri denetleyin:

- Varsayılan disk sürücüsü, kaynak dosyası olarak iki katı kadar alan hakkında gerektiren geçici dosyalar için yeterli alan yok.

- Bir `#if` kapatma için false oturumda değerlendiren yönergesi `#endif` yönergesi.

- Bir kaynak dosyası, bir satır başı ve satır besleme ile sonlanmıyor.

Aşağıdaki örnek, C1004 oluşturur:

```
// C1004.cpp
#if TEST
int main() {}
// C1004
```

Olası çözüm:

```
// C1004b.cpp
#if TEST
#endif

int main() {}
```