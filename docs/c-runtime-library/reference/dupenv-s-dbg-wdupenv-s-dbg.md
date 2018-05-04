---
title: _dupenv_s_dbg, _wdupenv_s_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
apitype: DLLExport
f1_keywords:
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
dev_langs:
- C++
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef129cec096734c23e911a5dc77bf3bd0b2df03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="dupenvsdbg-wdupenvsdbg"></a>_dupenv_s_dbg, _wdupenv_s_dbg

Geçerli ortamından bir değer alır.  Sürümleri [_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md) ile bellek tahsis [_malloc_dbg](malloc-dbg.md) ek hata ayıklama bilgileri sağlamak için.

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

*Arabellek*<br/>
Değişken değeri depolamak için bir arabellek.

*numberOfElements*<br/>
Boyutunu *arabellek*.

*varName*<br/>
Ortam değişkeni adı.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
Kaynak dosyanın adını işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyasında veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Başarılı, başarısız olduğunda bir hata kodu sıfır.

Bu işlevleri parametrelerini doğrulayın; varsa *arabellek* veya *varname* olan **NULL**, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, İşlevler kümesi **errno** için **EINVAL** ve geri dönüp **EINVAL**.

Bu işlevler için yeterli bellek ayıramıyor varsa, bunlar ayarlamak *arabellek* için **NULL** ve *numberOfElements* 0 ve return **ENOMEM**.

## <a name="remarks"></a>Açıklamalar

**_Dupenv_s_dbg** ve **_wdupenv_s_dbg** işlevleri aynı **_dupenv_s** ve **_wdupenv_s** dışında **_DEBUG** olan tanımlı, bu işlevleri hata ayıklama sürümü kullanma [malloc](malloc.md), [_malloc_dbg](malloc-dbg.md), ortam değişkeni değeri için bellek ayrılamadı. Hata ayıklama özellikleri hakkında bilgi için **_malloc_dbg**, bkz: [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, bayrağı tanımlayabilirsiniz **_CRTDBG_MAP_ALLOC**. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_dupenv_s** ve **_wdupenv_s** için eşleştirilir **_dupenv_s_dbg** ve **_wdupenv_s_dbg**, sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez **_clıent_block**. Blok türleri hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s_dbg**|**_dupenv_s_dbg**|**_dupenv_s_dbg**|**_wdupenv_s_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dupenv_s_dbg**|\<crtdbg.h >|
|**_wdupenv_s_dbg**|\<crtdbg.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
