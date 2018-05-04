---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 362716963911a29a9b3558c387e69c4cd91b369e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Bir sistem hata iletisi alıyorum (**strerror_s**, **_wcserror_s**) veya bir kullanıcı tarafından sağlanan hata iletisini yazdırma (**_strerror_s**, **__wcserror_s** ). Sürümleri bunlar [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Hata dizesi tutmak için arabellek.

*numberOfElements*<br/>
Arabellek boyutu.

*errnum*<br/>
Hata numarası.

*strErrMsg*<br/>
Kullanıcı tarafından sağlanan ileti.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı olursa, hatasında bir hata kodu.

### <a name="error-condtions"></a>Hata Condtions

|*Arabellek*|*numberOfElements*|*strErrMsg*|İçeriği *arabellek*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|tüm|tüm|yok|
|tüm|0|tüm|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

**Strerror_s** işlev eşlemeleri *errnum* dizesi içinde bir hata iletisi dizesi döndüren *arabellek*. **_strerror_s** ; hata numarası almaz geçerli değeri kullanan **errno** uygun iletiyi belirlemek için. Ne **strerror_s** ya da **_strerror_s** gerçekten ileti yazdırır: bunun için bir çıktı işlevini gibi aramasına gerek [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Varsa *strErrMsg* olan **NULL**, **_strerror_s** bir dize döndürür *arabellek* son kitaplığı çağrısı için sistem hata iletisini içeren bir hataya neden oldu. Hata ileti dizesi yeni satır karakteri ('\n') tarafından sonlandırıldı. Varsa *strErrMsg* eşit değil **NULL**, ardından **_strerror_s** bir dize döndürür *arabellek* dize iletinizi (sırasıyla) içeren bir iki nokta üst üste, bir boşluk, bir hata ve yeni satır karakteri oluşturan son kitaplığı çağrısı için sistem hata iletisi. Dize ileti en fazla 94 karakterden uzun olamaz.

Uzunluğu aşarsa, bu işlevler hata iletisi kesmek *numberOfElements* -1. Sonuç dizesini *arabellek* her zaman null-sonlandırılır.

Gerçek hata numarası **_strerror_s** değişkeninde depolanan [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Sistem hata iletilerini değişken üzerinden erişilen [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), bir dizi hata numarasına göre sıralanmış iletileri olduğu. **_strerror_s** uygun hata iletisini kullanarak erişen **errno** değeri olarak değişken için bir dizin **_sys_errlist**. Değişkenin değerini [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) öğe maksimum sayısı olarak tanımlanan **_sys_errlist** dizi. Doğru sonuçlar üretmek için çağrı **_strerror_s** hemen bir hata ile kitaplığı yordamı döndükten sonra. Aksi takdirde, sonraki çağrılar **strerror_s** veya **_strerror_s** kılabilirsiniz **errno** değeri.

**_wcserror_s** ve **__wcserror_s** joker karakter sürümleri **strerror_s** ve **_strerror_s**sırasıyla.

Bu işlevler kendi parametreleri doğrulayın. Arabellek ise **NULL** veya boyutu parametresi 0 ise açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, işlevlerin dönüş **EINVAL** ve **errno** için **EINVAL**.

**_strerror_s**, **_wcserror_s**, ve **__wcserror_s** ANSI tanımının bir parçası değil ancak bunun yerine Microsoft uzantıları. Bunları, burada taşınabilirlik istenen kullanmayın; ANSI uyumluluğu için kullanmanız **strerror_s** yerine.

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

Bu işlevler hata ayıklama sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<String.h >|
|**_wcserror_s**, **__wcserror_s**|\<String.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [perror](perror-wperror.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
