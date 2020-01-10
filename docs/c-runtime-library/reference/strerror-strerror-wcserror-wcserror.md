---
title: strerror, _strerror, _wcserror, __wcserror
description: Microsoft C çalışma zamanı kitaplığı (CRT) işlevleri strerror, _strerror, _wcserror ve __wcserror açıklanır.
ms.date: 01/07/2020
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
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
ms.openlocfilehash: 8c9c6850d6620407897b2a3a1dbf32e61f6719c0
ms.sourcegitcommit: 7bd3567fc6a0e7124aab51cad63bbdb44a99a848
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75755028"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Bir sistem hata iletisi dizesi (**strerror**, **_wcserror**) veya Kullanıcı tarafından sağlanan hata iletisi dizesinin ( **_strerror**, **__wcserror**) biçimlerini alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

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

## <a name="return-value"></a>Dönüş değeri

Bu işlevlerin hepsi, çalışma zamanına ait bir iş parçacığı yerel depolama arabelleğinde bir hata iletisi dizesine bir işaretçi döndürür. Aynı iş parçacığında daha sonra yapılan çağrılar bu dizenin üzerine yazabilir.

## <a name="remarks"></a>Açıklamalar

**Strerror** işlevi *errnum* 'ı bir hata iletisi dizesine eşler ve dizeye bir işaretçi döndürür. **Strerror** ve **_strerror** işlevleri aslında iletiyi yazdırmaz. Yazdırmak için [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)gibi bir çıkış işlevi çağırın:

```C
if (( _access( "datafile", 2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*StrErrMsg* **NULL**olarak geçirilirse **_strerror** bir dizeye bir işaretçi döndürür. Bir hata üreten son kitaplık çağrısının sistem hata iletisini içerir. Hata iletisi dizesi yeni satır karakteri (' \n ') tarafından sona erdirildi. *StrErrMsg* **null**olmadığında dize: *strErrMsg* dizeniz, iki nokta üst üste, bir boşluk, sistem hata iletisi ve yeni satır karakteri içerir. Dize iletiniz, en çok 94 karakter uzunluğunda olabilir ve her iki dar ( **_strerror**) veya geniş ( **__wcserror**) karakterden oluşabilir.

**_Strerror** için gerçek hata numarası [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)değişkeninde depolanır. Doğru sonuçlar oluşturmak için, bir kitaplık yordamının hata döndürmesine hemen sonra **_strerror** çağırın. Aksi halde, daha sonra kitaplık yordamlarına yapılan çağrılar **errno** değerinin üzerine yazabilir.

**_wcserror** ve **__wcserror** , sırasıyla **strerror** ve **_strerror**'in geniş karakterli sürümleridir.

**_strerror**, **_Wcserror**ve **__wcserror** standart C kitaplığının bir parçası değil, Microsoft 'a özgüdür. Bunları, taşınabilir kod istediğiniz yerde kullanmanız önerilmez. Standart C uyumluluğu için, bunun yerine **strerror** kullanın.

Hata dizelerini almak için, kullanım dışı bırakılmış makrolar yerine **strerror** veya **_wcserror** önerilir [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve kullanım dışı iç işlevler **__sys_errlist** ve **__sys_nerr**.

### <a name="generic-text-routine-mappings"></a>Genel metin rutin eşlemeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strerror**|\<String. h >|
|**_strerror**|\<String. h >|
|**_wcserror**, **__wcserror**|\<String. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz. [pError](perror-wperror.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize işleme](../../c-runtime-library/string-manipulation-crt.md)\
[clearerr](clearerr.md)\
[ferror](ferror.md)\
[perror, _wperror](perror-wperror.md)
