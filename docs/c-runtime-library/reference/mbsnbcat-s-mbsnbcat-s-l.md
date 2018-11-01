---
title: _mbsnbcat_s, _mbsnbcat_s_l
ms.date: 11/04/2016
apiname:
- _mbsnbcat_s_l
- _mbsnbcat_s
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
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
ms.openlocfilehash: d7e7a9d121336486e590ca3bd9e3967b02a2df08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497340"
---
# <a name="mbsnbcats-mbsnbcatsl"></a>_mbsnbcat_s, _mbsnbcat_s_l

Çok baytlı karakter dizesi için en çok ilk ekler **n** bayt başka bir çok baytlı karakter dizesi. Bunlar sürümleridir [_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md) açıklandığı gibi güvenlik geliştirmeleri mevcut olan [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Null ile sonlandırılmış çok baytlı karakter hedef dizesi.

*sizeInBytes*<br/>
Boyutu *dest* arabelleğinin bayt cinsinden.

*src*<br/>
Null ile sonlandırılmış çok baytlı karakter kaynak dizesi.

*Sayısı*<br/>
Bayt sayısı *src* eklenecek *dest*.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|**Hedef**|*sizeInBytes*|*src*|Dönüş değeri|
|------------|-------------------|-----------|------------------|
|**NULL**|Tüm|Tüm|**EINVAL**|
|Tüm|<= 0|Tüm|**EINVAL**|
|Tüm|Tüm|**NULL**|**EINVAL**|

Hata koşullardan herhangi biri meydana gelirse, işlev geçersiz parametre hata açıklandığı oluşturur [Parameter Validation](../../c-runtime-library/parameter-validation.md). Hata işlenirse, işlev döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbcat_s** işlevi ekler için *dest*, en çok ilk *sayısı* bayt *src*. Null karakter baytı, hemen önceyse *dest* bir ön bayt olduğundan ilk bayt tarafından üzerine yazılır *src*. Aksi takdirde, ilk baytı *src* Sonlandırıcı null karakterinin üzerine yazar *dest*. Bir boş bayt görünürse *src* önce *sayısı* baytları eklenmeden, **_mbsnbcat_s** öğesindeki tüm baytları ekler *src*, null kadar karakter. Varsa *sayısı* uzunluğundan büyükse *src*, uzunluğunu *src* yerine kullanılan *sayısı*. Ortaya çıkan dize bir null karakterle sonlandırılır. Kopyalama çakışan dizeler arasında yer alırsa davranış tanımsızdır.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Sürücüler, yoksa dışında bu işlevlerin sürümleri özdeş sahip **_l** soneki geçerli yerel ayarı ve sahip olanları kullanma **_l** soneki, bunun yerine yerel ayar parametresini kullanın Bu geçirildi. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak tanım Çıkarsama ve böylece bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kaldırmak ve bunlar otomatik olarak, yeni ve daha güvenli İşlevler, daha az güvenli eski işlevlerini değiştirmek için kullanabilirsiniz. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama sürümleri, ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat_s**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_s_l**|**_strncat_s_l**|**_mbsnbcat_s_l**|**_wcsncat_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcat_s**|\<Mbstring.h >|
|**_mbsnbcat_s_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
