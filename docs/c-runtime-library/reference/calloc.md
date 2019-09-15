---
title: calloc
ms.date: 11/04/2016
api_name:
- calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: ba498b35106f9ff1636bb1bc0764088a434b5b01
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939338"
---
# <a name="calloc"></a>calloc

Başlatılmış öğeleri 0 olarak, bellekte bir diziyi ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void *calloc(
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*sayısından*<br/>
Öğe sayısı.

*boyutla*<br/>
Her öğenin bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**calloc** , ayrılan alana bir işaretçi döndürür. Dönüş değeri tarafından işaret edilen depolama alanı, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garanti edilir. **Void**dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

**Calloc** işlevi, her bir uzunluk *boyutu* bayt olan *sayı* öğeleri dizisi için depolama alanı ayırır. Her öğe 0 olarak başlatılır.

**calloc** , bir bellek ayırma başarısız olursa veya istenen bellek miktarı **_Heap_maxreq**değerini aşarsa, **errno** değeri **ENOMEM** olarak ayarlanır. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**calloc** , C++ yeni işleyici modunu ayarlamak için [_set_new_mode](set-new-mode.md) işlevini kullanmak üzere malloc çağırır. Yeni işleyici modu, hata durumunda **malloc** 'in, [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **malloc** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **calloc** bellek ayıramadığında, **malloc** yeni işleyici yordamını aynı nedenden dolayı başarısız olduğunda **Yeni** işlecin yaptığı şekilde çağırır. Varsayılanı geçersiz kılmak için şunu çağırın

```C
_set_new_mode(1);
```

programınızı erken veya NEWMODE ile bağlayın. OBJ (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama, C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **calloc** [_calloc_dbg](calloc-dbg.md)olarak çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**calloc** , ve `__declspec(noalias)` işlevinin `__declspec(restrict)`genel değişkenleri değiştirmeyeceği garantisi olduğu ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir ve olarak işaretlenir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**calloc**|\<Stdlib. h > ve \<malloc. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
