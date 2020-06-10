---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 06/09/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 91be8803a0695670e7afe673b25b54fccde40a9c
ms.sourcegitcommit: 8167c67d76de58a7c2df3b4dcbf3d53e3b151b77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2020
ms.locfileid: "84664332"
---
# <a name="strerror_s-_strerror_s-_wcserror_s-__wcserror_s"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Bir sistem hata iletisi (**strerror_s**, **_wcserror_s**) veya Kullanıcı tarafından sağlanan bir hata iletisi (**_strerror_s**, **__wcserror_s**) alın. Bu sürümler, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle [, _strerror, _wcserror \_ _wcserror](strerror-strerror-wcserror-wcserror.md) .

## <a name="syntax"></a>Söz dizimi

```C
errno_t strerror_s(
   char *buffer,
   size_t sizeInBytes,
   int errnum
);
errno_t _strerror_s(
   char *buffer,
   size_t sizeInBytes,
   const char *strErrMsg
);
errno_t _wcserror_s(
   wchar_t *buffer,
   size_t sizeInWords,
   int errnum
);
errno_t __wcserror_s(
   wchar_t *buffer,
   size_t sizeInWords,
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

*arabelleğin*<br/>
Hata dizesini tutan arabellek.

*sizeInBytes*<br/>
Arabellekteki bayt sayısı.

*sizeInWords*<br/>
Arabellekteki sözcüklerin sayısı.

*errnum*<br/>
Hata numarası.

*strErrMsg*<br/>
Kullanıcı tarafından sağlanan ileti.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, hata durumunda hata kodu.

### <a name="error-condtions"></a>Hata onayları

|*arabelleğin*|*sizeInBytes/sizeInWords*|*strErrMsg*|*Arabelleğin* içeriği|
|--------------|------------------------|-----------------|--------------------------|
|**DEĞER**|herhangi biri|herhangi biri|yok|
|herhangi biri|0|herhangi biri|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

**Strerror_s** işlevi, hata iletisi dizesine hatayı, dizeyi *arabelleğe* *döndürerek eşleştirir.* **_strerror_s** hata numarası almaz; uygun iletiyi belirleyebilmek için **errno** geçerli değerini kullanır. Ne **strerror_s** ne de **_strerror_s** iletiyi yazdırmaz: bunun için [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)gibi bir çıkış işlevi çağırmanız gerekir:

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

*StrErrMsg* **null**ise **_strerror_s** , bir hata üreten son kitaplık çağrısının sistem hata iletisini içeren *arabellekte* bir dize döndürür. Hata iletisi dizesi yeni satır karakteri (' \n ') tarafından sona erdirildi. *StrErrMsg* , **null**değerine eşit değilse, **_strerror_s** dize iletinizi, iki nokta üst üste, bir boşluk, bir hata üreten son kitaplık çağrısının sistem hata iletisini ve yeni satır *karakterini içeren bir* dize döndürür. Dize iletiniz en fazla 94 karakter uzunluğunda olabilir.

Bu işlevler, uzunluğu buffer-1 boyutunu aşarsa hata iletisini keser. *Arabellekte* elde edilen dize her zaman null olarak sonlandırılır.

**_Strerror_s** için gerçek hata numarası [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)değişkeninde depolanır. Sistem hata iletilerine, hata numarasına göre sıralanmış bir ileti dizisi olan [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)değişken aracılığıyla erişilir. **_strerror_s** , **_sys_errlist**değişkenine dizin olarak **errno** değeri kullanarak uygun hata iletisine erişir. [_Sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) değişkeninin değeri, **_sys_errlist** dizisindeki en fazla öğe sayısı olarak tanımlanır. Doğru sonuçlar oluşturmak için, bir kitaplık yordamı hata ile çağrıldıktan hemen sonra **_strerror_s** çağırın. Aksi takdirde, **strerror_s** veya **_strerror_s** sonraki çağrıları **errno** değerinin üzerine yazabilir.

**_wcserror_s** ve **__wcserror_s** , sırasıyla **strerror_s** ve **_strerror_s**geniş karakterli sürümleridir.

Bu işlevler, parametrelerini doğrular. Buffer **null** ise veya boyut parametresi 0 Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md) bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **EINVAL** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

**_strerror_s**, **_WCSERROR_S**ve **__wcserror_s** ANSI tanımının bir parçası değildir ancak bunun yerine Microsoft uzantısı olur. Bunları, taşınabilirliği istediğiniz yerde kullanmayın; ANSI uyumluluğu için bunun yerine **strerror_s** kullanın.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz. [pError](perror-wperror.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
