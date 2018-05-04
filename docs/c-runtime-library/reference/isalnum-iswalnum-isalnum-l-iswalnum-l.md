---
title: isalnum, iswalnum, _isalnum_l, _iswalnum_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _iswalnum_l
- _isalnum_l
- iswalnum
- isalnum
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
- _istalnum_l
- _iswalnum_l
- iswalnum
- _isalnum_l
- isalnum
- _istalnum
dev_langs:
- C++
helpviewer_keywords:
- _istalnum function
- _ismbcalnum_l function
- iswalnum function
- isalnum function
- istalnum function
- _isalnum_l function
- _istalnum_l function
- _iswalnum_l function
ms.assetid: 0dc51306-ade8-4944-af27-e4176fc89093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c7c1156341d4c1b0b54d54f52a5a33eb6506e50
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="isalnum-iswalnum-isalnuml-iswalnuml"></a>isalnum, iswalnum, _isalnum_l, _iswalnum_l

Tamsayı alfasayısal bir karakterle temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isalnum( int c );
int iswalnum( wint_t c );
int _isalnum_l( int c,  _locale_t locale );
int _iswalnum_l( wint_t c, _locale_t locale );
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test etmek için bir tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamları döndürür sıfır olmayan IF her *c* alfasayısal bir karakterle belirli bir gösterimidir. **isalnum** , sıfır olmayan bir değer döndürür **isalpha** veya **isdigit** için sıfır olmayan bir değer olan *c*, diğer bir deyişle, varsa *c* içinde aralıkları A - Z, a - z veya 0 - 9. **iswalnum** , sıfır olmayan bir değer döndürür **iswalpha** veya **iswdigit** için sıfır olmayan bir değer olan *c*. Bu yordamlar her 0 döndürür *c* test durumu uygun değil.

Bu işlevleri sürümlerini **_l** soneki geçerli yerel yerine geçirilen yerel ayar parametresini kullanın. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Davranışını **isalnum** ve **_isalnum_l** tanımsız ise *c* EOF değil veya 0'dan 0xFF (bunlar dahil) aralığında. CRT hata ayıklama Kitaplığı kullanıldığında ve *c* bu değerleri işlevleri raise onayı ifade değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalnum**|**isalnum**|[_ismbcalnum](ismbcalnum-functions.md)|**iswalnum**|
|**_istalnum_l**|**_isalnum_l**|**_ismbcalnum_l**|**_iswalnum_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isalnum**|\<CType.h >|
|**iswalnum**|\<CType.h > veya \<wchar.h >|
|**_isalnum_l**|\<CType.h >|
|**_iswalnum_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
