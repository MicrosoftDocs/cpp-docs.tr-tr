---
description: 'Daha fazla bilgi edinin: SCC, SCC, SCC, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l'
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
ms.date: 11/04/2016
api_name:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: e6b979800caf404ee79f8913b0431b941acd20cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332694"
---
# <a name="iscsym-iscsymf-__iscsym-__iswcsym-__iscsymf-__iswcsymf-_iscsym_l-_iswcsym_l-_iscsymf_l-_iswcsymf_l"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

Bir tamsayının bir tanımlayıcıda kullanılabilecek bir karakteri temsil ettiğini belirleme.

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

*,*<br/>
Sınanacak tamsayı. *c* , işlevin dar karakter sürümü için 0-255 aralığında olmalıdır.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

*C* bir harf, alt çizgi veya rakam ise hem **__iscsym** hem de **__iswcsym** sıfır dışında bir değer döndürür. *C* bir harf veya alt çizgi ise hem **__iscsymf** hem de **__iswcsymf** sıfır dışında bir değer döndürür. Bu yordamların her biri, *c* , test koşulunu karşılamadığı takdirde 0 döndürür. **_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen *yerel ayarı* kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Açıklamalar

Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece bu yordamlar makrolar olarak tanımlanır. Bu yordamların makro sürümlerini kullandığınızda, bağımsız değişkenler birden çok kez değerlendirilebilirler. Bağımsız değişken listesi içinde yan etkileri olan ifadeleri kullanırken dikkatli olun.

Geriye dönük uyumluluk için, **SCC** ve **scc** 'ler yalnızca [&#95;&#95;stdc&#95;&#95;](../../preprocessor/predefined-macros.md) tanımlanmadığında veya 0 olarak tanımlandığında makrolar olarak tanımlanır; Aksi takdirde bunlar tanımsızdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**SCC** **, SCC,** **__iscsym**, **__iswcsym**, **__iscsymf**, **__iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, **_iswcsymf_l**|, \<ctype.h><br /><br /> C++: \<cctype> veya \<ctype.h>|

**SCC** **, SCC,** **__iscsym**, **__iswcsym**, **__iscsymf**, **__iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l** ve **_iswcsymf_l** yordamları Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
