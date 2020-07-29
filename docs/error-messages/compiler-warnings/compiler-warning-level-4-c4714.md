---
title: Derleyici Uyarısı (düzey 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: 286a9e6e12643d3dadd070e7c4cf4b2dd350c02c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219865"
---
# <a name="compiler-warning-level-4-c4714"></a>Derleyici Uyarısı (düzey 4) C4714

> ' function ' işlevi satır içine alınmadı __forceinline olarak işaretlendi

Verilen işlev satır içi genişletme için seçildi, ancak derleyici satır içinde gerçekleştirmedi.

, **`__forceinline`** Derleyicide daha güçlü bir işaret olmakla birlikte **`__inline`** , derleyicinin kararına göre de devam eder, ancak bu işlevden gelen avantajları belirlemede buluşsal yöntemler kullanılmaz.

Bazı durumlarda, derleyici, mekanik nedenlerle belirli bir işlevi satır içi olarak içermez. Örneğin, derleyici satır içi olmayacaktır:

- Hem SEH hem de C++ EH karıştırma ile sonuçlanacaksa bir işlev.

- -GX/EHs/EHa açık olduğunda, Copy tarafından oluşturulmuş nesneleri Kopyala ile bazı işlevler.

- -GX/EHs/EHa açık olduğunda, değere göre koşulsuz bir nesne döndüren işlevler.

- -Og/Ox/O1/O2 olmadan derlerken satır içi bütünleştirilmiş kod içeren işlevler.

- Değişken bağımsız değişken listesi olan işlevler.

- **`try`**(C++ özel durum işleme) ifadesiyle bir işlev.

Aşağıdaki örnek C4714 oluşturur:

```cpp
// C4714.cpp
// compile with: /Ob1 /GX /W4
__forceinline void func1()
{
   try
   {
   }
   catch (...)
   {
   }
}

void func2()
{
   func1();   // C4714
}

int main()
{
}
```
