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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 22a8ca8fa7e56a84289d7e90ffb519073f006b5c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332391"
---
# <a name="_searchenv-_wsearchenv"></a>_searchenv, _wsearchenv

Dosya aramak için ortam yollarını kullanır. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)bakın.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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
Aranacak dosyanın adı.

*Varname*<br/>
Aranacak ortam.

*Yoladı*<br/>
Tüm yolu depolamak için arabellek.

## <a name="remarks"></a>Açıklamalar

_searchenv **_searchenv** yordamolarak belirtilen etki alanında hedef dosyayı arar. *Varname* değişkeni herhangi bir ortam veya kullanıcı tanımlı değişken olabilir (örneğin, **PATH**, **LIB**, veya **INCLUDE**—dizin yollarının listesini belirtir. **_searchenv** büyük/küçük harf duyarlı olduğundan, *varname* ortam değişkeninin durumuyla eşleşmelidir.

Yordam ilk geçerli çalışma dizininde dosya yı arar. Dosyayı bulamazsa, ortam değişkeni tarafından belirtilen dizinlere bakar. Hedef dosya bu dizinlerden birindeyse, yeni oluşturulan yol *yol adına*kopyalanır. Dosya *adı* dosyası bulunamazsa, *yol adı* boş null-sonlandırılan dize içerir.

*Yol adı* arabelleği, yapılandırılan yol adının tam uzunluğunu karşılamak için en az **_MAX_PATH** karakter uzunluğunda olmalıdır. Aksi takdirde, **_searchenv** *yol adı* arabelleği aşabilir ve beklenmeyen davranışlara neden olabilir.

**_wsearchenv** **_searchenv**geniş karakterli bir sürümüdür ve **_wsearchenv** bağımsız değişkenleri geniş karakterli dizeleridir. **_wsearchenv** ve **_searchenv** aynı şekilde davranan.

*Dosya adı* boş bir dizeise, bu işlevler **ENOENT'i**döndürer.

*Dosya adı* veya yol *adı* **null** işaretçisi ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler -1 döndürün ve **EINVAL** **için errno** ayarlayın.

**Errno** ve hata kodları hakkında daha fazla bilgi için [bkz.](../../c-runtime-library/errno-constants.md)

C++'da, bu işlevler, bu işlevlerin daha yeni ve daha güvenli karşıtlarını çağıran şablon aşırı yüklemelerine sahiptir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv**|**_searchenv**|**_searchenv**|**_wsearchenv**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_searchenv**|\<stdlib.h>|
|**_wsearchenv**|\<stdlib.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dizin Kontrolü](../../c-runtime-library/directory-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)<br/>
