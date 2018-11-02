---
title: Derleyici Hatası C2088
ms.date: 11/04/2016
f1_keywords:
- C2088
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
ms.openlocfilehash: 6d53f2896fc3b964a4d2652b3bfd0dcebb4a7226
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550788"
---
# <a name="compiler-error-c2088"></a>Derleyici Hatası C2088

'operator': 'sınıf anahtarı' için geçersiz

İşleci, yapı veya birleşim için tanımlanmadı. Bu hata, yalnızca C kodu için geçerlidir.

Aşağıdaki örnek, üç kez C2088 oluşturur:

```
// C2088.c
struct S {
   int m_i;
} s;

int main() {
   int i = s * 1;   // C2088
   struct S s2 = +s;   // C2088
   s++;   // C2088
}
```