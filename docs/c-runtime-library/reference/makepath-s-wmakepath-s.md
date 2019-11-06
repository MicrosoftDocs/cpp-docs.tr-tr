---
title: _makepath_s, _wmakepath_s
ms.date: 11/04/2016
api_name:
- _wmakepath_s
- _makepath_s
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
ms.openlocfilehash: 7bd85734e71120a214d652048c02c176728474b2
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624350"
---
# <a name="_makepath_s-_wmakepath_s"></a>_makepath_s, _wmakepath_s

Bileşenlerden bir yol adı oluşturur. Bunlar, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_makepath, _wmakepath](makepath-wmakepath.md) 'in sürümleridir.

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

*Yolun*<br/>
Tam yol arabelleği.

*sizeInWords*<br/>
Arabellekteki arabelleğin boyutu.

*sizeInBytes*<br/>
Arabelleğin bayt cinsinden boyutu.

*sürücü*<br/>
İstenen sürücüye karşılık gelen bir harf (A, B, vb.) ve isteğe bağlı bir sonda iki nokta içerir. **_makepath_s** , eksik ise bileşik yola otomatik olarak iki nokta ekler. *Sürücü* **null** veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesinde bir sürücü harfi görünmez.

*öğesini*<br/>
Sürücü göstergesini veya gerçek dosya adını içermeyen dizinlerin yolunu içerir. Sondaki eğik çizgi isteğe bağlıdır ve eğik çizgi (/) veya ters eğik çizgi (\\) ya da her ikisi birden tek bir *dır* bağımsız değişkeninde kullanılabilir. Sondaki eğik çizgi (/veya \\) belirtilmediyse, otomatik olarak eklenir. *Dır* **null** ise veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesine dizin yolu eklenmez.

*fname*<br/>
Dosya adı uzantıları olmayan taban dosya adını içerir. *Fname* **null** veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesine dosya adı eklenmez.

*leri*<br/>
Gerçek dosya adı uzantısını, önde gelen nokta (.) ile veya olmadan içerir. **_makepath_s** , *EXT*içinde görünmezse dönemi otomatik olarak ekler. *EXT* **null** ise veya boş bir dizeye işaret ediyorsa, bileşik *yol* dizesinde uzantı eklenmez.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*Yolun*|*sizeInWords* / *sizeInBytes*|döndürülmesini|*Yolun* içeriği|
|------------|------------------------------------|------------|------------------------|
|**DEĞER**|Kaydedilmemiş|**EıNVAL**|değiştirilmedi|
|Kaydedilmemiş|< = 0|**EıNVAL**|değiştirilmedi|

Yukarıdaki hata koşullarından herhangi biri oluşursa, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlevler **EINVAL**döndürür. *Drive*, *fname*ve *EXT*parametreleri için **null** öğesine izin verilir. Bu parametreler null işaretçiler veya boş dizeler olduğunda davranış hakkında daha fazla bilgi için, açıklamalar bölümüne bakın.

## <a name="remarks"></a>Açıklamalar

**_Makepath_s** işlevi, tek tek bileşenlerden bir bileşik yol dizesi oluşturur ve sonucu *yolda*depolar. *Yol* , bir sürücü harfi, dizin yolu, dosya adı ve dosya adı uzantısı içerebilir. **_wmakepath_s** , **_makepath_s**öğesinin geniş karakterli bir sürümüdür; **_wmakepath_s** bağımsız değişkenleri geniş karakterli dizelerdir. **_wmakepath_s** ve **_makepath_s** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*Yol* bağımsız değişkeni, tüm yolu tutabilecek kadar büyük olan boş bir arabelleğe işaret etmelidir. Bileşik *yolun* , Stdlib. h Içinde tanımlanan **_Max_path** sabitinden büyük olmaması gerekir.

Yol **null**Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Ayrıca, **errno** **EINVAL**olarak ayarlanır. Diğer tüm parametrelerde **null** değerlere izin verilir.

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_Crtsetdebugfillthreshold](crtsetdebugfillthreshold.md)kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_makepath_s**|\<Stdlib. h >|
|**_wmakepath_s**|\<Stdlib. h > veya \<wchar. h >|

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
