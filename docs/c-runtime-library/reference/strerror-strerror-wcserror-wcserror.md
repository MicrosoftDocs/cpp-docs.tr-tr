---
title: strerror, _strerror, _wcserror, __wcserror
ms.date: 11/04/2016
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
ms.openlocfilehash: 0b4d70687bc2f428162d035c80d6bc8525a8fb9e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958142"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Bir sistem hata iletisi dizesi (**strerror**, **_wcserror**) veya Kullanıcı tarafından sağlanan hata iletisi dizesinin ( **_strerror**, **__wcserror**) biçimlerini alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [strerror_s, _strerror_s, _wcserror_s \_, _wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

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

Bu işlevlerin hepsi hata iletisi dizesine bir işaretçi döndürür. Sonraki çağrılar dizenin üzerine yazabilir.

## <a name="remarks"></a>Açıklamalar

**Strerror** işlevi *errnum* 'ı bir hata iletisi dizesine eşler ve dizeye bir işaretçi döndürür. Hiçbir **strerror** ve **_strerror** gerçekten iletiyi yazdırır: Bunun için [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)gibi bir çıkış işlevi çağırmanız gerekir:

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*StrErrMsg* **null**olarak geçirildiyse, **_strerror** bir hata üreten son kitaplık çağrısının sistem hata iletisini içeren bir dizeye bir işaretçi döndürür. Hata iletisi dizesi yeni satır karakteri (' \n ') tarafından sona erdirildi. *StrErrMsg* **null**değerine eşit değilse **_strerror** , dize iletinizi, bir iki nokta üst üste, bir boşluğu, bir hata üreten son kitaplık çağrısının sistem hata iletisini ve yeni bir satır içeren bir dizeye işaretçi döndürür inde. Dize iletiniz en fazla 94 karakter uzunluğunda olabilir.

**_Strerror** için gerçek hata numarası [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)değişkeninde depolanır. Doğru sonuçlar oluşturmak için, bir kitaplık yordamı hata vererek hemen sonra **_strerror** çağrısı yapın. Aksi halde, sonraki **strerror** veya **_strerror** çağrıları, **errno** değerinin üzerine yazabilir.

**_wcserror** ve **__wcserror** , **strerror** ve **_strerror**'un sırasıyla geniş karakterli sürümleridir.

**_strerror**, **_wcserror**ve **__wcserror** , ANSI tanımının bir parçası değildir; Bunlar Microsoft uzantılardır ve bunları taşınabilir koda istediğiniz yerde kullanmanızı öneririz. ANSI uyumluluğu için bunun yerine **strerror** kullanın.

Hata dizelerini almak için, kullanım dışı bırakılan makrolar [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve kullanım dışı bırakılan iç işlevler **__sys_errlist** ve **__sys_nerr**yerine **strerror** veya **_wcserror** önerilir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
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

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
