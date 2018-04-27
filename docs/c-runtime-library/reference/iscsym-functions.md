---
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 225a5ab6dd00619b825be5b7e5220de70aafc3ba
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

Tamsayı tanımlayıcıda kullanılabilir bir karakteri temsil edip etmediğini belirler.

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
Test etmek için bir tamsayı. *c* işlevi dar karakter sürümü için 0-255 aralığında olmalıdır.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Her ikisi de **__iscsym** ve **__iswcsym** sıfır olmayan bir değer döndürür *c* bir harf, alt çizgi veya sayı. Her ikisi de **__iscsymf** ve **__iswcsymf** sıfır olmayan bir değer döndürür *c* bir harf veya alt çizgi. Bu yordamlar her 0 döndürür *c* test durumu uygun değil. Bu işlevleri sürümlerini **_l** kullandıkları dışında sonek aynı *yerel* yerine geçerli yerel ayar için yerel ayara bağımlı davranışlarını geçirilen. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Açıklamalar

Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece bu yordamlar makroları olarak tanımlanır. Bu yordamlar makrosu sürümlerini kullanıyorsanız, bağımsız değişken birden çok kez değerlendirilebilir. Bağımsız değişken listesi içinde yan etkisi ifadeleri kullanırken dikkatli olun.

Geriye dönük uyumluluk için **iscsym** ve **iscsymf** makroları olarak tanımlanan yalnızca [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) tanımlı değil ya da tanımlanır 0; Aksi halde bunlar tanımlanmamış.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**iscsym**, **iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, **_iswcsymf_l**|C: \<ctype.h ><br /><br /> C++: \<cctype > veya \<ctype.h >|

**İscsym**, **iscsymf**, **__iscsym**, **__iswcsym**, **__iscsymf**, **__ iswcsymf**, **_iscsym_l**, **_iswcsym_l**, **_iscsymf_l**, ve **_iswcsymf_l** yordamları olan Microsoft belirli. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
