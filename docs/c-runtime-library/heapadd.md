---
title: _heapadd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _heapadd
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- heapadd
- _heapadd
dev_langs:
- C++
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce067dc000a681dfd1bfa9d3376131f86f5a73e1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086856"
---
# <a name="heapadd"></a>_heapadd

Bellek yığına ekler.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
int _heapadd(
   void *memblock,
   size_t size
);
```

#### <a name="parameters"></a>Parametreler

*memblock*<br/>
Yığın bellek işaretçisi.

*Boyutu*<br/>
Eklenecek bayt cinsinden bellek boyutu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `_heapadd` ; 0 döndürür. Aksi halde, işlev -1 döndürür ve ayarlar `errno` için `ENOSYS`.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Visual C++ sürüm 4. 0 ile başlayarak, yığın temelindeki, yeni hata ayıklama özellikleri desteklemek için C çalışma zamanı kitaplıklarına taşındı. Sonuç olarak, `_heapadd` artık Win32 API tabanlı herhangi bir platformda desteklenmiyor.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|`_heapadd`|\<malloc.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md) giriş.

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Ayırma](../c-runtime-library/memory-allocation.md)<br/>
[free](../c-runtime-library/reference/free.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[malloc](../c-runtime-library/reference/malloc.md)<br/>
[realloc](../c-runtime-library/reference/realloc.md)