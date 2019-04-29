---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 11/04/2016
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
ms.openlocfilehash: 00ff9d0df1a78d07eaa509201fb998b30396cc4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353828"
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Bir sistem hatası iletisi alın (**strerror_s**, **_wcserror_s**) veya bir kullanıcı tarafından sağlanan hata iletisi yazdırın (**_strerror_s**, **__wcserror_s** ). Bunlar sürümleridir [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Hata dizesini tutan arabellek.

*numberOfElements*<br/>
Arabellek boyutu.

*errnum*<br/>
Hata numarası.

*strErrMsg*<br/>
Kullanıcı tarafından sağlanan ileti.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, bir hata kodu.

### <a name="error-condtions"></a>Hata durumları

|*Arabellek*|*numberOfElements*|*strErrMsg*|İçeriğini *arabelleği*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|Tüm|Tüm|yok|
|Tüm|0|Tüm|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

**Strerror_s** işlevini eşlemeleri *errnum* bir hata mesajı dizesine eşliyor, dize döndüren *arabellek*. **_strerror_s** hata numarasını almaz geçerli değerini kullanan **errno** uygun iletiyi belirlemek için. Ne **strerror_s** ya da **_strerror_s** aslında iletiyi yazdırmaz: Bunun için gibi bir çıktı işlevi çağırmanız gerekir [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Varsa *strErrMsg* olduğu **NULL**, **_strerror_s** bir dize döndürür *arabellek* son kitaplık çağrısı için hata iletisinin içeren Bu bir hataya neden oldu. Hata iletisi dizesi, yeni satır karakteri ('\n') sonlandırılır. Varsa *strErrMsg* eşit değildir **NULL**, ardından **_strerror_s** bir dize döndürür *arabellek* (sırasıyla) dize iletinizin içeren bir iki nokta üst üste, boşluk, hata ve yeni satır karakteri oluşturan son kitaplık çağrısı için sistem hatası iletisi. Dize iletiniz en fazla 94 karakter uzunluğunda olabilir.

Uzunluğunu aşarsa, bu işlevlerin hata iletisini keser *numberOfElements* -1. İçerisindeki sonuç dizesi *arabellek* her zaman boş sonlandırılmıştır.

Gerçek hata numarası **_strerror_s** değişkeninde depolanan [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Sistem hata mesajlarına değişken üzerinden erişilen [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), hata numarasıyla sıralanan mesajlar dizisi olan. **_strerror_s** kullanarak uygun hata iletisine erişir **errno** değişkenine bir dizin olarak değer **_sys_errlist**. Değişkenin değerini [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) içindeki öğelerin maksimum sayısını olarak tanımlanan **_sys_errlist** dizisi. Doğru sonuçlar üretmek için çağrı **_strerror_s** sonra hemen bir yordamı ile ilgili bir hata döndürür. Aksi takdirde, izleyen çağrılar **strerror_s** veya **_strerror_s** üzerine yazıp **errno** değeri.

**_wcserror_s** ve **__wcserror_s** geniş karakterli sürümleridir **strerror_s** ve **_strerror_s**sırasıyla.

Bu işlevler kendi parametrelerini doğrular. Arabellek ise **NULL** veya boyut parametresi 0 olursa açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütmenin devam etmesine izin verilirse, İşlevler döndürür **EINVAL** ayarlayıp **errno** için **EINVAL**.

**_strerror_s**, **_wcserror_s**, ve **__wcserror_s** ANSI tanımının bir parçası değildir ancak bunun yerine Microsoft uzantılarıdır. Bunları, burada taşınabilirliğinin istendiği kullanmayın; ANSI uyumluluğu için kullanmak **strerror_s** yerine.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğu bir boyut bağımsız değişkeni belirtme gereksinimi ortadan otomatik olarak çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama sürümleri, ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<String.h >|
|**_wcserror_s**, **__wcserror_s**|\<String.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [perror](perror-wperror.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
