---
title: Derleyici hatası C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: e7d90d684c1d95f540f6357bf61ee7c6f889ad3f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302061"
---
# <a name="compiler-error-c2054"></a>Derleyici hatası C2054

' (', ' identifier ' izlemesi için bekleniyor

İşlev tanımlayıcısı, sonunda parantez gerektiren bir bağlamda kullanılır.

Bu hata, karmaşık bir başlatmada eşittir işareti (=) dışarıda bırakarak oluşabilir.

Aşağıdaki örnek C2054 oluşturur:

```c
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

Olası çözüm:

```c
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```
