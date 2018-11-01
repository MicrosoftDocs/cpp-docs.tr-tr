---
title: auto_gcroot::operator!
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr.auto_gcroot.operator!
- auto_gcroot.operator!
- msclr::auto_gcroot::operator!
- auto_gcroot::operator!
helpviewer_keywords:
- auto_gcroot::operator!
ms.assetid: f9728be3-2e09-4c01-a594-43e0d59d40d3
ms.openlocfilehash: c925ebdfc9b1a8c8006728884849c360350b5c57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568188"
---
# <a name="autogcrootoperator"></a>auto_gcroot::operator!

Kullanarak işleci `auto_gcroot` koşullu ifadede.

## <a name="syntax"></a>Sözdizimi

```
bool operator!() const;
```

## <a name="return-value"></a>Dönüş Değeri

**doğru** Sarmalanan Nesne geçersiz; ise **false** Aksi takdirde.

## <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_operator_not.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s;
   if ( s ) Console::WriteLine( "s is valid" );
   if ( !s ) Console::WriteLine( "s is invalid" );
   s = "something";
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
   s.reset();
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
}
```

```Output
s is invalid
now s is valid
now s is invalid
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[auto_gcroot Members](../dotnet/auto-gcroot-members.md)<br/>
[auto_gcroot::operator bool](../dotnet/auto-gcroot-operator-bool.md)