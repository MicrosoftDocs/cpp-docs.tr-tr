---
description: 'Hakkında daha fazla bilgi edinin: _expand'
title: _expand
ms.date: 4/2/2020
api_name:
- _expand
- _o__expand
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 31558bb67266430cc028e37a1e23dff2fa411356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235975"
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

**_expand** yeniden ayrılan bellek bloğuna void bir işaretçi döndürür. **_expand**, **realloc**'ın aksine bir bloğu boyutunu değiştirecek şekilde taşıyamaz. Bu nedenle, bloğu taşımadan genişletmek için yeterli kullanılabilir bellek varsa, **_expand** *memblock* parametresi dönüş değeri ile aynıdır.

**_expand** işlemi sırasında bir hata algılandığında **null değeri** döndürür. Örneğin, bir bellek bloğunu daraltmak için **_expand** kullanılırsa, küçük blok yığınında veya geçersiz bir blok İşaretçisinde bozulma algılayabilir ve **null** döndürebilir.

Bloğu taşımadan verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, işlev **null** değerini döndürür. **_expand** , istenen boyuttan daha küçük bir biçimde genişletilmiş bir blok döndürmez. Bir hata oluşursa, **errno** hatanın yapısını gösterir. **Errno** hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Öğenin yeni boyutunu denetlemek için **_msize** kullanın. Dışında bir türe işaretçi almak için **`void`** , dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

**_Expand** işlevi, bloğu yığın içinde taşımadan genişletmeyi veya anlaşmayı deneyerek, önceden ayrılmış bir bellek bloğunun boyutunu değiştirir. *Memblock* parametresi bloğunun başlangıcına işaret eder. *Boyut* parametresi, blok için bayt cinsinden yeni boyut verir. Bloğun içeriği, yeni ve eski boyutların daha kısa bir şekilde değiştirilmeden kalır. *memblock* , serbest bırakılmış bir blok olmamalıdır.

> [!NOTE]
> 64-bit platformlarda, yeni boyut geçerli boyuttan daha küçükse **_expand** bloğu sözleşmeyebilir; Özellikle, blok boyutu 16K 'den küçükse ve bu nedenle düşük parçalanma yığınında ayrılırsa, **_expand** engellemeyi değiştirmez ve *memblock* döndürür.

Uygulama, C çalışma zamanı kitaplıklarının bir hata ayıklama sürümü ile bağlantılı olduğunda **_expand** [_expand_dbg](expand-dbg.md)çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

Bu işlev, parametrelerini doğrular. *Memblock* null işaretçisiyse, bu Işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null** değerini döndürür. *Boyut* **_HEAP_MAXREQ** büyükse, **errno** **ENOMEM** olarak ayarlanır ve işlev **null** değerini döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

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

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Süz](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
