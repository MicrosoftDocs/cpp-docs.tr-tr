---
title: lock::operator==
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
helpviewer_keywords:
- lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
ms.openlocfilehash: 2e7e78f5d03074058dadd969f150855f305cf85e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647872"
---
# <a name="lockoperator"></a>lock::operator==

Eşitlik işleci.

## <a name="syntax"></a>Sözdizimi

```
template<class T> bool operator==(
   T t
);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Eşitlik için karşılaştırma yapılacak nesne.

## <a name="return-value"></a>Dönüş Değeri

Döndürür **true** varsa `t` kilit ait nesne aynı **false** Aksi takdirde.

## <a name="example"></a>Örnek

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[lock Üyeleri](../dotnet/lock-members.md)<br/>
[lock::operator!=](../dotnet/lock-operator-inequality.md)