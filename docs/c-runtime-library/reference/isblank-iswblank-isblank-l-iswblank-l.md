---
title: EBOŞSA, iswblank, _isblank_l, _iswblank_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
dev_langs:
- C++
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dbf3c55f6a9665d8d6ad046dba653b362d46cd2a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l

Tamsayı boşluk karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
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

Bu yordamları döndürür sıfır olmayan IF her *c* belirli bir boşluk veya yatay sekme karakteri gösterimidir ya da yerel ayarlara özgü bir metin satırının içinde sözcükleri ayırmak için kullanılan karakter kümesi biridir. **EBOŞSA** sıfır olmayan bir değer döndürür *c* bir boşluk karakteri olduğunda (0x20) veya yatay sekme karakterini (0x09). İçin test koşul sonucunu **EBOŞSA** işlevleri bağımlı **LC_CTYPE** kategori ayar yerel; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md). Bu işlevlerin olmayan sürümleri **_l** tüm yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; olan sürümleri **_l** kullandıkları dışında sonek aynı Bunun yerine geçirilen yerel ayar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

**iswblank** sıfır olmayan bir değer döndürür *c* standart bir alana karşılık gelen bir geniş karakter ya da yatay sekme karakteri.

Davranışını **EBOŞSA** ve **_isblank_l** tanımsız ise *c* EOF değil veya 0'dan 0xFF (bunlar dahil) aralığında. CRT hata ayıklama Kitaplığı kullanıldığında ve *c* bu değerleri işlevleri raise onayı ifade değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**EBOŞSA**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**EBOŞSA**|\<CType.h >|
|**iswblank**|\<CType.h > veya \<wchar.h >|
|**_isblank_l**|\<CType.h >|
|**_iswblank_l**|\<CType.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
