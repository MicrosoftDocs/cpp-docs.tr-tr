---
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
ms.date: 11/04/2016
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
ms.openlocfilehash: 8ee84243b98c08504ac0bb63593e39c32230b706
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331642"
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

Bir tamsayı bir tanımlayıcı kullanılan bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test edilecek tamsayı. *c* işlevi dar karakter sürümü için 0-255 aralığında olmalıdır.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Her ikisi de **__iscsym** ve **__iswcsym** sıfır olmayan bir değer döndürür *c* bir harf, alt çizgi veya rakam. Her ikisi de **__iscsymf** ve **__iswcsymf** sıfır olmayan bir değer döndürür *c* bir harf veya alt çizgi. Bu yordamların her biri 0 döndürür *c* test koşulu karşılamayan. Sahip bu işlevlerin sürümleri **_l** sonekine kullanmaları dışında *yerel* geçerli yerel ayar yerine geçirilen yerel ayara bağlı davranışları için. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Açıklamalar

Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlı olmadığı sürece, bu yordamların makrolar tanımlanır. Bu yordamların makrosu sürümlerini kullandığınızda, bağımsız değişkenlerin birden fazla kez değerlendirilebilir. Bağımsız değişken listesi içinde yan etkisi olan ifade kullanırken dikkatli olun.

Geriye dönük uyumluluk için **iscsym** ve **iscsymf** makroları olarak tanımlanan yalnızca [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) tanımlı değil veya tanımlanır 0; Aksi takdirde bunlar tanımsız olur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**iscsym**, **iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, **_iswcsymf_l**|C: \<ctype.h ><br /><br /> C++: \<cctype > veya \<ctype.h >|

**İscsym**, **iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__ iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, ve **_iswcsymf_l** olan rutinleri Microsoft'a özgü. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
