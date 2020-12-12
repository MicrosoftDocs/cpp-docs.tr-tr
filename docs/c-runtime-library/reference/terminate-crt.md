---
description: 'Daha fazla bilgi edinin: sonlandır (CRT)'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 8370c1f1aff54b5286ad4472b053275e3468a8d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326174"
---
# <a name="terminate-crt"></a>sonlandır (CRT)

**Set_terminate** kullanarak belirlediğiniz [iptali](abort.md) veya işlevi çağırır.

## <a name="syntax"></a>Syntax

```C
void terminate( void );
```

## <a name="remarks"></a>Açıklamalar

**Terminate** işlevi C++ özel durum işlemesi ile kullanılır ve aşağıdaki durumlarda çağırılır:

- Oluşan bir C++ özel durumu için eşleşen bir catch işleyicisi bulunamıyor.

- Yığın geriye doğru izleme sırasında yıkıcı işlevi tarafından bir özel durum oluşturulur.

- Özel durum oluşturulduktan sonra yığın bozuk.

Varsayılan olarak [iptal](abort.md) çağrıları **Sonlandır** . Kendi sonlandırma işlevinizi yazarak ve bağımsız değişkeni olarak işlevinizin adını **set_terminate** çağırarak, bu varsayılanı değiştirebilirsiniz. **sonlandır** **set_terminate** bir bağımsız değişken olarak verilen son işlevi çağırır. Daha fazla bilgi için bkz. [Işlenmemiş C++ özel durumları](../../cpp/unhandled-cpp-exceptions.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sonlandırmayı**|\<eh.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Özel durum Işleme yordamları](../../c-runtime-library/exception-handling-routines.md)<br/>
[durdur](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[bek](unexpected-crt.md)<br/>
