---
title: not
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
- std::not
- std.not
- Not
helpviewer_keywords:
- not function
ms.assetid: d2ddbd5c-33c0-4aff-8961-feac155b4ba1
ms.openlocfilehash: 01247a12484e49087d45e7d1417656a5c1782c8b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951271"
---
# <a name="not"></a>not

İçin bir alternatif! işlecinde.

## <a name="syntax"></a>Sözdizimi

```C

#define not !
```

## <a name="remarks"></a>Açıklamalar

Makro, ! işlecini verir.

## <a name="example"></a>Örnek

```cpp
// iso646_not.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 0;

   if (!a)
      cout << "a is zero" << endl;

   if (not(a))
      cout << "a is zero" << endl;
}
```

```Output
a is zero
a is zero
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iso646. h >