---
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
ms.openlocfilehash: c5eeb66ff0e6fb05063ec395e12cd97106ad724d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351325"
---
# <a name="_heapadd"></a>_heapadd

Yığına bellek ekler.

> [!IMPORTANT]
> Bu işlev geçersizdir. Visual Studio 2015'ten itibaren CRT'de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
int _heapadd(
   void *memblock,
   size_t size
);
```

#### <a name="parameters"></a>Parametreler

*memblock*<br/>
Yığın belleği için işaretçi.

*Boyutu*<br/>
Eklenecek bellek boyutu, baytlar halinde.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `_heapadd` 0 döndürür; aksi takdirde, işlev -1 `errno` `ENOSYS`döndürür ve ayarlar.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

Visual C++ sürüm 4.0 ile başlayarak, altta yatan yığın yapısı, yeni hata ayıklama özelliklerini desteklemek için C çalışma zamanı kitaplıklarına taşındı. Sonuç olarak, `_heapadd` artık Win32 API dayalı herhangi bir platformda desteklenir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|`_heapadd`|\<malloc.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Giriş'te [Uyumluluk'a](../c-runtime-library/compatibility.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../c-runtime-library/memory-allocation.md)<br/>
[Ücret -siz](../c-runtime-library/reference/free.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[malloc](../c-runtime-library/reference/malloc.md)<br/>
[realloc](../c-runtime-library/reference/realloc.md)
