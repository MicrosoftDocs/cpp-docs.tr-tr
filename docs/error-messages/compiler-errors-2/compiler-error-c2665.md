---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2665'
title: Derleyici hatası C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 784fe5ef0f24cd9e5fba99465d46f378b2b517fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210809"
---
# <a name="compiler-error-c2665"></a>Derleyici hatası C2665

' function ': Sayı1 aşırı yüklemelerinin hiçbiri parametre sayı2 'yi ' Type ' türünden dönüştüremiyor

Aşırı yüklenmiş işlevin parametresi gereken türe dönüştürülemiyor.  Olası çözümler:

- Bir dönüştürme işleci sağlayın.

- Açık dönüştürme kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2665 oluşturur.

```cpp
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```
