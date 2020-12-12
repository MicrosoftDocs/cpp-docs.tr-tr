---
description: 'Hakkında daha fazla bilgi edinin: _heapadd'
title: _heapadd
ms.date: 11/04/2016
api_name:
- _heapadd
api_location:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- heapadd
- _heapadd
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
ms.openlocfilehash: 0270f84de2c543e37f089418b833011c2d83230d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120688"
---
# <a name="_heapadd"></a>_heapadd

Yığına bellek ekler.

> [!IMPORTANT]
> Bu işlev artık kullanılmıyor. Visual Studio 2015 ' den başlayarak CRT ' de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
int _heapadd(
   void *memblock,
   size_t size
);
```

#### <a name="parameters"></a>Parametreler

*memblock*<br/>
Yığın belleği işaretçisi.

*boyutla*<br/>
Eklenecek bellek boyutu (bayt cinsinden).

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `_heapadd` 0 döndürür; Aksi takdirde, işlev-1 döndürür ve öğesini `errno` olarak ayarlar `ENOSYS` .

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Visual C++ sürüm 4,0 ' den başlayarak, temeldeki yığın yapısı yeni hata ayıklama özelliklerini desteklemek için C çalışma zamanı kitaplıklarına taşınmıştır. Sonuç olarak, `_heapadd` Win32 API dayalı hiçbir platformda artık desteklenmez.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|`_heapadd`|\<malloc.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. karşılama 'da [Uyumluluk](../c-runtime-library/compatibility.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../c-runtime-library/memory-allocation.md)<br/>
[Süz](../c-runtime-library/reference/free.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[malloc](../c-runtime-library/reference/malloc.md)<br/>
[realloc](../c-runtime-library/reference/realloc.md)
