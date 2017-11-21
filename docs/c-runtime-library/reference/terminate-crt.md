---
title: "Sonlandır (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: terminate
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
f1_keywords: terminate
dev_langs: C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: daf280ba64288a92f7b1deb60a429c56ffc98498
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="terminate-crt"></a>sonlandır (CRT)
Çağrıları `abort` veya işlev kullanarak belirtin `set_terminate`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void terminate( void );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `terminate` İşlevi ile C++ özel durum işleme kullanılır ve aşağıdaki durumlarda çağrılır:  
  
-   Eşleşen bir catch işleyicisi için oluşturulan bir C++ özel durum bulunamıyor.  
  
-   Bir özel durum yığını geriye doğru izleme sırasında yıkıcı işlevi tarafından oluşturulur.  
  
-   Bir özel durum atma sonra yığını bozuk.  
  
 `terminate`çağrıları `abort` varsayılan olarak. Kendi sonlandırma işlevi yazma ve arama bu varsayılan ayarı değiştirebilirsiniz `set_terminate` işlevinizi bağımsız değişkeni olarak adı. `terminate`bağımsız değişken olarak verilen son işlevi çağırır `set_terminate`. Daha fazla bilgi için bkz: [işlenmeyen C++ özel durumlarını](../../cpp/unhandled-cpp-exceptions.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`terminate`|\<EH.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme rutinleri](../../c-runtime-library/exception-handling-routines.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [beklenmeyen](../../c-runtime-library/reference/unexpected-crt.md)