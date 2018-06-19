---
title: siteyi g_enişlet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f709df131ded856881dc171c2e1549d3d5d378e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402357"
---
# <a name="expand"></a>_expand

Bellek blok boyutunu değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void *_expand(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Önceden ayrılmış bellek bloğu işaretçi.

*Boyutu*<br/>
Yeni boyutunu bayt cinsinden.

## <a name="return-value"></a>Dönüş Değeri

**siteyi g_enişlet** void işaretçi ayrılabilecek bellek bloğuna döndürür. **siteyi g_enişlet**öğesinden farklı olarak **realloc**, bir blok boyutunu değiştirmek için taşıyamazsınız. Bu nedenle, blok, taşımadan genişletmek kullanılabilir yeterli bellek varsa *memblock* parametresi **siteyi g_enişlet** dönüş değeri ile aynıdır.

**siteyi g_enişlet** döndürür **NULL** ne zaman bir hata algılandığında, işlem sırasında. Örneğin, varsa **siteyi g_enişlet** olan bir bellek bloğu daraltmak için kullanılan, küçük blok yığın veya geçersiz blok işaretçi Bozulması algılamak ve dönüş **NULL**.

Olup olmadığını taşımadan blok verilen boyuta genişletmek kullanılabilir bellek yetersiz, işlevi döndürür **NULL**. **siteyi g_enişlet** hiçbir zaman bir blok genişletilmiş bir boyut değerinden istenen döndürür. Bir hata oluşursa **errno** hatanın yapısını gösterir. Hakkında daha fazla bilgi için **errno**, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Yeni öğe boyutunu denetlemek için kullanın **_msize**. Bir işaretçi bir türe dışında almak için **void**, dönüş değerini cast türünü kullanın.

## <a name="remarks"></a>Açıklamalar

**Siteyi g_enişlet** işlev genişletin veya yığın konumunda taşımadan blok sözleşme çalışılırken tarafından önceden ayrılmış bellek bloğu boyutu değiştirir. *Memblock* parametresi blok başlangıcına işaret eder. *Boyutu* parametresi yeni blok boyutunu bayt cinsinden verir. Blok içeriğini kadar kısa yeni ve eski boyutlarının değiştirilmemiştir. *memblock* serbest bırakılmış bir blok olmamalıdır.

> [!NOTE]
> 64 bit platformlarda **siteyi g_enişlet** blok boyutu 16 K'dan az ise ve bu nedenle Düşük Parçalanma Yığın ayrılan yeni boyutu geçerli boyutundan; özellikle, düşükse blok sözleşme değil **siteyi g_enişlet**  değişmeden blok ayrılıp döndüğünde *memblock*.

Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında **siteyi g_enişlet** çözümler [_expand_dbg](expand-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

Bu işlev parametrelerini doğrular. Varsa *memblock* null işaretçi açıklandığı gibi bir geçersiz parametre işleyicisi bu işlevi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**. Varsa *boyutu* değerinden daha büyük **_HEAP_MAXREQ**, **errno** ayarlanır **ENOMEM** ve işlevi döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_expand**|\<malloc.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
