---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4208'
title: Derleyici Uyarısı (düzey 4) C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: a99e9435fcdbfb65248fb38883a8f3395ef4db14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314782"
---
# <a name="compiler-warning-level-4-c4208"></a>Derleyici Uyarısı (düzey 4) C4208

Standart olmayan uzantı kullanıldı: delete [exp]-exp değerlendirildi ancak yoksayıldı

Microsoft uzantıları (/Ze) ile, [delete işleci](../../cpp/delete-operator-cpp.md)ile köşeli ayraç içindeki bir değeri kullanarak bir diziyi silebilirsiniz. Değer yok sayılır.

```cpp
// C4208.cpp
// compile with: /W4
int main()
{
   int * MyArray = new int[18];
   delete [18] MyArray;      // C4208
   MyArray = new int[18];
   delete [] MyArray;        // ok
}
```

Bu değerler, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında geçersizdir.
