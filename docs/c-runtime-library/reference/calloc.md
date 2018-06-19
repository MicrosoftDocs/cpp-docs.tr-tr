---
title: calloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6986e1caec25cd544919039f690544af429524af
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394892"
---
# <a name="calloc"></a>calloc

0 olarak başlatılan öğelerle bir dizi bellek ayırır.

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

**calloc** ayrılan alanı için bir işaretçi döndürür. Dönüş değeri tarafından işaret depolama alanı nesnesinin herhangi bir türde bir depolama için uygun hizalanacak garanti edilmez. Bir işaretçi bir türe dışında almak için **void**, dönüş değerini cast türünü kullanın.

## <a name="remarks"></a>Açıklamalar

**Calloc** işlevi bir dizi için depolama alanı ayırır *numarası* öğeleri, her uzunlukta *boyutu* bayt sayısı. Her öğe 0 olarak başlatılır.

**calloc** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya bellek miktarını aşıyor istediyseniz **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**calloc** çağrıları **malloc** C++ kullanılacak [_set_new_mode](set-new-mode.md) yeni işleyici modu ayarlamak için işlevi. Yeni işleyici modunu gösterir, hatasında kullanılıp **malloc** belirlediği yeni işleyici yordamı çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **malloc** yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **calloc** bellek ayırmak başarısız **malloc** yeni işleyici yordamını aynı çağırıyor biçimi **yeni** işleci mu aynı nedenden dolayı başarısız olduğunda. Varsayılan değer geçersiz kılmak için arama

```C
_set_new_mode(1);
```

program veya NEWMODE bağlantısıyla erken. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).

Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında **calloc** çözümler [_calloc_dbg](calloc-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**calloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlev genel değişkenler değiştirmemeniz garanti ve işaretçi döndürdü diğer adı değil anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**calloc**|\<stdlib.h > ve \<malloc.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
