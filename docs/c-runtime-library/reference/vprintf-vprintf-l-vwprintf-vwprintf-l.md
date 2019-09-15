---
title: vprintf, _vprintf_l, vwprintf, _vwprintf_l
ms.date: 11/04/2016
api_name:
- vprintf
- _vwprintf_l
- _vprintf_l
- vwprintf
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- vwprintf
- _vtprintf
helpviewer_keywords:
- vwprintf function
- _vwprintf_l function
- vwprintf_l function
- _vtprintf function
- vtprintf_l function
- vprintf function
- _vprintf_l function
- vprintf_l function
- vtprintf function
- _vtprintf_l function
- formatted text [C++]
ms.assetid: 44549505-00a0-4fa7-9a85-f2e666f55a38
ms.openlocfilehash: b9b20e2c75c4819e966b42e6ae382fe041f8c4b0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945491"
---
# <a name="vprintf-_vprintf_l-vwprintf-_vwprintf_l"></a>vprintf, _vprintf_l, vwprintf, _vwprintf_l

Bağımsız değişken listesi için bir işaretçi kullanarak biçimlendirilen çıktıyı yazar. Bu işlevlerin daha güvenli sürümleri mevcuttur, bkz. [vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int vprintf(
   const char *format,
   va_list argptr
);
int _vprintf_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int vwprintf(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_l(
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

**vprintf** ve **eprintf** , yazılan karakter sayısını, Sonlandırıcı null karakterini veya bir çıkış hatası oluşursa negatif bir değeri geri döndürür. *Biçim* null işaretçisiyse veya biçim dizesi geçersiz biçimlendirme karakterleri Içeriyorsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler-1 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bağımsız değişken listesi için bir işaretçi alır ve sonra verilen verileri **stdout**'a biçimlendirir ve yazar.

**eprintf** , **vprintf**; öğesinin geniş karakterli sürümüdür Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **vprintf** Şu anda bir UNICODE akışına çıktıyı desteklememektedir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns). Geçersiz biçim dizelerinin algılandığını ve bir hatayla sonuçlandığını unutmayın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtprintf**|**vprintf**|**vprintf**|**diğer bir deyişle**|
|**_vtprintf_l**|**_vprintf_l**|**_vprintf_l**|**_vwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**vprintf**, **_vprintf_l**|\<stdio. h > ve \<stdarg. h >|\<varargs. h > *|
|**öprintf**, **_vwprintf_l**|\<stdio. h > veya \<wchar. h > ve \<stdarg. h >|\<varargs. h > *|

\*UNIX V uyumluluğu için gereklidir.

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
