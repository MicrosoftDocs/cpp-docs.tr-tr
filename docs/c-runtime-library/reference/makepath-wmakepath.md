---
title: _makepath, _wmakepath | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _makepath
- _wmakepath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21cfcfb8a1c82fb351b85b0fb169a94dd3c2c5d4
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105100"
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath

Bir yol adı bileşenlerini oluşturun. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>Parametreler

*Yolu*<br/>
Tam yol Ara.

*Sürücü*<br/>
Bir harf (A, B vb.) içeren istenen sürücü ve isteğe bağlı sondaki iki nokta karşılık gelen. **_makepath** eksik olup olmadığını iki nokta üst üste bileşik yolu otomatik olarak ekler. Varsa *sürücü* olduğu **NULL** veya noktaları boş bir dize için sürücü harfi görünür içinde bileşik *yolu* dize.

*dizini*<br/>
Sürücü göstergesi ya da gerçek dosya adı dahil değil, dizin yolunu içerir. Eğik isteğe bağlıdır ve eğik çizgi (/) veya ters eğik çizgi (\\) veya her ikisi de tek bir kullanılabilir *dir* bağımsız değişken. Sonda eğik çizgi olmadığına varsa (/ veya \\) belirtilirse, otomatik olarak eklenir. Varsa *dir* olduğu **NULL** veya noktalarına hiçbir dizin yolu boş bir dize içinde bileşik eklenen *yolu* dize.

*fname*<br/>
Herhangi bir dosya adı uzantısı olmadan temel dosya adı içeriyor. Varsa *fname* olduğu **NULL** veya dosya adı boş bir dize noktalarına bileşik içinde eklenen *yolu* dize.

*ext*<br/>
Gerçek dosya adı uzantısı ile veya olmadan başında nokta (.) içerir. **_makepath** dönemi içinde görünmüyorsa, otomatik olarak ekler *ext*. Varsa *ext* olduğu **NULL** veya işaret uzantısı boş bir dize içinde bileşik eklenen *yolu* dize.

## <a name="remarks"></a>Açıklamalar

**_Makepath** işlev sonucu içinde depolamadan bağımsız bileşenler bileşik yol dizesi oluşturur *yolu*. *Yolu* bir sürücü harfi, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. **_wmakepath** geniş karakterli sürümüdür **_makepath**; bağımsız değişkenler **_wmakepath** geniş karakterli dizelerdir. **_wmakepath** ve **_makepath** aynı şekilde davranır.

**Güvenlik Notu** null ile sonlandırılmış bir dize kullanın. Arabellek Taşması önlemek için null ile sonlandırılmış dize boyutunu aşamaz *yolu* arabellek. **_makepath** bileşik yol dizenin uzunluğu aşamaz emin olunmasını **_MAX_PATH**. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*Yolu* bağımsız değişken bir boş arabellek için tam yolu tutabilecek kadar büyük işaret etmelidir. Bileşik *yolu* değerinden büyük olmamalıdır **_MAX_PATH** sabiti Stdlıb.h içinde tanımlanır.

Yol ise **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Ayrıca, **errno** ayarlanır **EINVAL**. **NULL** diğer tüm parametreler için değerleri izin verilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_makepath**|\<stdlib.h >|
|**_wmakepath**|\<stdlib.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
