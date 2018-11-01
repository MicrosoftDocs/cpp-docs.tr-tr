---
title: not_eq
ms.date: 11/04/2016
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- not_eq
- std::not_eq
- std.not_eq
helpviewer_keywords:
- not_eq function
ms.assetid: d87ad299-8b50-4393-a57f-06f70e1f23fb
ms.openlocfilehash: b3a6805aa58b8671cb14ecbd4b56ab34e17f58c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618744"
---
# <a name="noteq"></a>not_eq

!= işleci alternatifi.

## <a name="syntax"></a>Sözdizimi

```C

#define not_eq !=

```

## <a name="remarks"></a>Açıklamalar

Makro != işlecini verir.

## <a name="example"></a>Örnek

```cpp
// iso646_not_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 0, b = 1;

   if (a != b)
      cout << "a is not equal to b" << endl;

   if (a not_eq b)
      cout << "a is not equal to b" << endl;
}
```

```Output
a is not equal to b
a is not equal to b
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<iso646.h >