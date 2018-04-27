---
title: isprint, iswprint, _isprint_l, _iswprint_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
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
- iswprint
- _istprint
- isprint
dev_langs:
- C++
helpviewer_keywords:
- _istprint function
- iswprint function
- _iswprint_l function
- isprint_l function
- istprint function
- isprint function
- iswprint_l function
- _isprint_l function
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c98aebcc7155aa6c7afbeef9b0da9ce7e010a63c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="isprint-iswprint-isprintl-iswprintl"></a>isprint, iswprint, _isprint_l, _iswprint_l

Tamsayı yazdırılabilir bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isprint(
   int c
);
int iswprint(
   wint_t c
);
int _isprint_l(
   int c,
   _locale_t locale
);
int _iswprint_l(
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

Bu yordamları döndürür sıfır olmayan IF her *c* yazdırılabilir karakter belirli bir gösterimidir. **isprint** sıfır olmayan bir değer döndürür *c* yazdırılabilir karakter — bu boşluk karakteri içerir (0x20 - 0x7E). **iswprint** sıfır olmayan bir değer döndürür *c* yazdırılabilir bir geniş karakter — bu geniş karakter alanı içerir. Bu yordamlar her 0 döndürür *c* test durumu uygun değil.

Bu işlevler için test koşul sonucunu bağlıdır **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin olmayan sürümleri **_l** tüm yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; olan sürümleri **_l** kullandıkları dışında sonek aynı Bunun yerine geçirilen yerel ayar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Davranışını **isprint** ve **_isprint_l** tanımsız ise *c* EOF değil veya 0'dan 0xFF (bunlar dahil) aralığında. CRT hata ayıklama Kitaplığı kullanıldığında ve *c* bu değerleri işlevleri raise onayı ifade değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|tanımlanan _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istprint**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprint**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isprint**|\<CType.h >|
|**iswprint**|\<CType.h > veya \<wchar.h >|
|**_isprint_l**|\<CType.h >|
|**_iswprint_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
