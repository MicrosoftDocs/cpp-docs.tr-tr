---
title: 'Nasıl yapılır: Yönetilmeyen Kaynakları Bayt Dizisine Yükleme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- native resources, loading into Byte array
- unmanaged resources, loading into Byte array
- native resources
ms.assetid: cdada6cd-6d42-437a-a90f-44a0b18d6a93
ms.openlocfilehash: d7d35af462a2d598995f222221a4023d09c73ff3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579893"
---
# <a name="how-to-load-unmanaged-resources-into-a-byte-array"></a>Nasıl yapılır: Yönetilmeyen Kaynakları Bayt Dizisine Yükleme

Yönetilmeyen kaynakları yüklemek için birkaç yol Bu konu açıklar bir <xref:System.Byte> dizi.

## <a name="example"></a>Örnek

Yönetilmeyen kaynaklarınızı saran boyutunu biliyorsanız, CLR dizisi erişinceye ve CLR dizisi dizi bloğu için bir işaretçi kullanarak diziye kaynağı'i yükleyin.

```
// load_unmanaged_resources_into_Byte_array.cpp
// compile with: /clr
using namespace System;
void unmanaged_func( unsigned char * p ) {
   for ( int i = 0; i < 10; i++ )
      p[ i ] = i;
}

public ref class A {
public:
   void func() {
      array<Byte> ^b = gcnew array<Byte>(10);
      pin_ptr<Byte> p =  &b[ 0 ];
      Byte * np = p;
      unmanaged_func( np );   // pass pointer to the block of CLR array.
      for ( int i = 0; i < 10; i++ )
         Console::Write( b[ i ] );
      Console::WriteLine();
   }
};

int main() {
   A^ g = gcnew A;
   g->func();
}
```

```Output
0123456789
```

## <a name="example"></a>Örnek

Bu örnek, verilerin bir yönetilmeyen bellek bloğundan yönetilen bir diziye nasıl kopyalanacağını gösterir.

```
// load_unmanaged_resources_into_Byte_array_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#include <string.h>
int main() {
   char buf[] = "Native String";
   int len = strlen(buf);
   array<Byte> ^byteArray = gcnew array<Byte>(len + 2);

   // convert any native pointer to IntPtr by doing C-Style cast
   Marshal::Copy( (IntPtr)buf, byteArray, 0, len );
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)