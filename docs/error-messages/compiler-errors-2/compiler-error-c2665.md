---
title: Derleyici Hatası C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 63817c4181edb942f43f41c24fb10278d14f397e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474744"
---
# <a name="compiler-error-c2665"></a>Derleyici Hatası C2665

'function': 'type' türünden Sayı1 aşırı hiçbiri parametresi sayı2 dönüştürebilir

Aşırı yüklenen işlevin parametre gerekli türüne dönüştürülemiyor.  Olası çözümler:

- Bir dönüştürme operatörünün sağlayın.

- Açık dönüştürme kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2665 oluşturur.

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```