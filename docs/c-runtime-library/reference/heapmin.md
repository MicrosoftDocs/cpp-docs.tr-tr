---
title: _heapmin
ms.date: 11/04/2016
apiname:
- _heapmin
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
- _heapmin
- heapmin
helpviewer_keywords:
- heap memory
- minimizing heaps
- memory, releasing
- heaps, releasing unused memory
- _heapmin function
- heapmin function
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
ms.openlocfilehash: 130986894d1e2a68415e6ab9218641eff484ffd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157231"
---
# <a name="heapmin"></a>_heapmin

İşletim sistemi için kullanılmayan yığın belleği serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
int _heapmin( void );
```

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_heapmin** ; 0 döndürür. Aksi halde, işlev -1 döndürür ve ayarlar **errno** için **ENOSYS**.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Heapmin** işlevi, işletim sistemi için kullanılmayan yığın bellek serbest bırakarak yığın azaltır. İşletim sistemi desteklemiyorsa **_heapmin**(örneğin, Windows 98), işlev -1 döndürür ve ayarlar **errno** için **ENOSYS**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_heapmin**|\<malloc.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
[malloc](malloc.md)<br/>
