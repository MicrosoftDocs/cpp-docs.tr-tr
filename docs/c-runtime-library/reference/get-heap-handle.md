---
description: 'Hakkında daha fazla bilgi edinin: _get_heap_handle'
title: _get_heap_handle
ms.date: 4/2/2020
api_name:
- _get_heap_handle
- _o__get_heap_handle
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_heap_handle
- get_heap_handle
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
ms.openlocfilehash: dacf90e981233c92534a2667ad31462e9bf5992c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205219"
---
# <a name="_get_heap_handle"></a>_get_heap_handle

C çalışma zamanı sistemi tarafından kullanılan yığının tanıtıcısını döndürür.

## <a name="syntax"></a>Syntax

```C
intptr_t _get_heap_handle( void );
```

## <a name="return-value"></a>Dönüş Değeri

C çalışma zamanı sistemi tarafından kullanılan Win32 yığınının tanıtıcısını döndürür.

## <a name="remarks"></a>Açıklamalar

[HeapSetInformation](/windows/win32/api/heapapi/nf-heapapi-heapsetinformation) ÇAĞıRMAK ve CRT yığınında düşük parçalanma yığınını etkinleştirmek istiyorsanız bu işlevi kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_heap_handle**|\<malloc.h>|

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

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
