---
title: sonlandır (CRT)
ms.date: 11/04/2016
api_name:
- terminate
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
ms.openlocfilehash: b76ce42817fa1a6b79ef32965fcfa550a508e88d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946193"
---
# <a name="terminate-crt"></a>sonlandır (CRT)

**Set_terminate**kullanarak belirttiğiniz [iptali](abort.md) veya işlevi çağırır.

## <a name="syntax"></a>Sözdizimi

```C
void terminate( void );
```

## <a name="remarks"></a>Açıklamalar

**Terminate** işlevi C++ özel durum işlemeyle kullanılır ve aşağıdaki durumlarda çağırılır:

- Oluşan C++ bir özel durum için eşleşen bir catch işleyicisi bulunamıyor.

- Yığın geriye doğru izleme sırasında yıkıcı işlevi tarafından bir özel durum oluşturulur.

- Özel durum oluşturulduktan sonra yığın bozuk.

Varsayılan olarak [iptal](abort.md) çağrıları **Sonlandır** . Kendi sonlandırma işlevinizi yazarak ve bağımsız değişkeni olarak işlevinizin adını **set_terminate** çağırarak bu varsayılan değeri değiştirebilirsiniz. **Sonlandır** , **set_terminate**için bağımsız değişken olarak verilen son işlevi çağırır. Daha fazla bilgi için bkz [. C++ işlenmemiş özel durumlar](../../cpp/unhandled-cpp-exceptions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sonlandırmayı**|\<Eh. h >|

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

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[bek](unexpected-crt.md)<br/>
