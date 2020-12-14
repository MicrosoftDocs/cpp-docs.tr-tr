---
description: 'Hakkında daha fazla bilgi edinin: isNaN, _isnan, _isnanf'
title: isnan, _isnan, _isnanf
ms.date: 01/31/2019
api_name:
- _isnan
- _isnanf
- isnan
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
ms.openlocfilehash: 819b53740c6717f0ba8d18376a38c91c80ee03c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211251"
---
# <a name="isnan-_isnan-_isnanf"></a>isnan, _isnan, _isnanf

Kayan nokta değerinin bir sayı (NAN) olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```C
int isnan(
   /* floating-point */ x
); /* C-only macro */

int _isnan(
   double x
);

int _isnanf(
   float x
); /* x64 only */

template <class T>
bool isnan(
   T x
) throw(); /* C++ only */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

C 'de, *x* bağımsız DEĞIŞKENI bir NaN ise **isnan** makrosu ve **_isnan** ve **_isnanf** işlevleri sıfır olmayan bir değer döndürür; Aksi takdirde 0 döndürür.

C++ ' da, **IsNaN** şablon işlevi, **`true`** *x* bağımsız değişkeni bir NaN ise döndürür; Aksi takdirde döndürür **`false`** .

## <a name="remarks"></a>Açıklamalar

NaN değeri başka bir NaN değerine eşit olarak karşılaştırmadığından, birini algılamak için bu işlevlerden veya makrolardan birini kullanmanız gerekir. Bir değer, kayan nokta işleminin sonucu belirtilen tür için IEEE-754 kayan nokta biçiminde gösterilemeyeceği zaman oluşturulur. Bir NaN 'nin çıkış için nasıl temsil edildiği hakkında bilgi için bkz. [printf](printf-printf-l-wprintf-wprintf-l.md).

C++ olarak derlendiğinde, **isNaN** makrosu tanımlı değildir ve bunun yerine bir **Inan** şablon işlevi tanımlanır. Makroyla aynı şekilde davranır, ancak tamsayı yerine bir değer döndürür **`bool`** .

**_İsnan** ve **_isnanf** işlevleri Microsoft 'a özgüdür. **_İsnanf** işlevi yalnızca x64 için derlendikleri zaman kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------------|-------------------------------|
|**isNaN**, **_isnanf**|\<math.h>|\<math.h> veya \<cmath>|
|**_isnan**|\<float.h>|\<float.h> veya \<cfloat>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnormal](isnormal.md)<br/>
