---
title: isupper, _isupper_l, iswupper, _iswupper_l
ms.date: 11/04/2016
api_name:
- isupper
- iswupper
- _iswupper_l
- _isupper_l
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- isupper
- _istupper
- iswupper
helpviewer_keywords:
- istupper function
- iswupper function
- isupper_l function
- _isupper_l function
- iswupper_l function
- _istupper function
- _iswupper_l function
- isupper function
ms.assetid: da2bcc9f-241c-48c0-9a0e-ad273827e16a
ms.openlocfilehash: 558373d845b88d8959651d0a76e24af80cb6fa5e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953614"
---
# <a name="isupper-_isupper_l-iswupper-_iswupper_l"></a>isupper, _isupper_l, iswupper, _iswupper_l

Bir tamsayının büyük harfli bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isupper(
   int c
);
int _isupper_l (
   int c,
   _locale_t locale
);
int iswupper(
   wint_t c
);
int _iwsupper_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Sınanacak tamsayı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, *c* , büyük harfle belirli bir gösterimse sıfır olmayan bir değer döndürür. *c* , büyük harfli bir karakter (a-Z) ise, **IsUpper** sıfır dışında bir değer döndürür. *c* büyük harfe karşılık gelen geniş bir karakter ise **ıswupper** sıfır dışında bir değer döndürür ya da *c* , **iswcnp**, **ıswdigit** **'in hiçbiri için uygulama tanımlı geniş karakter kümesinden biridir iswpunct**veya **ıswspace** sıfırdan farklı. Bu yordamların her biri, *c* , test koşulunu karşılamadığı takdirde 0 döndürür.

**_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen yerel ayarı kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*C* , EOF veya 0 ile 0xFF (dahil) arasında değilse, **ıupper** ve **_isüste_l** 'nin davranışı tanımsızdır. Bir hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir onaylama işlemi yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istupper**|**isupper**|[_ismbcupper](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**iswupper**|
|**_istupper_l**|**_isüste_l**|[_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_iswüste_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isupper**|\<CType. h >|
|**_isüste_l**|\<CType. h >|
|**iswupper**|\<CType. h > veya \<wchar. h >|
|**_iswüste_l**|\<CType. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
