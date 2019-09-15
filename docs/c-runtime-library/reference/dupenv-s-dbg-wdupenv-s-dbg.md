---
title: _dupenv_s_dbg, _wdupenv_s_dbg
ms.date: 11/04/2016
api_name:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
ms.openlocfilehash: 6c61986184f93c6cf6e83b33f77dce2bd017cfae
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937686"
---
# <a name="_dupenv_s_dbg-_wdupenv_s_dbg"></a>_dupenv_s_dbg, _wdupenv_s_dbg

Geçerli ortamdan bir değer alın.  Ek hata ayıklama bilgileri sağlamak için [_malloc_dbg](malloc-dbg.md) ile bellek ayıran [_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md) sürümleri.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _dupenv_s_dbg(
   char **buffer,
   size_t *numberOfElements,
   const char *varname,
   int blockType,
   const char *filename,
   int linenumber
);
errno_t _wdupenv_s_dbg(
   wchar_t **buffer,
   size_t * numberOfElements,
   const wchar_t *varname,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Değişkenin değerini depolayan arabellek.

*numberOfElements*<br/>
*Arabelleğin*boyutu.

*varname*<br/>
Ortam değişkeni adı.

*blockType*<br/>
Bellek bloğunun istenen türü: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
Kaynak dosyanın adı işaretçisi veya **null**.

*onayın*<br/>
Kaynak dosyadaki satır numarası veya **null**.

## <a name="return-value"></a>Dönüş Değeri

Başarı durumunda sıfır, hata durumunda hata kodu.

Bu işlevler parametrelerini doğrular; *buffer* veya *varname* **null**ise, [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **errno** olarak **EINVAL** ve **EINVAL**döndürür.

Bu işlevler yeterli bellek ayıramıyorsa, *buffer* 'ı null ve *numberOfElements* **değeri** 0 olarak ayarlar ve **ENOMEM**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Dupenv_s_dbg** ve **_wdupenv_s_dbg** işlevleri **_dupenv_s** ve **_wdupenv_s** ile aynıdır; ancak **_hata ayıklama** tanımlandığında, bu işlevler [malloc](malloc.md), [_malloc_dbg](malloc-dbg.md)hata ayıklama sürümünü kullanır ortam değişkeninin değeri için bellek ayırmak için. **_Malloc_dbg**hata ayıklama özellikleri hakkında daha fazla bilgi için, bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine, **_Crtdbg_map_polationbayrağını**tanımlayabilirsiniz. **_Crtdbg_map_ayırma** tanımlandığında, **_dupenv_s** ve **_wdupenv_s** çağrıları sırasıyla **_dupenv_s_dbg** ve **_Wdupenv_s_dbg**olarak eşlenir ve blok *türü* **_NORMAL_BLOCK**olarak ayarlanır. Bu nedenle, yığın bloklarını **_Client_block**olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Blok türleri hakkında daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s_dbg**|**_dupenv_s_dbg**|**_dupenv_s_dbg**|**_wdupenv_s_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dupenv_s_dbg**|\<Crtdbg. h >|
|**_wdupenv_s_dbg**|\<Crtdbg. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_dupenv_s_dbg.c
#include  <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[Ortam Sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
