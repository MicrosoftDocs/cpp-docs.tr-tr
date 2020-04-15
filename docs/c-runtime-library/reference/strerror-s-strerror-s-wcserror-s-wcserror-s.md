---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 4/2/2020
api_name:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
- _o__strerror_s
- _o__wcserror_s
- _o_strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
ms.openlocfilehash: ef712ecb6236513d169b4a8836b1365b0aca0633
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337364"
---
# <a name="strerror_s-_strerror_s-_wcserror_s-__wcserror_s"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Sistem hata iletisi alın **(strerror_s**, **_wcserror_s**) veya kullanıcı tarafından sağlanan bir hata iletisi yazdırın **(_strerror_s**, **__wcserror_s**). Bunlar, CRT'deki Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle [_wcserror strerror, \__strerror, _wcserror](strerror-strerror-wcserror-wcserror.md) [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

## <a name="syntax"></a>Sözdizimi

```C
errno_t strerror_s(
   char *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t _strerror_s(
   char *buffer,
   size_t numberOfElements,
   const char *strErrMsg
);
errno_t _wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t __wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *strErrMsg
);
template <size_t size>
errno_t strerror_s(
   char (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t _strerror_s(
   char (&buffer)[size],
   const char *strErrMsg
); // C++ only
template <size_t size>
errno_t _wcserror_s(
   wchar_t (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t __wcserror_s(
   wchar_t (&buffer)[size],
   const wchar_t *strErrMsg
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Hata dizesini tutmak için arabellek.

*numberOfElements*<br/>
Arabellek boyutu.

*errnum*<br/>
Hata numarası.

*strErrMsg*<br/>
Kullanıcı tarafından sağlanan ileti.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı, hata bir hata kodu.

### <a name="error-condtions"></a>Hata Condtions

|*Arabellek*|*numberOfElements*|*strErrMsg*|*Arabellek* içeriği|
|--------------|------------------------|-----------------|--------------------------|
|**Null**|herhangi bir|herhangi bir|yok|
|herhangi bir|0|herhangi bir|değiştirilmemiş|

## <a name="remarks"></a>Açıklamalar

**strerror_s** işlevi, *arabellekteki*dizeyi döndürerek hata iletisi dizesini *errnum* eşler. **_strerror_s** hata numarasını almaz; uygun iletiyi belirlemek için **errno'nun** geçerli değerini kullanır. Ne **strerror_s** ne de **_strerror_s** aslında mesajı yazdırır: Bunun [için, fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)gibi bir çıkış işlevi çağırmanız gerekir:

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

*strErrMsg* **NULL**ise , **_strerror_s** hata üreten son kitaplık çağrısı için sistem hata iletisini içeren *arabellekte* bir dize döndürür. Hata iletisi dizesi yeni satır karakteri ('\n') tarafından sonlandırılır. *strErrMsg* **NULL**eşit değilse, daha sonra **_strerror_s** (sırayla) dize ileti, bir üst üste, bir boşluk, bir hata üreten son kitaplık arama için sistem hata iletisi ve yeni bir satır karakteri içeren *arabellek* bir dize döndürür. Dize mesajınız en fazla 94 karakter uzunluğunda olabilir.

Bu işlevler, uzunluğu *OfElements* -1 sayısını aşarsa hata iletisini daraltmak. *Arabellekte* ortaya çıkan dize her zaman null-sonlandırılır.

**_strerror_s** için gerçek hata numarası değişken [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)saklanır. Sistem hata iletilerine, hata numarasıyla sıralanan iletiler dizisi olan [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)değişkeni üzerinden erişilir. **_strerror_s,** _sys_errlist değişkenine dizin olarak **errno** değerini **_sys_errlist**kullanarak uygun hata iletisine erişiyor. Değişken [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **değeri, _sys_errlist** dizisindeki en yüksek öğe sayısı olarak tanımlanır. Doğru sonuçlar elde etmek için, kitaplık yordamı bir hatayla döndükten hemen sonra **_strerror_s** arayın. Aksi takdirde, **strerror_s** veya **_strerror_s** sonraki aramalar **errno** değerini üzerine yazabilirsiniz.

**_wcserror_s** ve **__wcserror_s,** **sırasıyla strerror_s** ve **_strerror_s**geniş karakterli sürümleridir.

Bu işlevler parametrelerini doğrular. Arabellek **NULL** ise veya boyut parametresi 0 ise, geçersiz parametre işleyicisi, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlevleri **EINVAL** dönmek ve **EINVAL** **için errno** ayarlayın.

**_strerror_s**, **_wcserror_s**ve **__wcserror_s** ANSI tanımının bir parçası değildir, ancak bunun yerine Microsoft uzantılarıdır. Taşınabilirliğin istendiği yerlerde kullanmayın; ANSI uyumluluğu için bunun yerine **strerror_s** kullanın.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[perror](perror-wperror.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
