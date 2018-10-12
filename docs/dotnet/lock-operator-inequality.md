---
title: Lock::operator! = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
dev_langs:
- C++
helpviewer_keywords:
- lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6ea18e7881b3569a3f4f9da237dc8a2b31a2ef29
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163510"
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