---
title: _get_heap_handle
ms.date: 11/04/2016
apiname:
- _get_heap_handle
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
- _get_heap_handle
- get_heap_handle
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
ms.openlocfilehash: 82ea108a41bec1d0276e2c952b3f509f36bab8ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480034"
---
# <a name="getheaphandle"></a>_get_heap_handle

C çalışma zamanı sistemi tarafından kullanılan yığın tanıtıcısını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _get_heap_handle( void );
```

## <a name="return-value"></a>Dönüş Değeri

C çalışma zamanı sistemi tarafından kullanılan Win32 yığınının tanıtıcısını döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak istediğinizde kullanın [Heapsetınformation](/windows/desktop/api/heapapi/nf-heapapi-heapsetinformation) ve ve CRT yığınında düşük parçalanma yığınını etkinleştirmek.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_heap_handle**|\<malloc.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="sample"></a>Örnek

```cpp
// crt_get_heap_handle.cpp
// compile with: /MT
#include <windows.h>
#include <malloc.h>
#include <stdio.h>

int main(void)
{
    intptr_t hCrtHeap = _get_heap_handle();
    ULONG ulEnableLFH = 2;
    if (HeapSetInformation((PVOID)hCrtHeap,
                           HeapCompatibilityInformation,
                           &ulEnableLFH, sizeof(ulEnableLFH)))
        puts("Enabling Low Fragmentation Heap succeeded");
    else
        puts("Enabling Low Fragmentation Heap failed");
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
