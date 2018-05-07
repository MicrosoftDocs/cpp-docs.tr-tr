---
title: "Nasıl yapılır: String'deki karakterlere erişme | Microsoft Docs"
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ed9682492eedc915919758d42d5594560cb4a83a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Nasıl yapılır: Bir System::String'deki Karakterlere Erişme
Karakter erişmek için bir <xref:System.String> nesne yüksek performanslı çağrılar için yönetilmeyen işlevlere `wchar_t*` dizeleri. İlk karakteri iç işaretçi yöntemi verir <xref:System.String> nesnesi. Bu işaretçinin kullanılabilir doğrudan değiştirilebilir veya sabitlenmiş ve sıradan bekleyen bir işleve geçirilen `wchar_t` dize.  
  
## <a name="example"></a>Örnek  
 `PtrToStringChars` döndüren bir <xref:System.Char>, bir iç işaretçi olan (olarak da bilinen bir `byref`). Bu nedenle, atık toplama tabi değil. Yerel bir işleve aktardığınızda oluşturacağız sürece bu işaretçinin PIN gerekmez.  
  
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
 [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)