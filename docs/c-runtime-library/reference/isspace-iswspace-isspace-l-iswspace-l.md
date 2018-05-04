---
title: isspace, iswspace, _isspace_l, _iswspace_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- iswspace
- _isspace_l
- _iswspace_l
- isspace
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
- iswspace
- _istspace
- isspace
dev_langs:
- C++
helpviewer_keywords:
- iswspace function
- isspace function
- _iswspace_l function
- _isspace_l function
- iswspace_l function
- isspace_l function
- _istspace function
- istspace function
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 404fee8d74cec18c277f6c076a7cc41065a8b242
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="isspace-iswspace-isspacel-iswspacel"></a>isspace, iswspace, _isspace_l, _iswspace_l

Tamsayı bir boşluk karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isspace(
   int c
);
int iswspace(
   wint_t c
);
int _isspace_l(
   int c,
   _locale_t locale
);
int _iswspace_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test etmek için bir tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamları döndürür sıfır olmayan IF her *c* bir boşluk karakteri belirli bir gösterimidir. **isspace** sıfır olmayan bir değer döndürür *c* bir boşluk karakteri (0x09-0x0D veya 0x20). İçin test koşul sonucunu **isspace** işlevi bağımlı **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin olmayan sürümleri **_l** tüm yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; olan sürümleri **_l** kullandıkları dışında sonek aynı Bunun yerine geçirilen yerel ayar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

**iswspace** sıfır olmayan bir değer döndürür *c* standart bir boşluk karakteri karşılık gelen bir geniş karakter.

Davranışını **isspace** ve **_isspace_l** tanımsız ise *c* EOF değil veya 0'dan 0xFF (bunlar dahil) aralığında. CRT hata ayıklama Kitaplığı kullanıldığında ve *c* bu değerleri işlevleri raise onayı ifade değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istspace**|**isspace**|[_ismbcspace](ismbcgraph-functions.md)|**iswspace**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isspace**|\<CType.h >|
|**iswspace**|\<CType.h > veya \<wchar.h >|
|**_isspace_l**|\<CType.h >|
|**_iswspace_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
