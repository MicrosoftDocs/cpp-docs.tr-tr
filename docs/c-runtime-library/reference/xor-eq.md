---
title: xor_eq
ms.date: 11/04/2016
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- std.xor_eq
- xor_eq
- std::xor_eq
helpviewer_keywords:
- xor_eq function
ms.assetid: eca4b6b4-b77a-4d44-a09a-5a7e69fdb56c
ms.openlocfilehash: 2d1a8e62cad38ad8013d37e52768aa20e8eb50d4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957780"
---
# <a name="xor_eq"></a>xor_eq

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

**Üst bilgi:** \<iso646. h >