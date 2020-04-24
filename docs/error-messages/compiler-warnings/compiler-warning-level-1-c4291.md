---
title: Derleyici Uyarısı (düzey 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: c1972236e30be4e6ca738b606b00398f5c7860e0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754861"
---
# <a name="compiler-warning-level-1-c4291"></a>Derleyici Uyarısı (düzey 1) C4291

'declaration' : eşleşen operatör silme bulunamadı; başlatma bir özel durum atarsa bellek serbest bırakılmaz

Yerleşim [silme](../../cpp/delete-operator-cpp.md)nin olmadığı [yeni](../../cpp/new-operator-cpp.md) bir yerleşim kullanılır.

Bellek işleç **yeni**olan bir nesne için tahsis edildiğinde, nesnenin oluşturucusu çağrılır. Oluşturucu bir özel durum atarsa, nesne için ayrılan herhangi bir bellek ayrılmalıdır. İşleç **yeni** **silmek** işlevi yoksa bu gerçekleşemez.

İşleciyi herhangi bir ekstra bağımsız değişken olmadan **yeni** kullanır ve özel durum işlemeyi etkinleştirmek için [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), veya /EHa seçenekleriyle derlerseniz, derleyici, oluşturucu bir özel durum atarsa operatör **silme** çağrısı yapmak için kod oluşturur.

**Yeni** işlecinin yerleşim biçimini (ayırmanın boyutuna ek olarak bağımsız değişkenli form) kullanırsanız ve nesnenin oluşturucusu bir özel durum atarsa, derleyici yine de işleç **silme**çağrısı için kod oluşturur; ancak bunu yalnızca, belleği ayıran **yeni** işleç yenisinin yerleşim formuyla eşleşen bir işleç **silme** yerleşim formu varsa bunu yapar. Örneğin:

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

Yukarıdaki örnek, **işleç** **silme** nin yerleşim formu yeni işlecinin yerleşim formuyla eşleşen tanımlanmadığından C4291 uyarısı oluşturur. Sorunu çözmek **için, ana**kodun üzerine ekleyin. Aşırı yüklenilen işleci **silme** işlevi parametrelerinin ilk parametre hariç, aşırı yüklenen **new**işleciyeninin parametreleri ile eşleştirildiğine dikkat edin.

```cpp
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
