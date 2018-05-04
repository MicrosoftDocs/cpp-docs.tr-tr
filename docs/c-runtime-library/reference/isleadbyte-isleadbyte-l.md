---
title: isleadbyte, _isleadbyte_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _isleadbyte_l
- isleadbyte
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
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 682cdde6983c5e590920c43418e510b9c275b34e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l

Bir karakter baytı birden çok baytlı karakter olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test etmek için bir tamsayı.

## <a name="return-value"></a>Dönüş Değeri

**isleadbyte** bağımsız değişkeni test durumu ya da 0 uymazsa yoksa sıfır olmayan bir değer döndürür. "C" yerel ayarını ve tek baytlı karakter (SBCS) yerel kümesi **isleadbyte** her zaman 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**İsleadbyte** makrosu bağımsız değişken birden çok baytlı karakter ilk baytını ise sıfır olmayan bir değer döndürür. **isleadbyte** tüm tamsayı bağımsız değişkeni-1 için anlamlı bir sonuç üretir (**EOF**) için **UCHAR_MAX** (0xFF) (dahil) arasındadır.

Beklenen bağımsız değişken türü **isleadbyte** olan **int**; imzalı karakter aktarılırsa derleyici öngörülemeyen sonuçlara sağlayan oturum uzantısı tarafından bir tamsayıya dönüştürmek.

Bu işlev ile sürümü **_l** sonekidir aynı yerel ayara bağımlı davranışı için geçerli yerel yerine geçirilen yerel ayar kullanır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Her zaman false döndürür|**_isleadbyte**|Her zaman false döndürür|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isleadbyte**|\<CType.h >|
|**_isleadbyte_l**|\<CType.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
