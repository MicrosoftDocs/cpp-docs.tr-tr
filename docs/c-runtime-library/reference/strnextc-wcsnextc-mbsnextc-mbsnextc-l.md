---
title: _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _strnextc
- _mbsnextc_l
- _mbsnextc
- _wcsnextc
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strnextc
- tcsnextc
- _mbsnextc_l
- _mbsnextc
- mbsnextc_l
- ftcsnextc
- mbsnextc
- _tcsnextc
- _wcsnextc
- _ftcsnextc
- _strnextc
- wcsnextc
dev_langs:
- C++
helpviewer_keywords:
- _mbsnextc function
- _tcsnextc function
- _wcsnextc function
- tcsnextc function
- strnextc function
- mbsnextc function
- _strnextc function
- _mbsnextc_l function
- mbsnextc_l function
- wcsnextc function
ms.assetid: e3086173-9eb5-4540-a23a-5d866bd05340
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d9e8eb7bb0aef8bdc64c296b55e6dc96c8ef050c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strnextc-wcsnextc-mbsnextc-mbsnextcl"></a>_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l

Bir dizede sonraki karakteri bulur.

> [!IMPORTANT]
> **_mbsnextc** ve **_mbsnextc_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _strnextc(
   const char *str
);
unsigned int _wscnextc(
   const wchar_t *str
);
unsigned int _mbsnextc(
   const unsigned char *str
);
unsigned int _mbsnextc_l(
   const unsigned char *str,
   _locale_t locale
);

```

### <a name="parameters"></a>Parametreler

*str*<br/>
Kaynak dizesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri sonraki karakteri tamsayı değerini döndürür *str*.

## <a name="remarks"></a>Açıklamalar

**_Mbsnextc** işlevi sonraki birden çok baytlı karakter tamsayı değerini döndürür *str*, dize imleci ilerletmeden olmadan. **_mbsnextc** göre çok baytlı karakter sıralarının tanıdığı [birden çok baytlı kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda.

Varsa *str* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi 0 değerini döndürür.

**Güvenlik Notu** bu API taşması sorundan duruma olası bir tehdit doğurur. Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnextc**|**_strnextc**|**_mbsnextc**|**_wcsnextc**|

**_strnextc** ve **_wcsnextc** tek bayt karakter dizesi ve geniş karakter dizesi sürümleri **_mbsnextc**. **_wcsnextc** sonraki geniş karakter olarak tamsayı değerini döndürür *str*; **_strnextc** sonraki tek baytlı karakter tamsayı değerini döndürür *str*. **_strnextc** ve **_wcsnextc** yalnızca bu eşleme için sağlanır ve aksi durumda kullanılmamalıdır. Daha fazla bilgi için bkz: [kullanarak genel metin eşlemeleri](../../c-runtime-library/using-generic-text-mappings.md) ve [genel metin eşlemeleri](../../c-runtime-library/generic-text-mappings.md).

**_mbsnextc_l** yerine geçirilen yerel ayar parametresi kullanan dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnextc**|\<Mbstring.h >|
|**_mbsnextc_l**|\<Mbstring.h >|
|**_strnextc**|\<Tchar.h >|
|**_wcsnextc**|\<Tchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
