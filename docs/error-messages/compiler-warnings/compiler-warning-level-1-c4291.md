---
title: Derleyici Uyarısı (düzey 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: e45856702eef7f24595d10b81f39047d8f9a08b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221009"
---
# <a name="compiler-warning-level-1-c4291"></a>Derleyici Uyarısı (düzey 1) C4291

' declaration ': eşleşen bir işleç silme bulunamadı; başlatma bir özel durum oluşturursa bellek boşaltılmaz

Yerleştirme [silme](../../cpp/delete-operator-cpp.md)işlemi olmayan [Yeni](../../cpp/new-operator-cpp.md) bir yerleştirme kullanılır.

İşleci olan bir nesne için bellek ayrıldığında **`new`** , nesnenin Oluşturucusu çağırılır. Oluşturucu bir özel durum oluşturursa, nesne için ayrılan tüm bellek serbest bırakılmalıdır. Bu işleç ile eşleşen bir operatör işlevi yoksa, bu işlem gerçekleştirilemez **`delete`** **`new`** .

İşlecini **`new`** özel bir bağımsız değişken olmadan kullanırsanız ve [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHS](../../build/reference/eh-exception-handling-model.md)veya/EHa seçenekleriyle derlerseniz, **`delete`** Oluşturucu bir özel durum oluşturursa, derleyici işleci çağırmak için kod üretir.

İşlecin yerleştirme formunu **`new`** (ayırmanın boyutuna ek olarak bağımsız değişkenlerle birlikte) kullanıyorsanız ve nesnenin Oluşturucusu bir özel durum oluşturursa, derleyici işleci çağırmak için kod oluşturur **`delete`** ; ancak yalnızca **`delete`** , belleği ayrılan işlecin yerleştirme formuyla eşleşen bir operatör yerleştirme formu varsa bunu olur **`new`** . Örnek:

```cpp
// C4291.cpp
// compile with: /EHsc /W1
#include <malloc.h>

class CList
{
public:
   CList(int)
   {
      throw "Fail!";
   }
};

void* operator new(size_t size, char* pszFilename, int nLine)
{
   return malloc(size);
}

int main(void)
{
   try
   {
      // This will call ::operator new(unsigned int) to allocate heap
      // memory. Heap memory pointed to by pList1 will automatically be
      // deallocated by a call to ::operator delete(void*) when
      // CList::CList(int) throws an exception.
      CList* pList1 = new CList(10);
   }
   catch (...)
   {
   }

   try
   {
      // This will call the overloaded ::operator new(size_t, char*, int)
      // to allocate heap memory. When CList::CList(int) throws an
      // exception, ::operator delete(void*, char*, int) should be called
      // to deallocate the memory pointed to by pList2. Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291
   }
   catch (...)
   {
   }
}
```

Yukarıdaki örnek, **`delete`** işleç yerleştirme formu ile eşleşen hiçbir yerleştirme biçimi tanımlanmadığı için uyarı C4291 oluşturur **`new`** . Sorunu çözmek için, **Main**'in üzerine aşağıdaki kodu ekleyin. Tüm aşırı yüklenmiş işleç **`delete`** işlevi parametrelerinin **`new`** , ilk parametre hariç, aşırı yüklenmiş işleçle eşleştiğinden emin olun.

```cpp
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
