---
title: _makepath_s, _wmakepath_s
ms.date: 11/04/2016
apiname:
- _wmakepath_s
- _makepath_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
ms.openlocfilehash: 3536569fd3e77a353003e1372d5dc4ee6e4ee3fb
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210659"
---
# <a name="makepaths-wmakepaths"></a>_makepath_s, _wmakepath_s

Bir yol adı bileşenlerini oluşturur. Bunlar sürümleridir [_makepath, _wmakepath](makepath-wmakepath.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _makepath_s(
   char *path,
   size_t sizeInBytes,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
errno_t _wmakepath_s(
   wchar_t *path,
   size_t sizeInWords,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
template <size_t size>
errno_t _makepath_s(
   char (&path)[size],
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
); // C++ only
template <size_t size>
errno_t _wmakepath_s(
   wchar_t (&path)[size],
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Yolu*<br/>
Tam yol Ara.

*sizeInWords*<br/>
Sözcükleri arabellek boyutu.

*sizeInBytes*<br/>
Arabelleğin bayt cinsinden boyutu.

*Sürücü*<br/>
Bir harf (A, B vb.) içeren istenen sürücü ve isteğe bağlı sondaki iki nokta karşılık gelen. **_makepath_s** eksik olup olmadığını iki nokta üst üste bileşik yolu otomatik olarak ekler. Varsa *sürücü* olduğu **NULL** veya noktaları boş bir dize için sürücü harfi görünür içinde bileşik *yolu* dize.

*dizini*<br/>
Sürücü göstergesi ya da gerçek dosya adı dahil değil, dizin yolunu içerir. Eğik isteğe bağlıdır ve eğik çizgi (/) veya ters eğik çizgi (\\) veya her ikisi de tek bir kullanılabilir *dir* bağımsız değişken. Sonda eğik çizgi olmadığına varsa (/ veya \\) belirtilirse, otomatik olarak eklenir. Varsa *dir* olduğu **NULL** veya noktalarına hiçbir dizin yolu boş bir dize içinde bileşik eklenen *yolu* dize.

*fname*<br/>
Herhangi bir dosya adı uzantısı olmadan temel dosya adı içeriyor. Varsa *fname* olduğu **NULL** veya dosya adı boş bir dize noktalarına bileşik içinde eklenen *yolu* dize.

*ext*<br/>
Gerçek dosya adı uzantısı ile veya olmadan başında nokta (.) içerir. **_makepath_s** dönemi içinde görünmüyorsa, otomatik olarak ekler *ext*. Varsa *ext* olduğu **NULL** veya işaret uzantısı boş bir dize içinde bileşik eklenen *yolu* dize.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*Yolu*|*sizeInWords* / *sizeInBytes*|döndürülecek|İçeriğini *yolu*|
|------------|------------------------------------|------------|------------------------|
|**NULL**|Tüm|**EINVAL**|değiştirilmedi|
|Tüm|<= 0|**EINVAL**|değiştirilmedi|

Yukarıdaki hata koşullardan herhangi biri meydana gelirse, bu işlevler geçersiz parametre işleyicisi içinde açıklanan şekilde çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlevleri döndürür **EINVAL**. **NULL** parametrelerini izin verilen *sürücü*, *fname*, ve *ext*. Bu parametre null işaretçiler veya boş dizeler olduğunda davranışı hakkında bilgi için Açıklamalar bölümüne bakın.

## <a name="remarks"></a>Açıklamalar

**_Makepath_s** işlev sonucu içinde depolamadan bağımsız bileşenler bileşik yol dizesi oluşturur *yolu*. *Yolu* bir sürücü harfi, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. **_wmakepath_s** geniş karakterli sürümüdür **_makepath_s**; bağımsız değişkenler **_wmakepath_s** geniş karakterli dizelerdir. **_wmakepath_s** ve **_makepath_s** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*Yolu* bağımsız değişken bir boş arabellek için tam yolu tutabilecek kadar büyük işaret etmelidir. Bileşik *yolu* değerinden büyük olmamalıdır **_MAX_PATH** sabiti Stdlıb.h içinde tanımlanır.

Yol ise **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Ayrıca, **errno** ayarlanır **EINVAL**. **NULL** diğer tüm parametreler için değerleri izin verilir.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama sürümleri, ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h >|
|**_wmakepath_s**|\<stdlib.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_makepath_s.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];
   errno_t err;

   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",
                      "crt_makepath_s", "c" );
   if (err != 0)
   {
      printf("Error creating path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,
                       _MAX_FNAME, ext, _MAX_EXT );
   if (err != 0)
   {
      printf("Error splitting the path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path extracted with _splitpath_s:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c

Path extracted with _splitpath_s:
   Drive: c:
   Dir: \sample\crt\
   Filename: crt_makepath_s
   Ext: .c
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
