---
title: veya
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
- std::or
- std.or
- Or
helpviewer_keywords:
- or function
ms.assetid: 6523b3ac-0a18-44ec-9e9a-b9bab8525ead
ms.openlocfilehash: 0a3a6800fba71a6b6edc77cca91ec40fe5476509
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170156"
---
# <a name="or"></a>veya

İşlecin alternatifi &#124; &#124;

## <a name="syntax"></a>Sözdizimi

```C

#define or ||
```

## <a name="remarks"></a>Açıklamalar

Makro işleci &#124; &#124;verir.

## <a name="example"></a>Örnek

```cpp
// iso646_or.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   bool a = true, b = false, result;

   boolalpha(cout);

   result= a || b;
   cout << result << endl;

   result= a or b;
   cout << result << endl;
}
```

```Output
true
true
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<iso646. h >
