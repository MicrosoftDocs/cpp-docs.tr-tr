---
title: "_Statıc_assert makrosu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
- _STATIC_ASSERT
dev_langs:
- C++
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f62f2f2f5a0d78a0b77cb21d869be209d9293bd0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT Makrosu
Derleme zamanında bir ifade değerlendirme ve sonuç olduğunda bir hata oluştur `FALSE`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `booleanExpression`  
 İçin sıfır olmayan hesaplar (işaretçileri dahil) ifade (`TRUE`) veya 0 (`FALSE`).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu benzer [_ASSERT ve _ASSERTE makroları](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)dışında `booleanExpression` derleme zamanında yerine çalışma zamanında değerlendirilir. Varsa `booleanExpression` değerlendiren `FALSE` (0), [derleyici hatası C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) oluşturulur.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, biz denetleyin olup olmadığını `sizeof` bir `int` büyük veya 2 bayta eşit olup `sizeof` bir `long` 1 bayttır. Program derlenmez ve onu oluşturacaktır [derleyici hatası C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) çünkü bir `long` 1 bayt büyük.  
  
```  
// crt__static_assert.c  
  
#include <crtdbg.h>  
#include <stdio.h>  
  
_STATIC_ASSERT(sizeof(int) >= 2);  
_STATIC_ASSERT(sizeof(long) == 1);  // C2466  
  
int main()  
{  
    printf("I am sure that sizeof(int) will be >= 2: %d\n",  
        sizeof(int));  
    printf("I am not so sure that sizeof(long) == 1: %d\n",  
        sizeof(long));  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Makrosu|Gerekli başlık|  
|-----------|---------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h>|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR Makroları](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)