---
title: "Nasıl yapılır: String'deki karakterlere erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2cc927d2e06def1eba726f3123e9968003e62d1b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Nasıl yapılır: Bir System::String'deki Karakterlere Erişme
Karakter erişmek için bir <xref:System.String> nesne yüksek performanslı çağrılar için yönetilmeyen işlevlere `wchar_t*` dizeleri. İlk karakteri iç işaretçi yöntemi verir <xref:System.String> nesnesi. Bu işaretçinin kullanılabilir doğrudan değiştirilebilir veya sabitlenmiş ve sıradan bekleyen bir işleve geçirilen `wchar_t` dize.  
  
## <a name="example"></a>Örnek  
 `PtrToStringChars`döndüren bir <xref:System.Char>, bir iç işaretçi olan (olarak da bilinen bir `byref`). Bu nedenle, atık toplama tabi değil. Yerel bir işleve aktardığınızda oluşturacağız sürece bu işaretçinin PIN gerekmez.  
  
 Aşağıdaki kod göz önünde bulundurun.  Sabitleme gerekli değildir çünkü `ppchar` iç işaretçidir ve atık toplayıcı onun işaret dize geçerse, aynı zamanda güncelleştirecektir `ppchar`. Olmadan bir [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md), kod çalışır ve değil olası performans isabet olmuş sabitlemenin.  
  
 Geçirirseniz `ppchar` yerel bir işleve sonra onu sabitleme işaretçisi olmalıdır; atık toplayıcı yönetilmeyen yığın çerçevesinde herhangi işaretçileri güncelleştirmek mümkün olmaz.  
  
```  
// PtrToStringChars.cpp  
// compile with: /clr  
#include<vcclr.h>  
using namespace System;  
  
int main() {  
   String ^ mystring = "abcdefg";  
  
   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );  
  
   for ( ; *ppchar != L'\0'; ++ppchar )  
      Console::Write(*ppchar);  
}  
```  
  
```Output  
abcdefg  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek sabitlemenin nerede gösterir.  
  
```  
// PtrToStringChars_2.cpp  
// compile with: /clr  
#include <string.h>  
#include <vcclr.h>  
// using namespace System;  
  
size_t getlen(System::String ^ s) {  
   // Since this is an outside string, we want to be secure.  
   // To be secure, we need a maximum size.  
   size_t maxsize = 256;  
   // make sure it doesn't move during the unmanaged call  
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);  
   return wcsnlen(pinchars, maxsize);  
};  
  
int main() {  
   System::Console::WriteLine(getlen("testing"));  
}  
```  
  
```Output  
7  
```  
  
## <a name="example"></a>Örnek  
 İç işaretçi yerel C++ işaretçisinin tüm özelliklerine sahiptir. Örneğin, bağlı veri yapısı izlemek ve eklemeler ve yalnızca bir işaretçi kullanarak silme işlemleri yapmak için kullanabilirsiniz:  
  
```  
// PtrToStringChars_3.cpp  
// compile with: /clr /LD  
using namespace System;  
ref struct ListNode {  
   Int32 elem;   
   ListNode ^ Next;  
};  
  
void deleteNode( ListNode ^ list, Int32 e ) {   
   interior_ptr<ListNode ^> ptrToNext = &list;  
   while (*ptrToNext != nullptr) {  
      if ( (*ptrToNext) -> elem == e )  
         *ptrToNext = (*ptrToNext) -> Next;   // delete node  
      else  
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node  
   }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ birlikte çalışması (örtük PInvoke) kullanarak](../dotnet/using-cpp-interop-implicit-pinvoke.md)