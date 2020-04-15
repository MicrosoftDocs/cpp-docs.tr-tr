---
title: strerror, _strerror, _wcserror, __wcserror
description: Microsoft C Runtime Library (CRT) işlevlerini, strerror, _strerror, _wcserror ve __wcserror açıklar.
ms.date: 4/2/2020
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
- _o___wcserror
- _o__strerror
- _o__wcserror
- _o_strerror
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
ms.openlocfilehash: 9eecb7376cf476f0128dc20c8884746a3b4d47d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337324"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Bir sistem hatası ileti slalı **(strerror**, **_wcserror**) alır veya kullanıcı tarafından sağlanan hata iletisi dizesini biçimlendirin **(_strerror**, **__wcserror).** Bu işlevlerin daha güvenli sürümleri mevcuttur; [strerror_s, _strerror_s, \__wcserror_s, _wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
char * strerror(
   int errnum );

char * _strerror(
   const char *strErrMsg );

wchar_t * _wcserror(
   int errnum );

wchar_t * __wcserror(
   const wchar_t *strErrMsg );
```

### <a name="parameters"></a>Parametreler

*errnum*\
Hata numarası.

*strErrMsg*\
Kullanıcı tarafından sağlanan ileti.

## <a name="return-value"></a>Döndürülen değer

Bu işlevlerin tümü, çalışma zamanının sahip olduğu iş parçacığı yerel depolama arabelleğinde bir işaretçiyi hata iletisi dizesine döndürür. Daha sonra aynı iş parçacığı çağrıları bu dize üzerine yazabilirsiniz.

## <a name="remarks"></a>Açıklamalar

**Strerror** işlevi hata iletisi dizesini *eşler* ve bir işaretçiyi dize döndürür. **Strerror** ve **_strerror** işlevleri aslında iletiyi yazdırmaz. Yazdırmak için fprintf gibi bir çıktı işlevini [çağırın:](fprintf-fprintf-l-fwprintf-fwprintf-l.md)

```C
if (( _access( "datafile", 2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*strErrMsg* **NULL**olarak geçirilirse, **_strerror** bir işaretçiyi bir dize döndürür. Hata üreten son kitaplık çağrısının sistem hata iletisini içerir. Hata iletisi dizesi yeni satır karakteri ('\n') tarafından sonlandırılır. *strErrMsg* **NULL**olmadığında, dize sırayla içerir: *strErrMsg* dizeniz, bir üst üste, bir boşluk, sistem hata iletisi ve yeni bir çizgi karakteri. Dize mesajınız en fazla 94 karakter uzunluğunda, dar **(_strerror)** veya geniş **(__wcserror)** karakter olabilir.

**_strerror** için gerçek hata numarası değişken [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)saklanır. Doğru sonuçlar elde etmek için, kitaplık yordamı bir hata döndürdükten hemen sonra **_strerror** arayın. Aksi takdirde, daha sonra kitaplık yordamlarına yapılan çağrılar **errno** değerinin üzerine yazılabilir.

**_wcserror** ve **__wcserror** **sırasıyla strerror** ve **_strerror**geniş karaktersürümleridir.

**_strerror**, **_wcserror**ve **__wcserror,** Standart C kitaplığınbir parçası değildir Microsoft'a özgüdir. Bunları taşınabilir kodu istediğiniz yerde kullanmanızı önermiyoruz. Standart C uyumluluğu için **strerror'ı** kullanın.

Hata dizeleri almak için, _sys_errlist [ve](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve __sys_errlist ve **__sys_nerr**amortismana _sys_nerr makrolar **__sys_errlist** yerine **strerror** veya **_wcserror** öneririz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel metin yordam eşlemeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[perror](perror-wperror.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize işleme](../../c-runtime-library/string-manipulation-crt.md)\
[daha net](clearerr.md)\
[Ferror](ferror.md)\
[perror, _wperror](perror-wperror.md)
