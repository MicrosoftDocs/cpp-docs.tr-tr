---
title: isNaN, _isnan, _isnanf
ms.date: 01/31/2019
apiname:
- _isnan
- _isnanf
- isnan
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 8a907dd33803cebd7bc5d71789834d115333b6a0
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703096"
---
# <a name="isnan-isnan-isnanf"></a>isNaN, _isnan, _isnanf

Kayan nokta değerini (NAN) bir sayı olup olmadığını sınar.

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
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

C'de, **isnan** makrosu ve **_isnan** ve **_isnanf** işlevler ise sıfır olmayan bir değer döndürür bağımsız değişken *x* bir NAN olup; Aksi takdirde bunlar 0 değerini döndürür.

C++ ' ta **isnan** şablon işlevinin döndürdüğü **true** , bağımsız değişken *x* olduğu bir NaN; Aksi halde döndürür **false**.

## <a name="remarks"></a>Açıklamalar

NaN değerini başka bir NaN değerini eşit olarak karşılaştırmaz olduğundan, bu işlevler veya makro bir algılamak için kullanmanız gerekir. Belirtilen tür için IEEE 754 kayan nokta biçiminde kayan noktalı bir işlemin sonucunu temsil edilemeyen bir NaN üretilir. Çıkış için bir NaN nasıl temsil edildiğini hakkında daha fazla bilgi için bkz: [printf](printf-printf-l-wprintf-wprintf-l.md).

C++ derlendiğinde **isnan** Makro tanımlı değil ve bir **isnan** şablon işlevi yerine tanımlanır. Makro aynı şekilde davranır ancak türünde bir değer döndürür **bool** tamsayı değil.

**_İsnan** ve **_isnanf** Microsoft'a özgü işlevlerdir. **_İsnanf** işlevi, yalnızca x64 için derlendiğinde kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık (C)|Gerekli başlık (C++)|
|-------------|---------------------------|-------------------------------|
|**isnan**, **_isnanf**|\<Math.h >|\<Math.h > veya \<cmath >|
|**_isnan**|\<float.h >|\<float.h > veya \<cfloat >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnormal](isnormal.md)<br/>
