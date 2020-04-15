---
title: sonlandır (CRT)
ms.date: 4/2/2020
api_name:
- terminate
- _o_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- terminate
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
ms.openlocfilehash: 1aa95daeab424c933f10060fb4f87cb317aa188c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362539"
---
# <a name="terminate-crt"></a>sonlandır (CRT)

Set_terminate [abort](abort.md) **kullanarak**iptal veya bir işlev çağırır.

## <a name="syntax"></a>Sözdizimi

```C
void terminate( void );
```

## <a name="remarks"></a>Açıklamalar

**Sonlandırma** işlevi C++ özel durum işleme ile kullanılır ve aşağıdaki durumlarda çağrılır:

- Atılan c++ özel durumu için eşleşen bir catch işleyicisi bulunamıyor.

- Yığın gevşemesırasında bir özel durum yıkıcı işlev tarafından atılır.

- Yığın bir özel durum attıktan sonra bozulur.

çağrıları varsayılan olarak [iptal](abort.md) **eder.** Kendi sonlandırma işlevinizi yazarak ve işlevinizin adı ile **set_terminate** çağırarak bu varsayılanı değiştirebilirsiniz. **set_terminate** için bir argüman olarak **set_terminate**verilen son işlevi çağırır . Daha fazla bilgi için [bkz.](../../cpp/unhandled-cpp-exceptions.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Sonlandır**|\<eh.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```cpp
// crt_terminate.cpp
// compile with: /EHsc
#include <eh.h>
#include <process.h>
#include <iostream>
using namespace std;

void term_func();

int main()
{
    int i = 10, j = 0, result;
    set_terminate( term_func );
    try
    {
        if( j == 0 )
            throw "Divide by zero!";
        else
            result = i/j;
    }
    catch( int )
    {
        cout << "Caught some integer exception.\n";
    }
    cout << "This should never print.\n";
}

void term_func()
{
    cout << "term_func() was called by terminate().\n";

    // ... cleanup tasks performed here

    // If this function does not exit, abort is called.

    exit(-1);
}
```

```Output
term_func() was called by terminate().
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[Iptal](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Beklen -medik](unexpected-crt.md)<br/>
