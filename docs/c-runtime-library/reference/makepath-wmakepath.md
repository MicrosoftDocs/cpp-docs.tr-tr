---
title: _makepath, _wmakepath
ms.date: 4/2/2020
api_name:
- _makepath
- _wmakepath
- _o__makepath
- _o__wmakepath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
ms.openlocfilehash: 19a20de40bb02e49f618e8e617c9659788dc3e25
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914390"
---
# <a name="_makepath-_wmakepath"></a>_makepath, _wmakepath

Bileşenlerden bir yol adı oluşturun. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

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

*Yolun*<br/>
Tam yol arabelleği.

*sürücü*<br/>
İstenen sürücüye karşılık gelen bir harf (A, B, vb.) ve isteğe bağlı bir sonda iki nokta içerir. **_makepath** eksik ise bileşik yola otomatik olarak iki nokta ekler. *Sürücü* **null** veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesinde bir sürücü harfi görünmez.

*öğesini*<br/>
Sürücü göstergesini veya gerçek dosya adını içermeyen dizinlerin yolunu içerir. Sondaki eğik çizgi isteğe bağlıdır, bir eğik çizgi (/) veya ters eğik çizgi (\\) ya da her ikisi tek bir *dir* bağımsız değişkeninde kullanılabilir. Sondaki eğik çizgi (/veya \\) belirtilmemişse, otomatik olarak eklenir. *Dır* **null** ise veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesine dizin yolu eklenmez.

*fname*<br/>
Dosya adı uzantıları olmayan taban dosya adını içerir. *Fname* **null** veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesine dosya adı eklenmez.

*leri*<br/>
Gerçek dosya adı uzantısını, önde gelen nokta (.) ile veya olmadan içerir. **_makepath** , *EXT*içinde görünmezse dönemi otomatik olarak ekler. *EXT* **null** ise veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesinde uzantı eklenmez.

## <a name="remarks"></a>Açıklamalar

**_Makepath** işlevi, tek tek bileşenlerden bir bileşik yol dizesi oluşturur ve sonucu *yolda*depolar. *Yol* , bir sürücü harfi, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. **_wmakepath** , **_makepath**geniş karakterli bir sürümüdür; **_wmakepath** bağımsız değişkenler geniş karakterli dizelerdir. **_wmakepath** ve **_makepath** aynı şekilde davranır.

**Güvenlik notunun** Null ile sonlandırılmış bir dize kullanın. Arabellek taşmasını önlemek için, null ile sonlandırılmış dize, *yol* arabelleğinin boyutunu aşmamalıdır. **_makepath** bileşik yol dizesinin uzunluğunun **_MAX_PATH**aşmadığından emin değil. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*Yol* bağımsız değişkeni, tüm yolu tutabilecek kadar büyük olan boş bir arabelleğe işaret etmelidir. Bileşik *yolun* Stdlib. h içinde tanımlanan **_MAX_PATH** sabitinden büyük olmaması gerekir.

Yol **null**Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Ayrıca, **errno** **EINVAL**olarak ayarlanır. Diğer tüm parametrelerde **null** değerlere izin verilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_makepath**|\<Stdlib. h>|
|**_wmakepath**|\<Stdlib. h> veya \<wchar. h>|

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

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
