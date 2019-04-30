---
title: Derleyici Uyarısı (düzey 4) C4714
ms.date: 11/04/2016
f1_keywords:
- C4714
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
ms.openlocfilehash: ed94e5b716a697ec96d7fecac75433823c9a67e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395189"
---
# <a name="compiler-warning-level-4-c4714"></a>Derleyici Uyarısı (düzey 4) C4714

'function' __forceinline olarak satır içine alınmış işaretlenen işlevi

Verilen işlevin satır içi genişletme için seçildi, ancak derleyicinin kullanılmayacak satır içi kullanım.

Ancak `__forceinline` derleyici daha güçlü bir göstergesidir `__inline`, satır içi kullanım derleyicinin kararımıza hala gerçekleştirilir ancak hiçbir buluşsal yöntemler avantajlarından belirlemek için kullanılan inlining'i bu işlev.

Bazı durumlarda, derleyicinin olur satır belirli bir işlev mekanik nedenleri. Örneğin, derleyici, satır olur:

- SEH hem de C++ EH karıştırma neden olacaksa bir işlev.

- -GX/EHs/EHa açık olduğunda, değer olarak geçilemez nesneleri bazı işlevler kopyalama ile oluşturulmuş.

- -GX/EHs/EHa açık olduğunda izlenemeyen bir nesneyi değere göre döndürmenin işlevleri.

- Og/Ox/O1/O2 - olmadan derleme yaparken, satır içi derlemeyle işlevler.

- Bir bağımsız değişken listesi ile işlevler.

- Bir işlev ile bir **deneyin** deyimi (C++ özel durum işleme).

Aşağıdaki örnek, C4714 oluşturur:

```
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