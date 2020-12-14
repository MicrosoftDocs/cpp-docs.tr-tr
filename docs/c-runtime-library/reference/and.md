---
description: 'Hakkında daha fazla bilgi edinin: ve'
title: ve
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
- And
- std.and
- std::and
helpviewer_keywords:
- and macro
ms.assetid: 2644ab57-8e1b-48f0-9021-cafe3e26bdc4
ms.openlocfilehash: addc54fe49c30d7d0f3499415d687eef0112a6f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211342"
---
# <a name="and"></a>ve

 && işlecine bir alternatifi.

## <a name="syntax"></a>Syntax

```C

#define and &&
```

## <a name="remarks"></a>Açıklamalar

Makro && işlecini verir.

## <a name="example"></a>Örnek

```cpp
// iso646_and.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   bool a = true, b = false, result;

   boolalpha(cout);

   result= a && b;
   cout << result << endl;

   result= a and b;
   cout << result << endl;
}
```

```Output
false
false
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iso646.h>
