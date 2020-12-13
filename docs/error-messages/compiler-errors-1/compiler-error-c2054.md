---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2054'
title: Derleyici hatası C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: b86c805a5687679cfa4bb5ed667c3bcf3adbad94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341366"
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
