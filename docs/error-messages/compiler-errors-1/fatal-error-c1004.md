---
title: Önemli hata C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: 82a1a3e410505be53d4356e46d5521aebb72763c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756974"
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

- False olarak değerlendirilen bir `#if` yönergesinin kapanış `#endif` yönergesi yok.

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
