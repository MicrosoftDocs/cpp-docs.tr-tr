---
title: _get_heap_handle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 238fab4ec2d900c8183c018f3cb03fe6dc1fb2f5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202240"
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
