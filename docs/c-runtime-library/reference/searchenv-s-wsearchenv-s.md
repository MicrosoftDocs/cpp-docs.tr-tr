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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 3d526c546e1496b3b13b14a12c9025cbd0347cd2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332394"
---
# <a name="_searchenv_s-_wsearchenv_s"></a>_searchenv_s, _wsearchenv_s

Ortam yollarını kullanarak bir dosyayı arar. [CRT'deki](searchenv-wsearchenv.md) [Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi, _searchenv _wsearchenv bu sürümlerinde güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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
Aranacak dosyanın adı.

*Varname*<br/>
Aranacak ortam.

*Yoladı*<br/>
Tüm yolu depolamak için arabellek.

*numberOfElements*<br/>
*Yol adı* arabelleği boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu.

*Dosya adı* boş bir dizeise, iade değeri **ENOENT'tir.**

### <a name="error-conditions"></a>Hata Koşulları

|*filename*|*Varname*|*Yoladı*|*numberOfElements*|Döndürülen değer|Yol *adının* içeriği|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|herhangi bir|herhangi bir|**Null**|herhangi bir|**Eınval**|yok|
|**Null**|herhangi bir|herhangi bir|herhangi bir|**Eınval**|değiştirilmedi|
|herhangi bir|herhangi bir|herhangi bir|<= 0|**Eınval**|değiştirilmedi|

Bu hata koşullarından herhangi biri oluşursa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler EINVAL **için errno** ayarlayın ve **EINVAL** döndürün. **EINVAL**

## <a name="remarks"></a>Açıklamalar

**_searchenv_s** yordamolarak belirtilen etki alanında hedef dosya yı arar. *Varname* değişkeni, **PATH**, **LIB**ve **INCLUDE**gibi dizin yollarının listesini belirten herhangi bir ortam veya kullanıcı tanımlı değişken olabilir. **_searchenv_s** büyük/küçük harf duyarlı olduğundan, *varname* ortam değişkeninin durumuyla eşleşmelidir. *Varname,* işlemin ortamında tanımlanan bir ortam değişkeninin adı ile eşleşmiyorsa, işlev sıfır döndürür ve *yol adı* değişkeni değişmez.

Yordam, önce geçerli çalışma dizinindeki dosyayı arar. Dosyayı bulamazsa, çevre değişkeni tarafından belirtilen dizinler aracılığıyla sonraki bakar. Hedef dosya bu dizinlerden birindeyse, yeni oluşturulan yol *yol adına*kopyalanır. Dosya *adı* dosyası bulunamazsa, *yol adı* boş null-sonlandırılan dize içerir.

*Yol adı* arabelleği, yapılandırılan yol adının tam uzunluğunu karşılamak için en az **_MAX_PATH** karakter uzunluğunda olmalıdır. Aksi takdirde, **_searchenv_s,** beklenmeyen davranışlara neden olan *yol adı* arabelleği aşabilir.

**_wsearchenv_s** **_searchenv_s**geniş karakterli bir versiyonudur; **_wsearchenv_s** bağımsız değişkenler geniş karakterli dizeleridir. **_wsearchenv_s** ve **_searchenv_s** aynı şekilde davranan.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dizin Kontrolü](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
