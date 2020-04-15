---
title: calloc
description: C çalışma zamanı kitaplık işlevi calloc sıfır-initialized bellek ayırır.
ms.date: 4/2/2020
api_name:
- calloc
- _o_calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: fb4f7d6dc059023d34cb0b811edf5dfb48cb7a34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333645"
---
# <a name="calloc"></a>calloc

0'a başlatım öğeleri olan bir diziyi bellekolarak ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void *calloc(
   size_t number,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*number*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her öğenin baytuzunluk.

## <a name="return-value"></a>Dönüş Değeri

**calloc** ayrılan alana bir işaretçi döndürür. İade değerine işaret edilen depolama alanının, her tür nesnenin depolanması için uygun şekilde hizalanması garanti edilir. **Void**dışında bir tür için bir işaretçi almak için, dönüş değeri bir tür döküm kullanın.

## <a name="remarks"></a>Açıklamalar

**Calloc** işlevi, her biri uzunluk *boyutu* baytları olan bir dizi *sayı* öğesi için depolama alanı ayırır. Her öğe 0'a başharfle verilir.

**calloc,** bellek ayırması başarısız olursa veya istenen bellek miktarı **_HEAP_MAXREQ**aşıyorsa **errno'yu** **ENOMEM** olarak ayarlar. Bu ve diğer hata kodları hakkında bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Microsoft uygulamasında, *sayı* veya *boyut* sıfırsa, **calloc** bir işaretçiyi sıfır boyutuolmayan ayrılmış bir blota döndürür. Döndürülen işaretçi aracılığıyla okuma veya yazma girişimi tanımlanmamış davranışlara yol açar.

**calloc,** *yeni işleyici modunu*ayarlamak için C++ [_set_new_mode](set-new-mode.md) işlevini kullanır. Yeni işleyici modu, hata üzerine **calloc'un** yeni işleyici yordamını [_set_new_handler](set-new-handler.md)olarak ayarlayıp çağırmayacağını gösterir. Varsayılan olarak, **calloc** bellek tahsis başarısız yeni işleyici yordamı aramaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **calloc** bellek ayırmadığında, yeni işleyici yordamını aynı nedenle başarısız olduğunda **yeni** işlecinin yaptığı gibi çağırır. Varsayılanı geçersiz kılmak için,

```C
_set_new_mode(1);
```

programınızın başlarında veya NEWMODE ile *bağlantı. OBJ* (bkz. [Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **calloc** [_calloc_dbg.](calloc-dbg.md) Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için [CRT Hata Ayıklama Yığını'na](/visualstudio/debugger/crt-debug-heap-details)bakın.

**calloc** `__declspec(noalias)` işaretlenir `__declspec(restrict)`ve işlevin genel değişkenleri değiştirmemesi ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md) bakın ve [kısıtlayın.](../../cpp/restrict.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**calloc**|\<stdlib.h> \<ve malloc.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_calloc.c
// This program uses calloc to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>

int main( void )
{
   long *buffer;

   buffer = (long *)calloc( 40, sizeof( long ) );
   if( buffer != NULL )
      printf( "Allocated 40 long integers\n" );
   else
      printf( "Can't allocate memory\n" );
   free( buffer );
}
```

```Output
Allocated 40 long integers
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[Ücret -siz](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
