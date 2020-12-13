---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4714'
title: Derleyici Uyarısı (düzey 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: aca186ba6d81c0d769837e26023538e7e980fbc6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330572"
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
