---
title: Derleyici Hatası C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: 7366995f8930b4733ccff73aef38ebcf65a0c120
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408777"
---
# <a name="compiler-error-c2054"></a>Derleyici Hatası C2054

Beklenen ' (' 'identifier' izlemek için

İşlev tanımlayıcısının sonunda gerektiren bir bağlamda kullanılır.

Bu hata, bir eşittir işareti (=) üzerinde karmaşık başlatma gt;(yok) kaynaklanabilir.

Aşağıdaki örnek, C2054 oluşturur:

```
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

Olası çözüm:

```
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```