---
title: vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l
ms.date: 11/04/2016
apiname:
- _vwprintf_s_l
- vwprintf_s
- _vprintf_s_l
- vprintf_s
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
- vprintf_s
- vwprintf_s
- _vtprintf_s
helpviewer_keywords:
- vwprintf_s_l function
- _vwprintf_s_l function
- vwprintf_s function
- _vtprintf_s_l function
- vprintf_s_l function
- vtprintf_s_l function
- _vtprintf_s function
- vtprintf_s function
- _vprintf_s_l function
- formatted text [C++]
- vprintf_s function
ms.assetid: cf864996-a530-4b40-9c30-54c4cef439c8
ms.openlocfilehash: 1bca7c39ebea75a0981c2a9a8238c854930353ea
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499136"
---
# <a name="vprintf_s-_vprintf_s_l-vwprintf_s-_vwprintf_s_l"></a>vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l

Bağımsız değişken listesi için bir işaretçi kullanarak biçimlendirilen çıktıyı yazar. [Vprintf, _vprintf_l, eprintf, _vwprintf_l](vprintf-vprintf-l-vwprintf-vwprintf-l.md) 'in bu SÜRÜMLERI, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

## <a name="syntax"></a>Sözdizimi

```C
int vprintf_s(
   const char *format,
   va_list argptr
);
int _vprintf_s_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int vwprintf_s(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_s_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*format*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişken listesi işaretçisi.

*ayarlar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**vprintf_s** ve **vwprintf_s** yazılan karakter sayısını, Sonlandırıcı null karakterini veya bir çıkış hatası oluşursa negatif bir değeri geri döndürür. *Biçim* null işaretçisiyse veya biçim dizesi geçersiz biçimlendirme karakterleri Içeriyorsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler-1 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bağımsız değişken listesi için bir işaretçi alır ve sonra verilen verileri **stdout**'a biçimlendirir ve yazar.

Bu işlevlerin güvenli sürümleri **vprintf** ve eprintf öğesinden yalnızca güvenli sürümlerin, biçim dizesinin geçerli biçimlendirme karakterleri içerip içermemesini denetlerindekilerle farklılık gösterir.

**vwprintf_s** , **vprintf_s**öğesinin geniş karakterli sürümüdür; Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **vprintf_s** Şu anda UNICODE bir akışa çıktıyı desteklemez.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtprintf_s**|**vprintf_s**|**vprintf_s**|**vwprintf_s**|
|**_vtprintf_s_l**|**_vprintf_s_l**|**_vprintf_s_l**|**_vwprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**vprintf_s**, **_vprintf_s_l**|\<stdio. h > ve \<stdarg. h >|\<varargs. h > *|
|**vwprintf_s**, **_vwprintf_s_l**|\<stdio. h > veya \<wchar. h > ve \<stdarg. h >|\<varargs. h > *|

\*UNIX V uyumluluğu için gereklidir.

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
