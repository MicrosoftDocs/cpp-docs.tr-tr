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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b92e056816183b4bbb07edb3efec4415655d655e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341589"
---
# <a name="_makepath-_wmakepath"></a>_makepath, _wmakepath

Bileşenlerden bir yol adı oluşturun. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)bakın.

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
Tam yol arabelleği.

*Sürücü*<br/>
İstenilen sürücüye karşılık gelen bir harf (A, B, vb.) ve isteğe bağlı bir iz bırakan kolon içerir. **_makepath,** eksikse kolon'u bileşik yola otomatik olarak ekler. *Sürücü* **NULL** ise veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesinde sürücü harfi görünmez.

*Dir*<br/>
Sürücü atası veya gerçek dosya adı dahil değil, dizinlerin yolunu içerir. Sondaki eğik çizgi isteğe bağlıdır ve ileri eğik\\çizgi (/) veya bir ters eğik çizgi ( ) veya her ikisi de tek bir *dir* bağımsız değişkeninde kullanılabilir. İzleyen eğik çizgi \\(/ veya) belirtilmemişse, otomatik olarak eklenir. *Dir* **NULL** ise veya boş bir dize işaret ederse, bileşik *yol* dizesine dizin yolu eklenmez.

*Fname*<br/>
Herhangi bir dosya adı uzantısı olmadan temel dosya adını içerir. *Fname* **NULL** veya boş bir dize işaret ederse, bileşik *yol* dizesine dosya adı eklenmez.

*Dahili*<br/>
Bir satır aralığı (.) ile veya olmadan gerçek dosya adı uzantısını içerir. **_makepath,** *ekst'te*görünmüyorsa dönemi otomatik olarak ekler. *Ext* **NULL** veya boş bir dize işaret ederse, bileşik *yol* dizesinde hiçbir uzantı eklenir.

## <a name="remarks"></a>Açıklamalar

**_makepath** işlevi, sonucu *yolda*depolayarak tek tek bileşenlerden bileşik bir yol dizesi oluşturur. *Yol* bir sürücü mektubu, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. **_wmakepath** **_makepath**geniş karakterli bir versiyonudur; **_wmakepath** bağımsız değişkenler geniş karakterli dizeleridir. **_wmakepath** ve **_makepath** aynı şekilde davranan.

**Güvenlik Notu** Null-terminatedli dize kullanın. Arabellek taşmasını önlemek için, null-sonlandırılan dize *yol* arabelleği boyutunu aşmamalıdır. **_makepath,** bileşik yol dizesinin uzunluğunun **_MAX_PATH**geçmemesini sağlamaz. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*Yol* bağımsız değişkeni, tam yolu tutabilecek kadar büyük boş bir arabelleğe işaret etmelidir. Bileşik *yol,* Stdlib.h'de tanımlanan **_MAX_PATH** sabitinden daha büyük olmamalıdır.

Yol **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Buna ek olarak, **errno** **EINVAL**olarak ayarlanır. **Null** değerleri diğer tüm parametreler için izin verilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
