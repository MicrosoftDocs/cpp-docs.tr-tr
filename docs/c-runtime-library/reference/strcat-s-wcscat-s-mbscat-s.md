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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 458c8ef4c69630b92f39c6ca13a538a1ba7ec72a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355425"
---
# <a name="strcat_s-wcscat_s-_mbscat_s-_mbscat_s_l"></a>strcat_s, wcscat_s, _mbscat_s, _mbscat_s_l

Bir dize ekler. [STRCAT, wcscat _mbscat](strcat-wcscat-mbscat.md) bu sürümleri, [CRT Güvenlik Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri var.

> [!IMPORTANT]
> **_mbscat_s** ve **_mbscat_s_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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
Null-sonlandırılan hedef dize arabelleği.

*numberOfElements*<br/>
Hedef dize arabelleği boyutu.

*strSource*<br/>
Null-sonlandırılan kaynak dize arabelleği.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|*strDestination*|*numberOfElements*|*strSource*|Döndürülen değer|*strDestination* içeriği|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL** veya belirsiz|herhangi bir|herhangi bir|**Eınval**|değiştirilmemiş|
|herhangi bir|herhangi bir|**Null**|**Eınval**|*strDestination*[0] 0 olarak ayarlandı|
|herhangi bir|0 veya çok küçük|herhangi bir|**Erange**|*strDestination*[0] 0 olarak ayarlandı|

## <a name="remarks"></a>Açıklamalar

**strcat_s** işlevi *strSource'u* *strDestination'a* ekler ve ortaya çıkan dizeyi null bir karakterle sonlandırır. *strSource'un* ilk *karakteri, strDestination'ın*sonlandırıcı null karakterini yazar. Kaynak ve hedef dizeleri çakışıyorsa **strcat_s** davranışı tanımsızdır.

İkinci parametrenin kalan boyutu değil, arabelleğenin toplam boyutu olduğunu unutmayın:

```C
char buf[16];
strcpy_s(buf, 16, "Start");
strcat_s(buf, 16, " End");               // Correct
strcat_s(buf, 16 - strlen(buf), " End"); // Incorrect
```

**wcscat_s** ve **_mbscat_s** **strcat_s**geniş karakterli ve çok bayt karakterli versiyonlarıdır. wcscat_s bağımsız **değişkenleri** ve geri dönüş değeri geniş karakterli dizeleridir; **_mbscat_s** çok bayt karakterli dizeleri vardır. Bu üç işlev aynı şekilde çalışır.

*strDestination* null işaretçisi ise veya null-sonlandırılmadıysa veya *strSource* **bir NULL** işaretçisiyse veya hedef dize çok küçükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** döndürün ve **EINVAL** **için errno** ayarlayın.

**_l** sonekolan işlevlerin sürümleri aynı davranışa sahiptir, ancak geçerli yerel alan yerine geçen yerel parametreyi kullanın. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscat_s**|**strcat_s**|**_mbscat_s**|**wcscat_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcat_s**|\<string.h>|
|**wcscat_s**|\<string.h> \<veya wchar.h>|
|**_mbscat_s**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[strcpy_s, wcscpy_s, _mbscpy_s'daki](strcpy-s-wcscpy-s-mbscpy-s.md)kod örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
