---
title: _STATIC_ASSERT Makrosu
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
- _STATIC_ASSERT
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
ms.openlocfilehash: 78544424b727797158109fa3000ee2ebf8066cf7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229330"
---
# <a name="_static_assert-macro"></a>_STATIC_ASSERT Makrosu

Derleme zamanında bir ifadeyi değerlendirin ve sonuç **false**olduğunda bir hata oluşturun.

## <a name="syntax"></a>Söz dizimi

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sıfır (**true**) veya 0 (**false**) olarak değerlendirilen ifade (işaretçiler dahil).

## <a name="remarks"></a>Açıklamalar

Bu makro, [_assert ve _ASSERTE makrolarına benzer ve](assert-asserte-assert-expr-macros.md)bu durum, *Boolean* , çalışma zamanı yerine derleme zamanında değerlendirilir. *Boolean* **değeri false** (0) olarak değerlendirilirse, [derleyici hatası C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) oluşturulur.

## <a name="example"></a>Örnek

Bu örnekte, [sizeof](../../c-language/sizeof-operator-c.md) **`int`** a 'nın 2 bayta eşit veya daha büyük olup olmadığını ve [sizeof](../../c-language/sizeof-operator-c.md) a 'nın 1 bayt olup olmadığını denetliyoruz **`long`** . Program derlenmez ve 1 bayttan büyük olduğu için [derleyici hatası C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) oluşturacaktır **`long`** .

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

|Makroya|Gerekli başlık|
|-----------|---------------------|
|**_STATIC_ASSERT**|\<crtdbg.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_ASSERT, _ASSERTE _ASSERT_EXPR makrolar](assert-asserte-assert-expr-macros.md)<br/>
