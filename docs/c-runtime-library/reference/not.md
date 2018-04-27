---
title: değil | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
- std::not
- std.not
- Not
dev_langs:
- C++
helpviewer_keywords:
- not function
ms.assetid: d2ddbd5c-33c0-4aff-8961-feac155b4ba1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ea6f505085b11abceaf204d2d2c17ef29bef347
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="not"></a>not

Alternatif! işleç.

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

**Başlık:** \<iso646.h >