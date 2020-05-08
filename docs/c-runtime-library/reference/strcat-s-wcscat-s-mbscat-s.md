---
title: strcat_s, wcscat_s, _mbscat_s, _mbscat_s_l
ms.date: 4/2/2020
api_name:
- strcat_s
- _mbscat_s
- _mbscat_s_l
- wcscat_s
- _o__mbscat_s
- _o__mbscat_s_l
- _o_strcat_s
- _o_wcscat_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strcat_s
- wcscat_s
- _mbscat_s
- _mbscat_s_l
helpviewer_keywords:
- wcscat_s function
- strcat_s function
- mbscat_s function
- strings [C++], appending
- _mbscat_s function
- _mbscat_s_l function
- appending strings
ms.assetid: 0f2f9901-c5c5-480b-98bc-f8f690792fc0
ms.openlocfilehash: f7d890a753638112c4a1bb56cf6093a9510dbee2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910658"
---
# <a name="strcat_s-wcscat_s-_mbscat_s-_mbscat_s_l"></a>strcat_s, wcscat_s, _mbscat_s, _mbscat_s_l

Bir dize ekler. Strcat 'in bu sürümlerinde, [wcscat _mbscat](strcat-wcscat-mbscat.md) , [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

> [!IMPORTANT]
> **_mbscat_s** ve **_mbscat_s_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t strcat_s(
   char *strDestination,
   size_t numberOfElements,
   const char *strSource
);
errno_t wcscat_s(
   wchar_t *strDestination,
   size_t numberOfElements,
   const wchar_t *strSource
);
errno_t _mbscat_s(
   unsigned char *strDestination,
   size_t numberOfElements,
   const unsigned char *strSource
);
errno_t _mbscat_s_l(
   unsigned char *strDestination,
   size_t numberOfElements,
   const unsigned char *strSource,
   _locale_t locale
);
template <size_t size>
errno_t strcat_s(
   char (&strDestination)[size],
   const char *strSource
); // C++ only
template <size_t size>
errno_t wcscat_s(
   wchar_t (&strDestination)[size],
   const wchar_t *strSource
); // C++ only
template <size_t size>
errno_t _mbscat_s(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource
); // C++ only
template <size_t size>
errno_t _mbscat_s_l(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*strDestination*<br/>
Null ile sonlandırılmış hedef dize arabelleği.

*numberOfElements*<br/>
Hedef dize arabelleğinin boyutu.

*strSource*<br/>
Null ile sonlandırılmış kaynak dize arabelleği.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*strDestination*|*numberOfElements*|*strSource*|Döndürülen değer|*StrDestination* içeriği|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**Null** veya Sonlandırılmamış|kaydedilmemiş|kaydedilmemiş|**EıNVAL**|değiştirilmedi|
|kaydedilmemiş|kaydedilmemiş|**DEĞER**|**EıNVAL**|*strDestination*[0], 0 olarak ayarlandı|
|kaydedilmemiş|0 veya çok küçük|kaydedilmemiş|**ERANGE**|*strDestination*[0], 0 olarak ayarlandı|

## <a name="remarks"></a>Açıklamalar

**Strcat_s** Işlevi *strSource* 'u *strDestination* öğesine ekler ve elde edilen dizeyi null karakterle sonlandırır. *StrSource* başlangıç karakteri, *strDestination*'ın Sonlandırıcı null karakterinin üzerine yazar. Kaynak ve hedef dizeler çakıştığında **strcat_s** davranışı tanımsızdır.

İkinci parametrenin, kalan boyutu değil, arabelleğin toplam boyutu olduğunu unutmayın:

```C
char buf[16];
strcpy_s(buf, 16, "Start");
strcat_s(buf, 16, " End");               // Correct
strcat_s(buf, 16 - strlen(buf), " End"); // Incorrect
```

**wcscat_s** ve **_mbscat_s** , **strcat_s**geniş karakter ve çok baytlı karakter sürümleridir. **Wcscat_s** bağımsız değişkenleri ve dönüş değeri geniş karakterli dizelerdir; **_mbscat_s** olanlar çok baytlı karakter dizeleridir. Bu üç işlev, aynı şekilde davranır.

*StrDestination* null bir işaretçisiyse veya null sonlandırılırsa ya da *strSource* **null** işaretçisiyse veya hedef dize çok küçükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EINVAL** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

**_L** sonekine sahip işlevlerin sürümleri aynı davranışa sahiptir, ancak geçerli yerel ayar yerine geçirilen yerel ayar parametresini kullanın. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscat_s**|**strcat_s**|**_mbscat_s**|**wcscat_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcat_s**|\<String. h>|
|**wcscat_s**|\<String. h> veya \<wchar. h>|
|**_mbscat_s**|\<mbstring. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Strcpy_s, wcscpy_s _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)kod örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
