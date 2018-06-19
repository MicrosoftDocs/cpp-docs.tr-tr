---
title: Sonlandır (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- terminate
dev_langs:
- C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c743439b487f091b760e3747c47b471832e1ff3d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408680"
---
# <a name="terminate-crt"></a>sonlandır (CRT)

Çağrıları [abort](abort.md) veya işlev kullanarak belirtin **set_terminate**.

## <a name="syntax"></a>Sözdizimi

```C
void terminate( void );
```

## <a name="remarks"></a>Açıklamalar

**Sonlandırmak** işlevi ile C++ özel durum işleme kullanılır ve aşağıdaki durumlarda çağrılır:

- Eşleşen bir catch işleyicisi için oluşturulan bir C++ özel durum bulunamıyor.

- Bir özel durum yığını geriye doğru izleme sırasında yıkıcı işlevi tarafından oluşturulur.

- Bir özel durum atma sonra yığını bozuk.

**sonlandırma** çağrıları [abort](abort.md) varsayılan olarak. Kendi sonlandırma işlevi yazma ve arama bu varsayılan ayarı değiştirebilirsiniz **set_terminate** işlevinizi bağımsız değişkeni olarak adı. **sonlandırma** bağımsız değişken olarak verilen son işlevi çağırır **set_terminate**. Daha fazla bilgi için bkz: [işlenmeyen C++ özel durumlarını](../../cpp/unhandled-cpp-exceptions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Sonlandırma**|\<EH.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[beklenmeyen](unexpected-crt.md)<br/>
