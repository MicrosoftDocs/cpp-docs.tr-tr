---
title: _lock_file
ms.date: 11/04/2016
api_name:
- _lock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _lock_file
- lock_file
helpviewer_keywords:
- file locking [C++]
- _lock_file function
- lock_file function
ms.assetid: 75c7e0e6-efff-4747-b6ed-9bcf2b0894c3
ms.openlocfilehash: 43030030d1674cfba24c1300487f576b7a2085ea
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953312"
---
# <a name="_lock_file"></a>_lock_file

**Dosya** nesnesine eşzamanlı olarak erişen iş parçacıklarının tutarlılığını sağlamak Için bir **Dosya** nesnesini kilitler.

## <a name="syntax"></a>Sözdizimi

```C
void _lock_file( FILE* file );
```

### <a name="parameters"></a>Parametreler

*dosyasýný*<br/>
Dosya tanıtıcısı.

## <a name="remarks"></a>Açıklamalar

**_Lock_fıle** işlevi *Dosya*tarafından belirtilen **Dosya** nesnesini kilitler. Temel alınan dosya **_lock_tarafından**kilitlenmedi. Dosyadaki kilidi serbest bırakmak için [_unlock_al](unlock-file.md) kullanın. **_Lock_thread** ve **_unlock_bu** çağrıları bir iş parçacığında eşleştirilmelidir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lock_file**|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_lock_file.c
// This example creates multiple threads that write to standard output
// concurrently, first with _file_lock, then without.

#include <stdio.h>
#include <process.h>// _beginthread
#include <windows.h>// HANDLE

void Task_locked( void* str )
{
    for( int i=0; i<1000; ++i )
    {
        _lock_file( stdout );
        for( char* cp = (char*)str; *cp; ++cp )
        {
            _fputc_nolock( *cp, stdout );
        }
        _unlock_file( stdout );
    }
}

void Task_unlocked( void* str )
{
    for( int i=0; i<1000; ++i )
    {
        for( char* cp = (char*)str; *cp; ++cp )
        {
            fputc( *cp, stdout );
        }
    }
}

int main()
{
    HANDLE h[3];
    h[0] = (HANDLE)_beginthread( &Task_locked, 0, "First\n" );
    h[1] = (HANDLE)_beginthread( &Task_locked, 0, "Second\n" );
    h[2] = (HANDLE)_beginthread( &Task_locked, 0, "Third\n" );

    WaitForMultipleObjects( 3, h, true, INFINITE );

    h[0] = (HANDLE)_beginthread( &Task_unlocked, 0, "First\n" );
    h[1] = (HANDLE)_beginthread( &Task_unlocked, 0, "Second\n" );
    h[2] = (HANDLE)_beginthread( &Task_unlocked, 0, "Third\n" );

    WaitForMultipleObjects( 3, h, true, INFINITE );
}
```

```Output
...
First
Second
First
Second
Third
Second
Third
Second
...
FSiercsotn
dF
iSrescto
nFdi
rSsetc
oFnidr
sSte
cFoinrds
tS
eFciornsdt
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlock_file](unlock-file.md)<br/>
