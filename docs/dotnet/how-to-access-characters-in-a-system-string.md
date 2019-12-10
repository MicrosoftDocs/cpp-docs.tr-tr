---
title: "Nasıl yapılır: Bir System::String'deki Karakterlere Erişme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: 3c44c5e7651bb1c5b4c28654b896cbe64bd5bec7
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988646"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Nasıl yapılır: Bir System::String'deki Karakterlere Erişme

Bir <xref:System.String> nesnenin karakterlerine, `wchar_t*` dizeleri alan yönetilmeyen işlevlere yönelik yüksek performanslı çağrılar için erişebilirsiniz. Yöntemi, <xref:System.String> nesnesinin ilk karakterine iç işaretçi verir. Bu işaretçi doğrudan veya sabitlenebilir ve sıradan bir `wchar_t` dizesi bekleyen bir işleve geçirilebilir.

## <a name="example"></a>Örnek

`PtrToStringChars`, iç işaretçi olan (`byref`olarak da bilinir) bir <xref:System.Char>döndürür. Bu nedenle, atık toplamaya tabidir. Yerel bir işleve geçemediğiniz takdirde bu işaretçiyi sabitlemek zorunda kalmazsınız.

Aşağıdaki kodu göz önünde bulundurun.  `ppchar` iç işaretçi olduğundan ve çöp toplayıcı işaret ettiği dizeyi gösteriyorsa, `ppchar`da güncelleştirir. [Pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md)olmadan, kod çalışır ve sabitleme nedeniyle olası performans okuması yoktur.

`ppchar` yerel bir işleve geçirirseniz, bir sabitleme işaretçisi olmalıdır; Çöp toplayıcı, yönetilmeyen yığın çerçevesindeki işaretçileri güncelleştiremeyecektir.

```cpp
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

Bu örnek, sabitlemenin nerede gerekli olduğunu gösterir.

```cpp
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

İç işaretçinin bir yerel C++ işaretçinin tüm özellikleri vardır. Örneğin, bir bağlı veri yapısına yol göstermek ve yalnızca bir işaretçiyi kullanarak eklemeler ve silmeler yapmak için kullanabilirsiniz:

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
