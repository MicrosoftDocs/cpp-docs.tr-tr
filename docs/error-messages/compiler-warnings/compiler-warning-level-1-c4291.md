---
title: Derleyici Uyarısı (düzey 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: e1b787e7149afe93fb50cc1e6ceaecba2e787876
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384263"
---
# <a name="compiler-warning-level-1-c4291"></a>Derleyici Uyarısı (düzey 1) C4291

'bildirim': bulunamadı; eşleşen hiçbir delete işleci başlatma bir özel durum oluşturursa bellek serbest bırakılmaz

Bir yerleştirme [yeni](../../cpp/new-operator-cpp.md) kullanılan var olan hiçbir yerleştirme [Sil](../../cpp/delete-operator-cpp.md).

Ne zaman bellek tahsis edildiği işleci olan bir nesne için **yeni**, nesnenin oluşturucusundan çağrılır. Oluşturucusu bir özel durum oluşturursa, nesne için ayrılan belleği serbest bırakılması. Bu sürece yer alamaz operatörün **Sil** işleci eşleşen exists işlevi **yeni**.

İşlecini kullanıyorsanız **yeni** herhangi bir ek bağımsız değişkenler ve derleme ile olmadan [/GX](../../build/reference/gx-enable-exception-handling.md), [EHS](../../build/reference/eh-exception-handling-model.md), ya da özel durum işleme, derleyici etkinleştirmek için/eha seçenekleri için kod üretir işlecini çağırmak **Sil** Oluşturucusu bir özel durum atar.

Yerleştirme biçimini kullanırsanız **yeni** işleci (ayırma boyutu yanı sıra bağımsız değişkenlerle formu) ve nesnenin oluşturucusu bir özel durum oluşturursa, derleyici hala işleciniçağırmakiçinkodoluşturur**Sil**; ancak bunu yalnızca bir yerleştirme form işlecinin, bunu yapar **Sil** yerleştirme formun işlecinin eşleşen mevcut **yeni** tarafından ayrılan bellek. Örneğin:

```
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

Yukarıdaki örnekte C4291 uyarıyı oluşturur çünkü işlecinin yerleştirme form **Sil** tanımlanmış yerleştirme formun işlecinin eşleşen **yeni**. Sorunu çözmek için aşağıdaki kodu yukarıdaki Ekle **ana**. Dikkat tüm aşırı yüklenmiş işleç **Sil** işlev parametrelerini aşırı yüklenmiş işlecin eşleştiğinden **yeni**, ilk parametresi dışında.

```
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```