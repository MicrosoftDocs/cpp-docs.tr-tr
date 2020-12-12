---
description: 'Hakkında daha fazla bilgi edinin: _vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l'
title: _vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l
ms.date: 11/04/2016
api_name:
- _vwprintf_p
- _vprintf_p
- _vprintf_p_l
- _vwprintf_p_l
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
- _vwprintf_p_l
- vprintf_p
- _vprintf_p_l
- _vwprintf_p
- vprintf_p_l
- vwprintf_p_l
- vwprintf_p
- vtprintf_p
- _vtprintf_p
- _vprintf_p
helpviewer_keywords:
- _vtprintf_p_l function
- _vtprintf_p function
- vtprintf_p function
- _vwprintf_p function
- _vwprintf_p_l function
- _vprintf_p function
- _vprintf_p_l function
- vprintf_p_l function
- vwprintf_p function
- vprintf_p function
- vtprintf_p_l function
- vwprintf_p_l function
- formatted text [C++]
ms.assetid: 3f99bde3-c891-493d-908f-30559c421058
ms.openlocfilehash: 20bee781aa139335dbdbb2feac299e0dde8da8c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120649"
---
# <a name="_vprintf_p-_vprintf_p_l-_vwprintf_p-_vwprintf_p_l"></a>_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l

Bağımsız değişken listesi için bir işaretçi kullanarak biçimlendirilen çıktıyı yazar ve bağımsız değişkenlerin kullanıldığı sıranın belirtimini sağlar.

## <a name="syntax"></a>Sözdizimi

```C
int _vprintf_p(
   const char *format,
   va_list argptr
);
int _vprintf_p_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vwprintf_p(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_p_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*formatını*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişken listesi işaretçisi.

*locale*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**_vprintf_p** ve **_vwprintf_p** , sonlandıran null karakteri veya bir çıkış hatası oluşursa negatif bir değer dahil değil, yazılan karakter sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bağımsız değişken listesi için bir işaretçi alır ve sonra verilen verileri **stdout**'a biçimlendirir ve yazar. Bu işlevler **vprintf_s** ve **vwprintf_s** farklıdır ve yalnızca bağımsız değişkenlerin kullanıldığı sırayı belirleme yeteneğini desteklemezler. Daha fazla bilgi için bkz. [Printf_p Konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

**_vwprintf_p** , **_vprintf_p** öğesinin geniş karakterli sürümüdür; Akış ANSI modunda açılırsa iki işlev aynı şekilde davranır. **_vprintf_p** Şu anda UNICODE bir akışa çıktıyı desteklememektedir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

*Biçim* null işaretçisiyse veya biçim dizesi geçersiz biçimlendirme karakterleri Içeriyorsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler-1 döndürür ve **errno** , **EINVAL** olarak ayarlanır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtprintf_p**|**_vprintf_p**|**_vprintf_p**|**_vwprintf_p**|
|**_vtprintf_p_l**|**_vprintf_p_l**|**_vprintf_p_l**|**_vwprintf_p_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**_vprintf_p**, **_vprintf_p_l**|\<stdio.h> ve \<stdarg.h>|\<varargs.h>*|
|**_vwprintf_p**, **_vwprintf_p_l**|\<stdio.h> or \<wchar.h> ve \<stdarg.h>|\<varargs.h>*|

\* UNIX V uyumluluğu için gereklidir.

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout** ve **stderr** Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf_p Konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
