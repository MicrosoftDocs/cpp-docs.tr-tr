---
description: 'Daha fazla bilgi edinin: nasıl yapılır: yönetilmeyen kaynakları bayt dizisine yükleme'
title: 'Nasıl yapılır: Yönetilmeyen Kaynakları Bayt Dizisine Yükleme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- native resources, loading into Byte array
- unmanaged resources, loading into Byte array
- native resources
ms.assetid: cdada6cd-6d42-437a-a90f-44a0b18d6a93
ms.openlocfilehash: e5a7a88a505d3f02b8e9287d6407ddbe77b99dee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258284"
---
# <a name="how-to-load-unmanaged-resources-into-a-byte-array"></a>Nasıl yapılır: Yönetilmeyen Kaynakları Bayt Dizisine Yükleme

Bu konuda, yönetilmeyen kaynakları bir diziye yüklemek için çeşitli yollar ele alınmaktadır <xref:System.Byte> .

## <a name="examples"></a>Örnekler

Yönetilmeyen kaynağınızın boyutunu biliyorsanız, bir CLR dizisini önceden ayırabilir ve ardından CLR dizisinin dizi bloğunun bir işaretçisini kullanarak kaynağı diziye yükleyebilirsiniz.

```cpp
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

Bu örnek, yönetilmeyen bir bellek bloğundan yönetilen bir diziye verilerin nasıl kopyalanacağını gösterir.

```cpp
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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
