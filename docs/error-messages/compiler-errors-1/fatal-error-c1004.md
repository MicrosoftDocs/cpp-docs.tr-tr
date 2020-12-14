---
description: 'Daha fazla bilgi edinin: önemli hata C1004'
title: Önemli hata C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: f21978f5ff314a8273dde60428dc89ca0c5767b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262691"
---
# <a name="fatal-error-c1004"></a>Önemli hata C1004

beklenmeyen dosya sonu bulundu

Derleyici bir yapı çözümlemeden kaynak dosyanın sonuna ulaştı. Kod, aşağıdaki öğelerden biri eksik olabilir:

- Bir kapanış ayracı

- Bir kapanış ayracı

- Bir kapanış açıklama işaretçisi (*/)

- Noktalı virgül

Bu hatayı çözmek için aşağıdakileri kontrol edin:

- Varsayılan disk sürücüsünde geçici dosyalar için yeterli alan yok. Bu, kaynak dosyayla iki kat daha fazla alan gerektirir.

- `#if`False olarak değerlendirilen bir yönerge bir kapanış yönergesi içermez `#endif` .

- Kaynak dosya bir satır başı ve satır besleme ile bitmiyor.

Aşağıdaki örnek C1004 oluşturur:

```cpp
// C1004.cpp
#if TEST
int main() {}
// C1004
```

Olası çözüm:

```cpp
// C1004b.cpp
#if TEST
#endif

int main() {}
```
