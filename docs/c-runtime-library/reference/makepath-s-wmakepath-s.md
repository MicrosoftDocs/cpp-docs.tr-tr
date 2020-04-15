---
title: _makepath_s, _wmakepath_s
ms.date: 4/2/2020
api_name:
- _wmakepath_s
- _makepath_s
- _o__makepath_s
- _o__wmakepath_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 3a44651cb9ff8be806c45c6b6c5f41f810319a85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341599"
---
# <a name="_makepath_s-_wmakepath_s"></a>_makepath_s, _wmakepath_s

Bileşenlerden bir yol adı oluşturur. Bunlar, [CRT'deki](makepath-wmakepath.md) Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle _wmakepath _makepath [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

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
Tam yol arabelleği.

*sizeInWords*<br/>
Sözcükteki arabelleğe boyutu.

*sizeBytes*<br/>
Arabellek bayt boyutu.

*Sürücü*<br/>
İstenilen sürücüye karşılık gelen bir harf (A, B, vb.) ve isteğe bağlı bir iz bırakan kolon içerir. **_makepath_s,** eksikse kolon'u bileşik yola otomatik olarak ekler. *Sürücü* **NULL** ise veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesinde sürücü harfi görünmez.

*Dir*<br/>
Sürücü atası veya gerçek dosya adı dahil değil, dizinlerin yolunu içerir. Sondaki eğik çizgi isteğe bağlıdır ve ileri eğik\\çizgi (/) veya bir ters eğik çizgi ( ) veya her ikisi de tek bir *dir* bağımsız değişkeninde kullanılabilir. İzleyen eğik çizgi \\(/ veya) belirtilmemişse, otomatik olarak eklenir. *Dir* **NULL** ise veya boş bir dize işaret ederse, bileşik *yol* dizesine dizin yolu eklenmez.

*Fname*<br/>
Herhangi bir dosya adı uzantısı olmadan temel dosya adını içerir. *Fname* **NULL** veya boş bir dize işaret ederse, bileşik *yol* dizesine dosya adı eklenmez.

*Dahili*<br/>
Bir satır aralığı (.) ile veya olmadan gerçek dosya adı uzantısını içerir. **_makepath_s,** *ekst'te*görünmüyorsa dönemi otomatik olarak ekler. *Ext* **NULL** veya boş bir dize işaret ederse, bileşik *yol* dizesinde hiçbir uzantı eklenir.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|*Yolu*|*sizeWords* / *sizeBytes*|Dönüş|*Yolun* içeriği|
|------------|------------------------------------|------------|------------------------|
|**Null**|herhangi bir|**Eınval**|değiştirilmemiş|
|herhangi bir|<= 0|**Eınval**|değiştirilmemiş|

Yukarıdaki hata koşullarından herhangi biri oluşursa, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütme devam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlevleri **EINVAL**döndürür. **NULL** *parametrelersürücü,* *fname*ve *ext*için izin verilir. Bu parametreler null işaretçileri veya boş dizeleri olduğunda davranış hakkında bilgi için Açıklamalar bölümüne bakın.

## <a name="remarks"></a>Açıklamalar

**_makepath_s** işlevi, sonucu *yolda*depolayarak tek tek bileşenlerden bileşik bir yol dizesi oluşturur. *Yol* bir sürücü mektubu, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. **_wmakepath_s** **_makepath_s**geniş karakterli bir versiyonudur; **_wmakepath_s** bağımsız değişkenleri geniş karakterli dizeleridir. **_wmakepath_s** ve **_makepath_s** aynı şekilde aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*Yol* bağımsız değişkeni, tam yolu tutabilecek kadar büyük boş bir arabelleğe işaret etmelidir. Bileşik *yol,* Stdlib.h'de tanımlanan **_MAX_PATH** sabitinden daha büyük olmamalıdır.

Yol **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Buna ek olarak, **errno** **EINVAL**olarak ayarlanır. **Null** değerleri diğer tüm parametreler için izin verilir.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
