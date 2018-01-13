---
title: _configthreadlocale | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _configthreadlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _configthreadlocale
- configthreadlocale
dev_langs: C++
helpviewer_keywords:
- configthreadlocale function
- locales, per-thread
- _configthreadlocale function
- per-thread locale
- thread locale
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aacd7b82525ca1b74c3d7a7ab7f8e09497e491ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="configthreadlocale"></a>_configthreadlocale
İş parçacığı başına yerel ayar seçenekleri yapılandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `type`  
 Ayarlama seçeneği. Aşağıdaki tabloda listelenen seçeneklerden biri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceki iş parçacığı başına yerel ayar durumu (`_DISABLE_PER_THREAD_LOCALE` veya `_ENABLE_PER_THREAD_LOCALE`), veya -1 hata durumunda.  
  
## <a name="remarks"></a>Açıklamalar  
 `_configurethreadlocale` İşlevi iş parçacığına özgü yerel kullanımını denetlemek için kullanılır. İş parçacığı başına yerel ayar durumunu belirlemek için aşağıdaki seçeneklerden birini kullanın:  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 Geçerli iş parçacığı kullanımı iş parçacığına özgü yerel ayarı olun. Sonraki çağrılar `setlocale` yalnızca iş parçacığının kendi yerel ayar bu iş parçacığında etkiler.  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 Genel yerel kullanın geçerli iş parçacığının olun. Sonraki çağrılar `setlocale` genel yerel kullanarak başka bir iş parçacığı bu iş parçacığında etkiler.  
  
 `0`  
 Bu belirli iş parçacığı için geçerli ayarları alır.  
  
 Bu işlevler davranışını etkileyen `setlocale`, `_tsetlocale`, `_wsetlocale`, ve `_setmbcp`. İş parçacığı başına yerel ayar devre dışı, sonraki çağrı olduğunda `setlocale` veya `_wsetlocale` genel yerel kullanan tüm iş parçacığı yerel değiştirir. İş parçacığı başına yerel ayar etkinleştirildiğinde, `setlocale` veya `_wsetlocale` yalnızca geçerli iş parçacığının yerel etkiler.  
  
 Kullanırsanız `_configurethreadlocale` bir iş parçacığı başına yerel ayar etkinleştirmek için arama öneririz `setlocale` veya `_wsetlocale` hemen sonra bu iş parçacığında tercih edilen yerel ayarlanacak.  
  
 Varsa `type` değerlerden biri değil tabloda listelenen, bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_configthreadlocale`|\<Locale.h >|  
  
## <a name="example"></a>Örnek  
  
```cpp  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using two independent threads.  
//  
// Compile by using: cl /EHsc /W4 crt_configthreadlocale.cpp 
  
#include <locale.h>  
#include <mbctype.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date and time in the current  
// locale's format.  
int get_time(unsigned char* str)  
{  
    __time64_t  ltime;  
    struct tm   thetime;  
  
    // Retieve the time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // using %#x is the long date representation,  
    // appropriate to the current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm*)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to German  
// and prints the time.  
unsigned __stdcall SecondThreadFunc( void* /*pArguments*/ )  
{  
    unsigned char str[BUFF_SIZE];  
  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  

    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI);  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "German"));  
  
    // Retrieve the time string from the helper function  
    if (get_time(str) == 0)  
    {  
        printf("The time in German locale is: '%s'\n", str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread spawns a second thread (above) and then  
// sets the locale to English and prints the time.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Enable per-thread locale causes all subsequent locale   
    // setting changes in this thread to only affect this thread.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Retrieve the time string from the helper function  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "English"));  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      NULL, 0, &threadID );  
  
    if (get_time(str) == 0)  
    {  
        // Retrieve the time string from the helper function  
        printf("The time in English locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
} 
```  
  
```Output  
The thread locale is now set to English_United States.1252.  
The time in English locale is: 'Wednesday, May 12, 2004'  
  
The thread locale is now set to German_Germany.1252.  
The time in German locale is: 'Mittwoch, 12. Mai 2004'  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar](../../parallel/multithreading-and-locales.md)  
