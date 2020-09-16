---
title: "Nasıl yapılır: Bir System::String'deki Karakterlere Erişme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: cb62eb0fecbee202e4d01635a60da565241822ee
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686801"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Nasıl yapılır: Bir System::String'deki Karakterlere Erişme

<xref:System.String>Dizelerin bulunduğu yönetilmeyen işlevlere yönelik yüksek performanslı çağrılar için bir nesnenin karakterlerine erişebilirsiniz `wchar_t*` . Yöntemi, nesnenin ilk karakterine iç işaretçi verir <xref:System.String> . Bu işaretçi doğrudan veya sabitlenebilir ve normal bir dize bekleyen bir işleve geçirilebilir **`wchar_t`** .

## <a name="examples"></a>Örnekler

`PtrToStringChars`<xref:System.Char>iç işaretçi (de olarak da bilinir) olan bir döndürür `byref` . Bu nedenle, atık toplamaya tabidir. Yerel bir işleve geçemediğiniz takdirde bu işaretçiyi sabitlemek zorunda kalmazsınız.

Aşağıdaki kodu göz önünde bulundurun.  `ppchar`İç işaretçi olduğundan ve çöp toplayıcı işaret ettiği dizeyi işaret ediyorsa, bu işlem de güncelleştirilecek `ppchar` . [Pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md)olmadan, kod çalışır ve sabitleme nedeniyle olası performans okuması yoktur.

`ppchar`Yerel bir işleve geçirirseniz, bunun sabitleme işaretçisi olması gerekir; çöp toplayıcı yönetilmeyen yığın çerçevesindeki işaretçileri güncelleştiremeyecektir.

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

İç işaretçinin tüm özelliklerine sahip bir yerel C++ işaretçisi vardır. Örneğin, bir bağlı veri yapısına yol göstermek ve yalnızca bir işaretçiyi kullanarak eklemeler ve silmeler yapmak için kullanabilirsiniz:

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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
