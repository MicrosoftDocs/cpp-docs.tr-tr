---
title: __sptr, __uptr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __uptr_cpp
- __sptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: daa431204c66def272d07fc0b670dc279e1569ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sptr-uptr"></a>__sptr, __uptr
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Kullanım `__sptr` veya `__uptr` nasıl derleyicisi bir 64-bit işaretçi 32-bit işaretçi kodu belirtmek için bir 32 bit işaretçi bildirimi değiştiricisi. Bir 64-bit işaretçi değişkenine atanan ya da bir 64-bit platformda başvuru yapıldı 32-bit işaretçi, örneğin, dönüştürülür.  
  
 Microsoft belgelerine desteği için 64-bit platformları bazen bir 32 bit işaretçi en önemli bit için oturum bit ifade eder. Varsayılan olarak, 64-bit gösteren bir işaretçi bir 32 bit işaretçi dönüştürmek için oturum uzantısı derleyici kullanır. Diğer bir deyişle, en az önemli 32 bit 64-bit işaretçisinin 32-bit işaretçi değerine ayarlanır ve en önemli 32 bit 32-bit işaretçisinin oturum bit değerine ayarlanır. Bu dönüştürme oturum bit 0 ise, ancak oturum bit 1 değilse, doğru sonuçlar verir. Örneğin, eşdeğer 64-bit adres 0x000000007FFFFFFF 32-bit adres 0x7FFFFFFF verir, ancak 0x80000000 32-bit adres yanlış 0xFFFFFFFF80000000 için değiştirilebilir.  
  
 `__sptr`, Veya işaretçisi imzalı değiştiricisi belirten bir işaretçi dönüştürme 32-bit işaretçinin oturum bit 64-bit işaretçinin en önemli BITS ayarlayın. `__uptr`, İmzasız işaretçi değiştiricisi belirtiyor dönüştürme en önemli BITS sıfır olarak ayarlayın. Aşağıdaki bildirimler göster `__sptr` ve `__uptr` değiştiriciler, iki nitelenmemiş işaretçileri ile kullanılan iki işaretçileri tam ile [__ptr32](../cpp/ptr32-ptr64.md) türü ve bir işlev parametresi.  
  
```  
int * __sptr psp;  
int * __uptr pup;  
int * __ptr32 __sptr psp32;  
int * __ptr32 __uptr pup32;  
void MyFunction(char * __uptr __ptr32 myValue);  
```  
  
 Kullanım `__sptr` ve `__uptr` değiştiricileri işaretçi bildirimleri ile. Değiştiriciler konumu kullanmak bir [işaretçi türü niteleyici](../c-language/pointer-declarations.md), değiştirici başka bir deyişle, yıldız işareti gelmelidir. Değiştiriciler ile kullanamazsınız [üyeleri işaretçileri](../cpp/pointers-to-members.md). Değiştiriciler işaretçi olmayan bildirimleri etkilemez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kullanma 32-bit işaretçileri bildirir `__sptr` ve `__uptr` değiştiriciler, her 32-bit işaretçi bir 64-bit işaretçi değişkenine atar ve ardından her bir 64-bit işaretçiyi on altılık değeri görüntüler. Örnek ile yerel 64 bit derleyici derlenir ve 64-bit bir platform üzerinde yürütülür.  
  
```cpp  
// sptr_uptr.cpp  
// processor: x64  
#include "stdio.h"  
  
int main()  
{  
    void *        __ptr64 p64;  
    void *        __ptr32 p32d; //default signed pointer  
    void * __sptr __ptr32 p32s; //explicit signed pointer  
    void * __uptr __ptr32 p32u; //explicit unsigned pointer  
  
// Set the 32-bit pointers to a value whose sign bit is 1.  
    p32d = reinterpret_cast<void *>(0x87654321);  
    p32s = p32d;  
    p32u = p32d;  
  
// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated   
// to the __sptr and __uptr modifiers.   
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");  
    printf("p32d:       %p\n", p32d);   
    printf("p32s:       %p\n", p32s);  
    printf("p32u:       %p\n", p32u);  
  
    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");  
    p64 = p32d;   
    printf("p32d: p64 = %p\n", p64);  
    p64 = p32s;  
    printf("p32s: p64 = %p\n", p64);  
    p64 = p32u;  
    printf("p32u: p64 = %p\n", p64);  
    return 0;  
}  
```  
  
```Output  
Display each 32-bit pointer (as an unsigned 64-bit pointer):  
p32d:       0000000087654321  
p32s:       0000000087654321  
p32u:       0000000087654321  
  
Display the 64-bit pointer created from each 32-bit pointer:  
p32d: p64 = FFFFFFFF87654321  
p32s: p64 = FFFFFFFF87654321  
p32u: p64 = 0000000087654321  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft'a Özel Değiştiriciler](../cpp/microsoft-specific-modifiers.md)