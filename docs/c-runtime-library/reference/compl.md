---
title: compl
ms.date: 11/04/2016
api_name:
- compl
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
- std::compl
- std.compl
- compl
helpviewer_keywords:
- compl function
ms.assetid: e03f6fb5-cb8b-4afa-99c0-905f4105fb34
ms.openlocfilehash: b44290df1a0127ac56bb6fb09e211230a63d0846
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939058"
---
# <a name="compl"></a>compl

~ işleci alternatifi.

## <a name="syntax"></a>Sözdizimi

```C
#define compl ~
```

## <a name="remarks"></a>Açıklamalar

Makro, ~ işlecini verir.

## <a name="example"></a>Örnek

```cpp
// iso646_compl.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 1, result;

   result = ~a;
   cout << result << endl;

   result= compl(a);
   cout << result << endl;
}
```

```Output
-2
-2
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iso646. h >