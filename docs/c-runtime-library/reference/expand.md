---
title: _expand
ms.date: 11/04/2016
api_name:
- _expand
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
ms.openlocfilehash: cb986d893bd862e61ae595317a890fb489c19919
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941550"
---
# <a name="_expand"></a>_expand

Bellek bloğunun boyutunu değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void *_expand(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Önceden ayrılmış bellek bloğuna yönelik işaretçi.

*boyutla*<br/>
Bayt cinsinden yeni boyut.

## <a name="return-value"></a>Dönüş Değeri

**_expand** yeniden ayrılan bellek bloğuna void bir işaretçi döndürür. **_expand**, **realloc**'ın aksine bir bloğu boyutunu değiştirecek şekilde taşıyamaz. Bu nedenle, bloğu taşımadan genişletmek için yeterli kullanılabilir bellek varsa, **_expand** için *memblock* parametresi, dönüş değeri ile aynıdır.

**_expand** işlemi sırasında bir hata algılandığında **null değeri** döndürür. Örneğin, bir bellek bloğunu daraltmak için **_expand** kullanılırsa, küçük blok yığınında veya geçersiz bir blok İşaretçisinde bozulma algılayabilir ve **null**döndürebilir.

Bloğu taşımadan verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, işlev **null**değerini döndürür. **_expand** , istenen boyuttan daha küçük bir şekilde genişletilmiş bir blok döndürmez. Bir hata oluşursa, **errno** hatanın yapısını gösterir. **Errno**hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Öğenin yeni boyutunu denetlemek için **_msize**kullanın. **Void**dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

**_Expand** işlevi, bloğu yığında bir konuma taşımadan genişletmeyi veya anlaşmayı deneyerek, önceden ayrılmış bir bellek bloğunun boyutunu değiştirir. *Memblock* parametresi bloğunun başlangıcına işaret eder. *Boyut* parametresi, blok için bayt cinsinden yeni boyut verir. Bloğun içeriği, yeni ve eski boyutların daha kısa bir şekilde değiştirilmeden kalır. *memblock* , serbest bırakılmış bir blok olmamalıdır.

> [!NOTE]
> 64-bit platformlarda, yeni boyut geçerli boyuttan daha küçükse, **_expand** bloğu sözleşmeyebilir; Özellikle, blok boyutu 16K 'den küçükse ve bu nedenle düşük parçalanma yığınında ayrılırsa, **_expand** engellemeyi değiştirmez ve *memblock*döndürür.

Uygulama, C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **_expand** , [_expand_dbg](expand-dbg.md)olarak çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

Bu işlev, parametrelerini doğrular. *Memblock* null işaretçisiyse, bu Işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür. *Boyut* **_Heap_maxreq**değerinden büyükse, **errno** , **ENOMEM** olarak ayarlanır ve işlev **null**değerini döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_expand**|\<malloc. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_expand.c

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   char *bufchar;
   printf( "Allocate a 512 element buffer\n" );
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )
      exit( 1 );
   printf( "Allocated %d bytes at %Fp\n",
         _msize( bufchar ), (void *)bufchar );
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )
      printf( "Can't expand" );
   else
      printf( "Expanded block to %d bytes at %Fp\n",
            _msize( bufchar ), (void *)bufchar );
   // Free memory
   free( bufchar );
   exit( 0 );
}
```

```Output
Allocate a 512 element buffer
Allocated 512 bytes at 002C12BC
Expanded block to 1024 bytes at 002C12BC
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
