---
title: _Statıc_assert makrosu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbbab8314a038d796ebd1a13342f3054e59f3e68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="staticassert-macro"></a>_STATIC_ASSERT Makrosu

Derleme zamanında bir ifade değerlendirme ve sonuç olduğunda bir hata oluştur **FALSE**.

## <a name="syntax"></a>Sözdizimi

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>Parametreler

*booleanDeyimi* için sıfır olmayan hesaplar (işaretçileri dahil) ifade (**TRUE**) veya 0 (**FALSE**).

## <a name="remarks"></a>Açıklamalar

Bu makrosu benzer [_ASSERT ve _ASSERTE makroları](assert-asserte-assert-expr-macros.md)dışında *booleanDeyimi* derleme zamanında yerine çalışma zamanında değerlendirilir. Varsa *booleanDeyimi* değerlendiren **FALSE** (0), [derleyici hatası C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) oluşturulur.

## <a name="example"></a>Örnek

Bu örnekte, biz denetleyin olup olmadığını [sizeof](../../c-language/sizeof-operator-c.md) bir **int** büyük veya 2 bayta eşit olup [sizeof](../../c-language/sizeof-operator-c.md) bir **uzun** 1 bayttır. Program derlenmez ve onu oluşturacaktır [derleyici hatası C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) çünkü bir **uzun** 1 bayt büyük.

```C
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
|**_STATIC_ASSERT**|\<crtdbg.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Makroları](assert-asserte-assert-expr-macros.md)<br/>
