---
title: strerror, _strerror, _wcserror, __wcserror
ms.date: 11/04/2016
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 4038fcc29c18e5d73024cbe5688c674e00d1409e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353865"
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Sistem hata iletisi dizesi alır (**strerror**, **_wcserror**) veya bir kullanıcı tarafından sağlanan hata iletisi dizesi biçimlendirir (**_strerror**, **__wcserror**). Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char *strerror(
   int errnum
);
char *_strerror(
   const char *strErrMsg
);
wchar_t * _wcserror(
   int errnum
);
wchar_t * __wcserror(
   const wchar_t *strErrMsg
);
```

### <a name="parameters"></a>Parametreler

*errnum*<br/>
Hata numarası.

*strErrMsg*<br/>
Kullanıcı tarafından sağlanan ileti.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin tümü, hata iletisi dizeye bir işaretçi döndürür. Sonraki çağrılar dize üzerine yazabilirsiniz.

## <a name="remarks"></a>Açıklamalar

**Strerror** işlevini eşlemeleri *errnum* bir hata iletisi dizesi ve dizeye bir işaretçi döndürür. Ne **strerror** ya da **_strerror** aslında iletiyi yazdırmaz: Bunun için çıkış işlevi çağırmak zorunda [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

Varsa *strErrMsg* olarak geçirilen **NULL**, **_strerror** bir hata oluşturan son kitaplık çağrısı için sistem hata iletisini içeren bir dizeye bir işaretçi döndürür. Hata iletisi dizesi, yeni satır karakteri ('\n') sonlandırılır. Varsa *strErrMsg* eşit değildir **NULL**, ardından **_strerror** (sırasıyla) dize iletinizin, bir iki nokta üst üste, boşluk, sistem hatası içeren bir dizeye bir işaretçi döndürür bir hata ve yeni satır karakteri oluşturan son kitaplık çağrısı iletisi. Dize iletiniz en fazla 94 karakter uzunluğunda olabilir.

Gerçek hata numarası **_strerror** değişkeninde depolanan [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Doğru sonuçlar üretmek için çağrı **_strerror** sonra hemen bir yordamı ile ilgili bir hata döndürür. Aksi takdirde, izleyen çağrılar **strerror** veya **_strerror** üzerine yazıp **errno** değeri.

**_wcserror** ve **__wcserror** geniş karakterli sürümleridir **strerror** ve **_strerror**sırasıyla.

**_strerror**, **_wcserror**, ve **__wcserror** ANSI tanımının bir parçası değildir; Microsoft uzantılarıdır ve siz bunları taşınabilir kod istediğiniz kullanmamanızı öneririz. ANSI uyumluluğu için kullanmak **strerror** yerine.

Hata dizelerini almak için önerilir **strerror** veya **_wcserror** kullanım dışı makroları yerine [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve kullanım dışı iç işlevleri **__sys_errlist** ve **__sys_nerr**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strerror**|\<String.h >|
|**_strerror**|\<String.h >|
|**_wcserror**, **__wcserror**|\<String.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [perror](perror-wperror.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
