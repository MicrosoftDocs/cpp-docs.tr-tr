---
title: _searchenv, _wsearchenv
ms.date: 4/2/2020
api_name:
- _searchenv
- _wsearchenv
- _o__searchenv
- _o__wsearchenv
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
- _wsearchenv
- _tsearchenv
- wsearchenv
- _searchenv
- searchenv
helpviewer_keywords:
- _wsearchenv function
- files [C++], finding
- _searchenv function
- tsearchenv function
- environment paths, searching for files
- _tsearchenv function
- wsearchenv function
- searchenv function
- environment paths
ms.assetid: 9c944a27-d326-409b-aee6-410e8762d9d3
ms.openlocfilehash: 83ba5663d569d449a0024db5abe2eb3ee903123b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913220"
---
# <a name="_searchenv-_wsearchenv"></a>_searchenv, _wsearchenv

Bir dosya aramak için ortam yollarını kullanır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md).

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
void _searchenv(
   const char *filename,
   const char *varname,
   char *pathname
);
void _wsearchenv(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname
);
template <size_t size>
void _searchenv(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
void _wsearchenv(
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

## <a name="remarks"></a>Açıklamalar

**_Searchenv** rutin, belirtilen etki alanındaki hedef dosyayı arar. *Varname* değişkeni, Dizin yollarının bir listesini belirten herhangi bir ortam veya Kullanıcı tanımlı değişken (örneğin, **Path**, **LIB**veya **Include**) olabilir. **_Searchenv** , büyük/küçük harfe duyarlı olduğundan, *varname* ortam değişkeni durumuyla eşleşmelidir.

Bu yordam, ilk olarak dosyayı geçerli çalışma dizininde arar. Dosyayı bulamazsa, ortam değişkeni tarafından belirtilen dizinlere bakar. Hedef dosya bu dizinlerden birinde ise, yeni oluşturulan yol, *yol adına*kopyalanır. Dosya *adı* dosyası bulunamazsa, *PathName* boş bir null ile sonlandırılmış dize içerir.

*Yol* adı arabelleği, oluşturulan yol adının tam uzunluğuna uyum sağlamak için en az **_MAX_PATH** karakter uzunluğunda olmalıdır. Aksi takdirde **_searchenv** , *yol adının* arabelleği taşarak beklenmedik davranışa neden olabilir.

**_wsearchenv** , **_searchenv**geniş karakterli bir sürümüdür ve **_wsearchenv** bağımsız değişkenler geniş karakterli dizelerdir. **_wsearchenv** ve **_searchenv** aynı şekilde davranır.

*Dosya adı* boş bir dize ise, bu Işlevler **ENOENT**döndürür.

*Filename* veya *PathName* **null** işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

**Errno** ve hata kodları hakkında daha fazla bilgi için bkz. [errno sabitleri](../../c-runtime-library/errno-constants.md).

C++ ' da, bu işlevlerde bu işlevlerin daha yeni ve daha güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv**|**_searchenv**|**_searchenv**|**_wsearchenv**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_searchenv**|\<Stdlib. h>|
|**_wsearchenv**|\<Stdlib. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_searchenv.c
// compile with: /W3
// This program searches for a file in
// a directory that's specified by an environment variable.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";

   // Search for file in PATH environment variable:
   _searchenv( searchfile, envvar, pathbuffer ); // C4996
   // Note: _searchenv is deprecated; consider using _searchenv_s
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 8\VC\BIN\CL.EXE
```

## <a name="see-also"></a>Ayrıca bkz.

[Dizin denetimi](../../c-runtime-library/directory-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)<br/>
