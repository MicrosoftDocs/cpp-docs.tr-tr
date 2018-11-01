---
title: auto_handle::release
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::auto_handle::release
- auto_handle.release
- msclr.auto_handle.release
- auto_handle::release
helpviewer_keywords:
- auto_handle::release
ms.assetid: d4848150-859e-4c61-a946-09d24d3d6577
ms.openlocfilehash: d5ace35f75ebaa6007ddf9486eee8c45d75fa77f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591934"
---
# <a name="autohandlerelease"></a>auto_handle::release

Nesneden serbest `auto_handle` yönetimi.

## <a name="syntax"></a>Sözdizimi

```
_element_type ^ release();
```

## <a name="return-value"></a>Dönüş Değeri

Yayımlanan nesne.

## <a name="example"></a>Örnek

```
// msl_auto_handle_release.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

ref class ClassA {
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {
      Console::WriteLine( "ClassA constructor: " + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "ClassA destructor: " + m_s );
   }

   void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

int main()
{
   ClassA^ a;

   // create a new scope:
   {
      auto_handle<ClassA> agc1 = gcnew ClassA( "first" );
      auto_handle<ClassA> agc2 = gcnew ClassA( "second" );
      a = agc1.release();
   }
   // agc1 and agc2 go out of scope here

   a->PrintHello();

   Console::WriteLine( "done" );
}
```

```Output
ClassA constructor: first
ClassA constructor: second
ClassA destructor: second
Hello from first A!
done
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\auto_handle.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[auto_handle Members](../dotnet/auto-handle-members.md)<br/>
[auto_handle::~auto_handle](../dotnet/auto-handle-tilde-auto-handle.md)<br/>
[auto_handle::reset](../dotnet/auto-handle-reset.md)