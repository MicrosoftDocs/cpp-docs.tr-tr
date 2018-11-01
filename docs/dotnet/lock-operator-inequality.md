---
title: lock::operator!=
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
helpviewer_keywords:
- lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
ms.openlocfilehash: 5f202d6e7cc4c023b366f370ec2c419336822964
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558450"
---
# <a name="lockoperator"></a>lock::operator!=

Eşitsizlik işleci.

## <a name="syntax"></a>Sözdizimi

```
template<class T> bool operator!=(
   T t
);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Eşitsizlik için karşılaştırılacak nesne.

## <a name="return-value"></a>Dönüş Değeri

Döndürür **true** varsa `t` farklı kilit 's nesneden **false** Aksi takdirde.

## <a name="example"></a>Örnek

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[lock Üyeleri](../dotnet/lock-members.md)<br/>
[lock::operator==](../dotnet/lock-operator-equality.md)