---
title: _searchenv, _wsearchenv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _searchenv
- _wsearchenv
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
- _wsearchenv
- _tsearchenv
- wsearchenv
- _searchenv
- searchenv
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afcd461446f98024e04e44e28facae4fba65b0aa
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100411"
---
# <a name="searchenv-wsearchenv"></a>_searchenv, _wsearchenv

Bir dosyayı aramak için ortam yollarını kullanır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Dosya adı*<br/>
Aranacak dosyanın adı.

*varName*<br/>
Aranacak ortam.

*yol adı*<br/>
Tam yolu depolayan arabellek.

## <a name="remarks"></a>Açıklamalar

**_Searchenv** yordamı hedef dosyayı belirtilen etki alanındaki arar. *Varname* herhangi bir ortam veya kullanıcı tanımlı değişken olabilir — örneğin, **yolu**, **LIB**, veya **INCLUDE**— belirten bir dizin yolları listesi. Çünkü **_searchenv** , duyarlıdır *varname* ortam değişkeninin durum eşleşmesi gerekir.

Yordam önce dosyanın geçerli çalışma dizininde arar. Dosyayı bulamazsa, ortam değişkeni tarafından belirtilen dizinleri arar. Hedef dosya bu dizinlerden birindeyse, yeni oluşturulan yol kopyalanır *pathname*. Varsa *filename* dosya bulunamadı, *pathname* boş bir null ile sonlandırılmış dize içerir.

*Pathname* arabellek olmalıdır en az **_MAX_PATH** oluşturulan yol adının tam uzunluğunu karşılamak için karakter uzunluğunda. Aksi takdirde, **_searchenv** arabelleğinden taşabilir *pathname* arabellek ve beklenmeyen davranışlara neden olabilir.

**_wsearchenv** geniş karakterli sürümüdür **_searchenv**ve bağımsız değişkenleri **_wsearchenv** geniş karakterli dizelerdir. **_wsearchenv** ve **_searchenv** aynı şekilde davranır.

Varsa *filename* bu işlevler döndürür bir boş bir dize ise **ENOENT**.

Varsa *filename* veya *pathname* olduğu bir **NULL** işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Hakkında daha fazla bilgi için **errno** ve hata kodları [errno sabitleri](../../c-runtime-library/errno-constants.md).

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv**|**_searchenv**|**_searchenv**|**_wsearchenv**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_searchenv**|\<stdlib.h >|
|**_wsearchenv**|\<stdlib.h > veya \<wchar.h >|

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

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_searchenv_s, _wsearchenv_s](searchenv-s-wsearchenv-s.md)<br/>
