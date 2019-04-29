---
title: _expand
ms.date: 11/04/2016
apiname:
- _expand
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: c1606bedbb1264bddb7674c829fe456f506d6584
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335210"
---
# <a name="expand"></a>_expand

Bir bellek bloğunu boyutunu değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void *_expand(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Daha önce ayrılmış bellek bloğuna işaretçi.

*Boyutu*<br/>
Yeni boyutu bayt cinsinden.

## <a name="return-value"></a>Dönüş Değeri

**_tümünü Genişlet** bırakılan bellek bloğuna void bir işaretçi döndürür. **_tümünü Genişlet**aksine **realloc**, bir blok boyutunu değiştirmek için taşınamıyor. Bu nedenle, blok, taşımadan genişletmek için kullanılabilir yeterli bellek yoksa *memblock* parametresi **_expand** dönüş değeri ile aynıdır.

**_tümünü Genişlet** döndürür **NULL** ne zaman bir hata algılandığında, işlemi sırasında. Örneğin, varsa **_expand** olan bir bellek bloğunu daraltmak için kullanılan, küçük blok yığın veya geçersiz blok işaretçi Bozulması algılamasını ve dönüş **NULL**.

Yetersiz bellek bloğu için verilen boyuta taşımadan genişletmek için kullanılabilir, yok, işlev döndürür **NULL**. **_tümünü Genişlet** hiçbir zaman bir boyut için genişletilmiş değerinden istenen bir blok döndürür. Bir hata oluşursa **errno** hatanın yapısını gösterir. Hakkında daha fazla bilgi için **errno**, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Yeni öğenin boyutunu denetlemek için kullanmak **_msize**. Dışında bir türe işaretçi almaya **void**, bir tür ataması dönüş değerini kullanın.

## <a name="remarks"></a>Açıklamalar

**_Expand** işlev genişletin veya blok yığın konumunda taşımadan sözleşme çalışılırken tarafından önceden ayrılan bellek blok boyutu değiştirir. *Memblock* parametresi bloğunun başlangıcına işaret eder. *Boyutu* parametre yeni blok boyutunu bayt cinsinden verir. Blok içeriklerini kadar kısa yeni ve eski boyutlarının değiştirilmez. *memblock* serbest bırakılmış bir blok olmamalıdır.

> [!NOTE]
> 64-bit platformlarda **_expand** oluştuysa blok boyutu 16 K'küçüktür ve bu nedenle düşük parçalanma yığında ayrılan yeni boyut; özellikle, geçerli boyuttan daha az ise, bloğun sözleşme değil **_tümünü Genişlet**  değişmeden blok ayrılıp döndüğünde *memblock*.

Uygulamayı hata ayıklama sürümü C çalışma zamanı kitaplıkları ile ilişkilendirildiğinde **_expand** çözümler [_expand_dbg](expand-dbg.md). Yığının hata ayıklama işlemi sırasında nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığın](/visualstudio/debugger/crt-debug-heap-details).

Bu işlev, parametrelerini doğrular. Varsa *memblock* null bir işaretçiyse, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**. Varsa *boyutu* büyüktür **_HEAP_MAXREQ**, **errno** ayarlanır **ENOMEM** ve işlev döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_expand**|\<malloc.h >|

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
