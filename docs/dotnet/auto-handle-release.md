---
title: auto_handle::Release | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_handle::release
- auto_handle.release
- msclr.auto_handle.release
- auto_handle::release
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::release
ms.assetid: d4848150-859e-4c61-a946-09d24d3d6577
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5237ec59d8e90a793d6df83d6dbc2c0ff1ec1cb0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391754"
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