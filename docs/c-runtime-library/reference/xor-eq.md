---
title: xor_eq
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
- std.xor_eq
- xor_eq
- std::xor_eq
helpviewer_keywords:
- xor_eq function
ms.assetid: eca4b6b4-b77a-4d44-a09a-5a7e69fdb56c
ms.openlocfilehash: 4ba3025df471a0433d4e3c4a1a8ddb75400c9523
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521394"
---
# <a name="xoreq"></a>xor_eq

^= işleci alternatifi.

## <a name="syntax"></a>Sözdizimi

```C

#define xor_eq ^=
```

## <a name="remarks"></a>Açıklamalar

Makro, ^= işlecini verir.

## <a name="example"></a>Örnek

```cpp
// iso646_xor_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 3, b = 2, result;

   result= a ^= b;
   cout << result << endl;

   a = 3;
   b = 2;

   result= a xor_eq b;
   cout << result << endl;
}
```

```Output
1
1
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<iso646.h >