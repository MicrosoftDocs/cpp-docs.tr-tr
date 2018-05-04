---
title: _mbsnbset_s, _mbsnbset_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbset_s_l
- _mbsnbset_s
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
- mbsnbset_s
- _mbsnbset_s_l
- _mbsnbset_s
- mbsnbset_s_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnset_s function
- mbsnbset_s function
- mbsnbset_s_l function
- _mbsnbset_s_l function
- _tcsnset_s_l function
- _mbsnbset_s function
- _tcsnset_s function
- tcsnset_s_l function
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07cbdc979ddd7ba240d9dcaf623d408b8c2681e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="mbsnbsets-mbsnbsetsl"></a>_mbsnbset_s, _mbsnbset_s_l

İlk Ayarlar **n** çok baytlı karakter dizesi belirtilen bir karakterin için bayt. Bu sürümleri [_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _mbsnbset_s(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count
);
errno_t _mbsnbset_s_l(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbset_s(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbset_s_l(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Değiştirilecek dize.

*Boyutu*<br/>
Dize arabellek boyutu.

*c*<br/>
Tek baytlı veya çok baytlı karakter ayarı.

*Sayısı*<br/>
Ayarlanacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde bir hata kodu.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbset_s** ve **_mbsnbset_s_l** işlevleri ayarla, en fazla ilk *sayısı* bayt *str* için *c*. Varsa *sayısı* uzunluğundan daha büyük *str*, uzunluğu *str* yerine kullanılan *sayısı*. Varsa *c* birden çok baytlı karakter ve tamamen tarafından belirtilen bayt son halinde ayarlanamaz *sayısı*, son bayta kalan boş bir karakter ile doldurulan. **_mbsnbset_s** ve **_mbsnbset_s_l** bir sonlandırma yerleştirmeyin sonunda null *str*.

**_mbsnbset_s** ve **_mbsnbset_s_l** benzer **_mbsnset**, bunlar ayarlanmış ancak bu *sayısı* bayt yerine *sayısı* karakter *c*.

Varsa *str* olan **NULL** veya *sayısı* sıfır açıklandığı gibi bu işlev bir geçersiz parametre özel durum oluşturur [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**. Ayrıca, varsa *c* geçerli bir birden çok baytlı karakter değil **errno** ayarlanır **EINVAL** ve boşluk yerine kullanılır.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. **_Mbsnbset_s** bu işlev sürümünü kullanan geçerli yerel ayar için bu yerel ayara bağımlı davranışı; **_mbsnbset_s_l** yerine yerel ayar parametresi kullanır ancak bu sürümü aynı o geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

C++'da, Bu işlevlerden birinin kullanımını şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer ve böylece boyutu bağımsız değişkeniyle belirtmek için gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

Bu işlevler hata ayıklama sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnset_s**|**_strnset_s**|**_mbsnbset_s**|**_wcsnset_s**|
|**_tcsnset_s_l**|`_strnset_s _l`|**_mbsnbset_s_l**|**_wcsnset_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbset_s**|\<Mbstring.h >|
|**_mbsnbset_s_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mbsnbset_s.c
#include <mbstring.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 bytes of string to be *'s */
   printf( "Before: %s\n", string );
   _mbsnbset_s( string, sizeof(string), '*', 4 );
   printf( "After:  %s\n", string );
}
```

## <a name="output"></a>Çıkış

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
