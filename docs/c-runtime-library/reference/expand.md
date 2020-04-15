---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 7f2a789bc5f475411808bc00a4280b7573b67cf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347540"
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
Daha önce ayrılmış bellek bloğu için işaretçi.

*Boyutu*<br/>
Baytlarda yeni boyut.

## <a name="return-value"></a>Dönüş Değeri

**_expand,** yeniden ayrılan bellek bloğuna geçersiz bir işaretçi döndürür. **_expand**, **realloc**aksine, boyutunu değiştirmek için bir blok taşıyamaz. Bu nedenle, taşımadan bloğu genişletmek için yeterli bellek varsa, **_expand** için *memblock* parametresi dönüş değeri ile aynıdır.

**_expand** işlemi sırasında bir hata algılandığında **NULL** döndürür. Örneğin, **_expand** bir bellek bloğunu küçültmek için kullanılırsa, küçük blok yığınındaki bozulmayı veya geçersiz bir blok işaretçisini algılayıp **NULL**döndürebilir.

Taşımadan bloğu verilen boyuta genişletmek için yeterli bellek yoksa, işlev **NULL**döndürür. **_expand,** istenenden daha az bir boyuta genişletilmiş bir bloğu asla döndürmez. Bir hata oluşursa, **errno** hatanın doğasını gösterir. **errno**hakkında daha fazla bilgi için, [bkz. errno, _doserrno, _sys_errlist, ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

İade değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalanması garanti edilen bir depolama alanına işaret ediyor. Öğenin yeni boyutunu denetlemek için **_msize**kullanın. **Void**dışında bir tür için bir işaretçi almak için, dönüş değeri bir tür döküm kullanın.

## <a name="remarks"></a>Açıklamalar

**_expand** işlevi, yığının içinde konumunu hareket ettirmeden bloğu genişletmeye veya daralmaya çalışarak daha önce ayrılmış bir bellek bloğunun boyutunu değiştirir. *Memblock* parametresi bloğun başına işaret eden. *Boyut* parametresi, baytlar halinde bloğun yeni boyutunu verir. Bloğun içeriği, yeni ve eski boyutların daha kısasına kadar değişmez. *memblock* serbest bırakılmış bir blok olmamalıdır.

> [!NOTE]
> 64 bit platformlarda, yeni boyut geçerli boyuttan küçükse **_expand** blok sözleşme olmayabilir; özellikle, blok boyutu 16K'dan küçükse ve bu nedenle Düşük Parçalanma Yığını'nda ayrılmışsa, **_expand** bloğu değişmeden bırakır ve *memblock'u*döndürür.

Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **_expand** [_expand_dbg.](expand-dbg.md) Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için [CRT Hata Ayıklama Yığını'na](/visualstudio/debugger/crt-debug-heap-details)bakın.

Bu işlev parametrelerini doğrular. *Memblock* null işaretçisi ise, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür. *Boyut* **_HEAP_MAXREQ'den**büyükse, **errno** **ENOMEM** olarak ayarlanır ve işlev **NULL**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
[Ücret -siz](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
