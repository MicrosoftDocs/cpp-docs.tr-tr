---
title: calloc
ms.date: 11/04/2016
apiname:
- calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: 59aa535136cf32ea5dd68b8917ec969eee41e2ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347736"
---
# <a name="calloc"></a>calloc

Öğeleri 0 olarak başlatılmış bir dizide bir bellek ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void *calloc(
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*Sayı*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her öğenin bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**calloc** ayrılan alana bir işaretçi döndürür. Dönüş değeri tarafından işaret edilen depolama alanı nesnesinin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti edilir. Dışında bir türe işaretçi almaya **void**, bir tür ataması dönüş değerini kullanın.

## <a name="remarks"></a>Açıklamalar

**Calloc** işlevi bir dizi için depolama alanı ayırır *numarası* öğeleri, her uzunlukta *boyutu* bayt. Her öğe 0 olarak başlatılır.

**calloc** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya bellek miktarını aşıyor istenirse **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**calloc** çağrıları **malloc** kullanılacak C++ [_set_new_mode](set-new-mode.md) yeni işleyici modu ayarlamak için işlevi. Yeni işleyici modunu gösterir mi, hata durumunda, **malloc** tarafından belirlenen yeni işleyici rutinini çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** bellek dağıtma hatasında yeni işleyici rutinini çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **calloc** bellek ayırmak başarısız **malloc** aynı yeni işleyici rutinini çağırır biçimi **yeni** işleci yok aynı nedenden dolayı başarısız olduğunda. Varsayılan geçersiz kılmak için çağırın

```C
_set_new_mode(1);
```

programınızda ya NEWMODE bağlantıyla erkenden. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulamayı hata ayıklama sürümü C çalışma zamanı kitaplıkları ile ilişkilendirildiğinde **calloc** çözümler [_calloc_dbg](calloc-dbg.md). Yığının hata ayıklama işlemi sırasında nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığın](/visualstudio/debugger/crt-debug-heap-details).

**calloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevin genel değişkenleri garanti edilir ve döndürülen işaretçiye diğer adı değil. Daha fazla bilgi için [noalias](../../cpp/noalias.md) ve [kısıtlama](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**calloc**|\<stdlib.h > ve \<malloc.h >|

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
