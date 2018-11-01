---
title: _searchenv_s, _wsearchenv_s
ms.date: 11/04/2016
apiname:
- _wsearchenv_s
- _searchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 40c2d0c42a3d61f84db78015388eba19742af06e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505683"
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s

Ortam yollarını kullanarak bir dosyayı arar. Bu sürümleri [_searchenv, _wsearchenv](searchenv-wsearchenv.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Dosya adı*<br/>
Aranacak dosyanın adı.

*varName*<br/>
Aranacak ortam.

*yol adı*<br/>
Tam yolu depolayan arabellek.

*numberOfElements*<br/>
Boyutu *pathname* arabellek.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; bir hata kodu.

Varsa *filename* boş bir dize ise dönüş değeri **ENOENT**.

### <a name="error-conditions"></a>Hata koşulları

|*Dosya adı*|*varName*|*yol adı*|*numberOfElements*|Dönüş değeri|İçeriğini *yol adı*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|Tüm|Tüm|**NULL**|Tüm|**EINVAL**|yok|
|**NULL**|Tüm|Tüm|Tüm|**EINVAL**|değiştirilmedi|
|Tüm|Tüm|Tüm|<= 0|**EINVAL**|değiştirilmedi|

Bu hata durumlardan biri oluşursa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Searchenv_s** yordamı hedef dosyayı belirtilen etki alanındaki arar. *Varname* herhangi bir ortam veya gibi dizin yolları listesi belirten kullanıcı tanımlı değişken olabilir **yolu**, **LIB**, ve **Ekle** . Çünkü **_searchenv_s** , duyarlıdır *varname* ortam değişkeninin durum eşleşmesi gerekir. Varsa *varname* mu işlem ortamında tanımlanan ortam değişkeni adı eşleşmiyor, sıfır döndürür ve *pathname* değişkendir değişmez.

Yordam önce dosyanın geçerli çalışma dizininde arar. Dosyayı bulamazsa, sonraki aracılığıyla ortam değişkeni tarafından belirtilen dizinleri arar. Hedef dosya bu dizinlerden birindeyse, yeni oluşturulan yol kopyalanır *pathname*. Varsa *filename* dosya bulunamadı, *pathname* boş bir null ile sonlandırılmış dize içerir.

*Pathname* arabellek olmalıdır en az **_MAX_PATH** oluşturulan yol adının tam uzunluğunu karşılamak için karakter uzunluğunda. Aksi takdirde, **_searchenv_s** arabelleğinden taşabilir *pathname* beklenmeyen davranışlara neden olur.

**_wsearchenv_s** geniş karakterli sürümüdür **_searchenv_s**; bağımsız değişkenler **_wsearchenv_s** geniş karakterli dizelerdir. **_wsearchenv_s** ve **_searchenv_s** aynı şekilde davranır.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h >|
|**_wsearchenv_s**|\<stdlib.h > veya \<wchar.h >|

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

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
