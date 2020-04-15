---
title: strrchr, wcsrchr, _mbsrchr, _mbsrchr_l
ms.date: 4/2/2020
api_name:
- strrchr
- wcsrchr
- _mbsrchr
- _mbsrchr_l
- _o__mbsrchr
- _o__mbsrchr_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsrchr
- _ftcsrchr
- strrchr
- wcsrchr
- _mbsrchr
helpviewer_keywords:
- _mbsrchr function
- tcsrchr function
- mbsrchr_l function
- characters [C++], scanning for
- ftcsrchr function
- _tcsrchr function
- strings [C++], scanning
- mbsrchr function
- strrchr function
- scanning strings
- wcsrchr function
- _ftcsrchr function
- _mbsrchr_l function
ms.assetid: 75cf2664-758e-49bb-bf6b-8a139cd474d2
ms.openlocfilehash: b0aaa670cb6aa5af9e6f8a28234ba5c442d2f633
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365050"
---
# <a name="strrchr-wcsrchr-_mbsrchr-_mbsrchr_l"></a>strrchr, wcsrchr, _mbsrchr, _mbsrchr_l

Bir karakterin son oluşumu için bir dize tarar.

> [!IMPORTANT]
> `_mbsrchr`ve `_mbsrchr_l` Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char *strrchr(
   const char *str,
   int c
); // C only
char *strrchr(
   char *str,
   int c
); // C++ only
const char *strrchr(
   const char *str,
   int c
); // C++ only
wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C only
wchar_t *wcsrchr(
   wchar_t *str,
   wchar_t c
); // C++ only
const wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C++ only
unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C only
unsigned char *_mbsrchr(
   unsigned char *str,
   unsigned int c
); // C++ only
const unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C++ only
unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C only
unsigned char *_mbsrchr_l(
   unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
const unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Aramak için null-terminated string.

*C*<br/>
Karakter bulunacak.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi *str'deki* *son c* oluşumuna veya *c* bulunamazsa NULL'a verir.

## <a name="remarks"></a>Açıklamalar

İşlev `strrchr` *str*c *c* **(char**dönüştürülmüş) son oluşumunu bulur. Arama, sonlandırıcı null karakterini içerir.

`wcsrchr`ve `_mbsrchr` geniş karakterli ve çok bayt `strrchr`karakterli versiyonlarıdır. Bağımsız `wcsrchr` değişkenler ve geri dönüş değeri geniş karakterli dizeleri; olanlar `_mbsrchr` çok bayt karakterli dizeleri vardır.

C'de, bu işlevler ilk bağımsız değişken için bir **const** işaretçisi alır. C++'da iki aşırı yükleme kullanılabilir. Const için bir **const** işaretçi alarak aşırı yükleme **const**bir işaretçi döndürür; olmayan**const** bir işaretçi alır sürümü**non-const**bir işaretçi döndürür. Makro _CRT_CONST_CORRECT_OVERLOADS, bu işlevlerin **hem const** hem de**const** olmayan sürümleri varsa tanımlanır. Her iki C++ aşırı yüklemesi için**const** olmayan davranışı istiyorsanız, _CONST_RETURN simgesini tanımlayın.

`_mbsrchr`parametrelerini doğrular. *str* NULL ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine `errno` izin verilirse, EINVAL olarak ayarlanır ve `_mbsrchr` 0 döndürür. `strrchr`ve `wcsrchr` parametrelerini doğrulamayın. Bu üç işlev aynı şekilde çalışır.

Çıktı değeri, yerel LC_CTYPE kategori ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsrchr`|`strrchr`|`_mbsrchr`|`wcsrchr`|
|**Yok**|**Yok**|`_mbsrchr_l`|**Yok**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`strrchr`|\<string.h>|
|`wcsrchr`|\<string.h> \<veya wchar.h>|
|`_mbsrchr`, `_mbsrchr_l`|\<mbstring.h>|

Uyumluluk hakkında daha fazla bilgi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Kullanma `strrchr`örneği için, [bkz.](strchr-wcschr-mbschr-mbschr-l.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
