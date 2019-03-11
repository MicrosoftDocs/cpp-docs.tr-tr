---
title: 'Nasıl yapılır: Yönetilmeyen kaynakları Bayt dizisine yükleme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- native resources, loading into Byte array
- unmanaged resources, loading into Byte array
- native resources
ms.assetid: cdada6cd-6d42-437a-a90f-44a0b18d6a93
ms.openlocfilehash: 641bdf4429bca35800e3fbbbb7622f2651bb3fee
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751576"
---
# <a name="how-to-load-unmanaged-resources-into-a-byte-array"></a>Nasıl yapılır: Yönetilmeyen kaynakları Bayt dizisine yükleme

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

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
