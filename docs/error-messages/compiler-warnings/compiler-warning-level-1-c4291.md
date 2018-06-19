---
title: Derleyici Uyarısı (düzey 1) C4291 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4291
dev_langs:
- C++
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c10351be640dc142f224cb5583a980e396f086cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282385"
---
# <a name="compiler-warning-level-1-c4291"></a>Derleyici Uyarısı (düzey 1) C4291
'bildirimi': bulundu; hiçbir eşleşen delete işleci başlatma bir özel durum oluşturursa bellek serbest bırakılmaz  
  
 Bir yerleştirme [yeni](../../cpp/new-operator-cpp.md) kullanılan olduğu hiçbir yerleştirme [silmek](../../cpp/delete-operator-cpp.md).  
  
 Ne zaman bellek ayrılır işlece sahip bir nesne için **yeni**, nesnenin oluşturucusu olarak adlandırılır. Oluşturucusu bir özel durum oluşturursa, nesne için ayrılmış bellek ayırması. Sürece bu yer alamaz bir işleç **silmek** işleci eşleşen exists işlevi **yeni**.  
  
 İşleç kullanırsanız **yeni** herhangi bir ek bağımsız değişkenler ve derleme ile olmadan [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), ya da özel durum işleme, derleyici etkinleştirmek için /EHa seçeneklerini kodu üretir Operatör çağrısı **silmek** Oluşturucusu bir özel durum oluşturursa.  
  
 Yerleştirme biçiminde kullanırsanız **yeni** işleci (ayırma boyutu yanı sıra bağımsız değişkenlerle form) ve nesnenin oluşturucusu bir özel durum oluşturur, derleyici hala işleci çağırmakiçinkodoluşturur**Sil**; ancak bunu yalnızca bunu işlecinin yerleştirme form varsa ne yapacağını **silmek** yerleştirme formun işlecinin eşleşen var. **yeni** bellek tahsis. Örneğin:  
  
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
  
 Yukarıdaki örnekte uyarı C4291 oluşturur çünkü işlecinin yerleştirme form **silmek** tanımlanmış işlecinin yerleştirme form ile eşleşen **yeni**. Sorunu çözmek için yukarıdaki aşağıdaki kodu ekleyin **ana**. Dikkat tüm aşırı yüklenmiş işlecinin **silmek** işlev parametreleri aşırı yüklenmiş işlecinin eşleştiğinden **yeni**, ilk parametre dışında.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```