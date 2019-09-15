---
title: bitor
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
- bitor
- std.bitor
- std::bitor
helpviewer_keywords:
- bitor function
ms.assetid: 3c0a3711-9c74-41f2-b400-2f7797da30d1
ms.openlocfilehash: bda47a4590095ecf089efa23b983622e2fbd1a59
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939454"
---
# <a name="bitor"></a>bitor

&#124; İşlecin alternatifi.

## <a name="syntax"></a>Sözdizimi

```C

#define bitor |
```

## <a name="remarks"></a>Açıklamalar

Makro işleci &#124;verir.

## <a name="example"></a>Örnek

```cpp
// iso646_bitor.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 1, b = 2, result;

   result = a | b;
   cout << result << endl;

   result= a bitor b;
   cout << result << endl;
}
```

```Output
3
3
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iso646. h >