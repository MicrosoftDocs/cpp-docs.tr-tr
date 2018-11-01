---
title: Derleyici Hatası C2109
ms.date: 11/04/2016
f1_keywords:
- C2109
helpviewer_keywords:
- C2109
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
ms.openlocfilehash: 6592f36b29fe643e088669089b1af1b69b7b2125
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452058"
---
# <a name="compiler-error-c2109"></a>Derleyici Hatası C2109

alt simge dizi veya işaretçi türü gereklidir

Alt simge dizisi değil bir değişken üzerinde kullanıldı.

Aşağıdaki örnek, C2109 oluşturur:

```
// C2109.cpp
int main() {
   int a, b[10] = {0};
   a[0] = 1;   // C2109
   b[0] = 1;   // OK
}
```