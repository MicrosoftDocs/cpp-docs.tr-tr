---
title: "Nasıl yapılır: bir System:: String'deki karakterlere erişme | Microsoft Docs"
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
ms.openlocfilehash: 6c5c4c6032330a58a6f1ea9fb85d3da57c28a177
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416194"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Nasıl yapılır: Bir System::String'deki Karakterlere Erişme

Karakter erişebileceğiniz bir <xref:System.String> yönetilmeyen yüksek performanslı çağrıları için nesne işlevlere `wchar_t*` dizeleri. Yöntemin ilk karakteri iç işaretçiye verir <xref:System.String> nesne. This işaretçisi kullanılabilir doğrudan değiştirilebilir veya sabitlenmiş ve sıradan bekleyen bir işleve geçirilen `wchar_t` dize.

## <a name="example"></a>Örnek

`PtrToStringChars` döndürür bir <xref:System.Char>, iç işaretçiye olduğu (olarak da bilinen bir `byref`). Bu nedenle, çöp toplama tabi olduğu. Yerel bir işleve geçirilecek gideceğinizi sürece bu işaretçiyi sabitleme gerekmez.

Aşağıdaki kodu düşünün.  Sabitleme gerekli değildir çünkü `ppchar` iç işaretçidir ve atık toplayıcı işaret için dize geçerse de güncelleştirir `ppchar`. Olmadan bir [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md), kod ve değil olası performans düşüşüne neden olmuş sabitleyerek.

Geçirirseniz `ppchar` yerel bir işleve ardından, bir sabitleme işaretçisi olması gerekir; çöp toplayıcı yönetilmeyen yığın çerçevesinde herhangi bir işaretçinin güncelleştirmeniz mümkün olmayacaktır.

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

Bu örnek, sabitleme gerekmesi halinde gösterir.

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

İç işaretçi yerel C++ işaretçisinin tüm özelliklerine sahiptir. Örneğin, bağlı veri yapısı izlemek ve eklemeler ve silmeler yalnızca bir işaretçi kullanarak yapmak için kullanabilirsiniz:

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