---
title: _searchenv_s, _wsearchenv_s
ms.date: 4/2/2020
api_name:
- _wsearchenv_s
- _searchenv_s
- _o__searchenv_s
- _o__wsearchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
ms.openlocfilehash: 5dd21013c8910ba07e2d23606af49bc80458dbc6
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918991"
---
# <a name="_searchenv_s-_wsearchenv_s"></a>_searchenv_s, _wsearchenv_s

Ortam yollarını kullanarak bir dosya arar. Bu _searchenv sürümleri [, _WSEARCHENV](searchenv-wsearchenv.md) [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char *pathname,
   size_t numberOfElements
);
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname,
   size_t numberOfElements
);
template <size_t size>
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Arama yapılacak dosyanın adı.

*varname*<br/>
Aranacak ortam.

*PathName*<br/>
Yolun tamamını depolayan arabellek.

*numberOfElements*<br/>
*Yol adı* arabelleğinin boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu.

*Dosya adı* boş bir **dize ise,** dönüş değeri kaydedilir.

### <a name="error-conditions"></a>Hata koşulları

|*filename*|*varname*|*PathName*|*numberOfElements*|Döndürülen değer|*Yol adının* içeriği|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|kaydedilmemiş|kaydedilmemiş|**DEĞER**|kaydedilmemiş|**EıNVAL**|yok|
|**DEĞER**|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|**EıNVAL**|değiştirilmedi|
|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|<= 0|**EıNVAL**|değiştirilmedi|

Bu hata koşullarından herhangi biri oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Searchenv_s** rutin, belirtilen etki alanındaki hedef dosyayı arar. *Varname* değişkeni, **Path**, **LIB**ve **Include**gibi dizin yollarının bir listesini belirten herhangi bir ortam veya Kullanıcı tanımlı değişken olabilir. **_Searchenv_s** , büyük/küçük harfe duyarlı olduğundan, *varname* ortam değişkeni durumuyla eşleşmelidir. *Varname* , işlemin ortamında tanımlanan bir ortam değişkeninin adı ile eşleşmiyorsa, işlev sıfır döndürür ve *yol adı* değişkeni değiştirilmez.

Bu yordam, ilk olarak geçerli çalışma dizinindeki dosya için arama yapar. Dosyayı bulamazsa, ortam değişkeni tarafından belirtilen dizinlerde bir sonrakine bakar. Hedef dosya bu dizinlerden birinde ise, yeni oluşturulan yol, *yol adına*kopyalanır. Dosya *adı* dosyası bulunamazsa, *PathName* boş bir null ile sonlandırılmış dize içerir.

*Yol* adı arabelleği, oluşturulan yol adının tam uzunluğuna uyum sağlamak için en az **_MAX_PATH** karakter uzunluğunda olmalıdır. Aksi takdirde, **_searchenv_s** *yol* arabelleğinin beklenmedik davranışa neden olduğu taşmayabilir.

**_wsearchenv_s** , **_searchenv_s**geniş karakterli bir sürümüdür; **_wsearchenv_s** bağımsız değişkenler geniş karakterli dizelerdir. **_wsearchenv_s** ve **_searchenv_s** aynı şekilde davranır.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_searchenv_s**|\<Stdlib. h>|
|**_wsearchenv_s**|\<Stdlib. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_searchenv_s.c
/* This program searches for a file in
* a directory specified by an environment variable.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";
   errno_t err;

   /* Search for file in PATH environment variable: */
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );
   if (err != 0)
   {
      printf("Error searching the path. Error code: %d\n", err);
   }
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE
```

## <a name="see-also"></a>Ayrıca bkz.

[Dizin denetimi](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
