---
title: Derleyici Uyarısı (düzey 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: cd161a37683703fd67b4c682558a51121c130816
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175720"
---
# <a name="compiler-warning-level-1-c4291"></a>Derleyici Uyarısı (düzey 1) C4291

' declaration ': eşleşen bir işleç silme bulunamadı; başlatma bir özel durum oluşturursa bellek boşaltılmaz

Yerleştirme [silme](../../cpp/delete-operator-cpp.md)işlemi olmayan [Yeni](../../cpp/new-operator-cpp.md) bir yerleştirme kullanılır.

**Yeni**işleçle bir nesne için bellek ayrıldığında, nesnenin Oluşturucusu çağırılır. Oluşturucu bir özel durum oluşturursa, nesne için ayrılan tüm bellek serbest bırakılmalıdır. **Yeni**işleçle eşleşen bir işleç **silme** işlevi yoksa, bu işlem gerçekleşmiyor.

Özel durum işlemeyi etkinleştirmek için herhangi bir ek bağımsız değişken olmadan **Yeni** işleç kullanırsanız ve [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHS](../../build/reference/eh-exception-handling-model.md)veya/EHa seçenekleriyle derleme yaparsanız, Oluşturucu bir özel durum oluşturursa, derleyici işleç **silme** çağrısı yapmak için kod üretir.

**Yeni** işlecin yerleştirme formunu (ayırmanın boyutuna ek olarak bağımsız değişkenlerle birlikte) kullanıyorsanız ve nesnenin Oluşturucusu bir özel durum oluşturursa, derleyici işleç **silme**çağrısı için kod oluşturur; Ancak, yalnızca bir delete işleci varsa, belleği ayrılan **Yeni** işlecin yerleştirme formuyla eşleşen bir işleç **silme** Örneğin:

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

Yukarıdaki örnek, **New**işlecinin yerleştirme formuyla eşleşen bir **Delete** işleci tanımlanmamış olduğundan, uyarı C4291 oluşturur. Sorunu çözmek için, **Main**'in üzerine aşağıdaki kodu ekleyin. Tüm aşırı yüklenmiş işleç **silme** işlevi parametrelerinin, ilk parametre hariç, **Yeni**aşırı yüklenmiş işleçle eşleştiğinden emin olun.

```
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
