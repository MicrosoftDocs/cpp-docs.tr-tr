---
title: Önemli hata C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: 13fb8963b33569facf62ccedfe9ce8b7bbbbfdc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383212"
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