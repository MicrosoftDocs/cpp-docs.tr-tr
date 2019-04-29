---
title: vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l
ms.date: 11/04/2016
apiname:
- _vfprintf_l
- vfprintf
- vfwprintf
- _vfwprintf_l
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
apitype: DLLExport
f1_keywords:
- vfwprintf
- _vftprintf
- vfprintf
helpviewer_keywords:
- _vfwprintf_l function
- _vftprintf function
- vfprintf function
- _vftprintf_l function
- vfprintf_l function
- vftprintf_l function
- vfwprintf_l function
- vftprintf function
- vfwprintf function
- _vfprintf_l function
- formatted text [C++]
ms.assetid: 4443be50-cedf-40b2-b3e2-ff2b3af3b666
ms.openlocfilehash: 889fedde263b9815597702f1e9d5b252f3998bdd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364902"
---
# <a name="vfprintf-vfprintfl-vfwprintf-vfwprintfl"></a>vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l

Bağımsız değişkenler listesine bir işaretçi kullanarak biçimlendirilmiş çıktı yazın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int vfprintf(
   FILE *stream,
   const char *format,
   va_list argptr
);
int _vfprintf_l(
   FILE *stream,
   const char *format,
   locale_t locale,
   va_list argptr
);
int vfwprintf(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
int _vfwprintf_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

*Biçim*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişkenler listesine işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**vfprintf** ve **vfwprintf** bir hata oluşursa, sondaki boş karakter veya negatif bir değer içermeyen yazılan karakter sayısını döndürür. Ya da *stream* veya *biçimi* null bir işaretçiyse, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, İşlevler -1 döndürür ve **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bir bağımsız değişken listesi için bir işaretçi alır sonra biçimlendirir ve belirtilen verileri Yazar *stream*.

**vfwprintf** öğesinin geniş karakterli sürümüdür **vfprintf**; akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **vfprintf** UNICODE akışına çıkış şu anda desteklemiyor.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftprintf**|**vfprintf**|**vfprintf**|**vfwprintf**|
|**_vftprintf_l**|**_vfprintf_l**|**_vfprintf_l**|**_vfwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üst bilgiler|
|-------------|---------------------|----------------------|
|**vfprintf**, **_vfprintf_l**|\<stdio.h > ve \<stdarg.h >|\<XENIX > *|
|**vfwprintf**, **_vfwprintf_l**|\<stdio.h > veya \<wchar.h >, ve \<stdarg.h >|\<XENIX > *|

\* UNIX V uyumluluğu için gerekli.

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
