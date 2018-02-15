---
title: _cwait | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _cwait
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cwait
dev_langs:
- C++
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 483b98f005a77ff41d2a319a9d07ccc88ad32721
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cwait"></a>_cwait
Başka bir işlem sonlanana kadar bekler.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
intptr_t _cwait(   
   int *termstat,  
   intptr_t procHandle,  
   int action   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `termstat`  
 Belirtilen işlem Sonuç kodu depolanacağı bir arabellek işaretçisine ya da NULL.  
  
 `procHandle`  
 İşlemin beklemesi tanıtıcısını (diğer bir deyişle, önce sonlandırmak için olan işlem `_cwait` dönebilirsiniz).  
  
 `action`  
 NULL: Windows işletim sistemi uygulamaları tarafından göz ardı; diğer uygulamalar için: gerçekleştirmek için eylem kodu `procHandle`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen işlem başarıyla tamamlandığında, belirtilen işlem işleyicisini döndürür ve ayarlar `termstat` için belirtilen işlem tarafından döndürülen sonuç kodu. Aksi takdirde, -1 döndürür ve ayarlar `errno` gibi.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`ECHILD`|Belirtilen işlem var, `procHandle` geçersiz veya çağrısı [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx) veya [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) API başarısız oldu.|  
|`EINVAL`|`action` geçersizdir.|  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_cwait` İşlevi bekler tarafından sağlanan işlem kimliği belirtilen işlemin sonlandırılması için `procHandle`. Değeri `procHandle` için geçirilen `_cwait` çağrısı tarafından döndürülen değer olmalıdır [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) belirtilen işlem oluşturulan işlevi. İşlem kimliği önce ererse `_cwait` olarak adlandırılır, `_cwait` hemen döndürür. `_cwait` kendisi için diğer bilinen işlemin tamamlanmasını beklemek için herhangi bir işlem tarafından kullanılan geçerli bir tanıtıcı (`procHandle`) bulunmaktadır.  
  
 `termstat` belirtilen işlemin dönüş kodu depolanacağı bir arabellek noktalarına. Değeri `termstat` belirtilen işlem normalde Windows çağırarak sonlandırıldı olup olmadığını gösteren [ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx) API. `ExitProcess` Belirtilen işlem çağırırsa dahili olarak çağrılır `exit` veya `_exit`, döndürür `main`, veya sonuna ulaştığında `main`. Geri geçirilir değeri hakkında daha fazla bilgi için `termstat`, bkz: [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx). Varsa `_cwait` için bir NULL değer kullanılarak çağrılan `termstat`, belirtilen işlemin dönüş kodu saklanmaz.  
  
 `action` Parametresi, Windows işletim sistemi tarafından yoksayıldığından, çünkü üst-alt ilişkisi bu ortamlarda uygulanmaz.  
  
 Sürece `procHandle` -1 -2 mi (geçerli işlem ya da iş parçacığı işleme), tanıtıcı kapatılacak. Bu nedenle, bu durumda, döndürülen tanıtıcı kullanmayın.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_cwait`|\<Process.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_cwait.c  
// compile with: /c  
// This program launches several processes and waits  
// for a specified process to finish.  
  
#define _CRT_RAND_S  
  
#include <windows.h>  
#include <process.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
// Macro to get a random integer within a specified range  
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))  
  
struct PROCESS  
{  
   int     nPid;  
   char    name[40];  
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };  
  
int main( int argc, char *argv[] )  
{  
   int termstat, c;  
   unsigned int number;  
  
   srand( (unsigned)time( NULL ) );    // Seed randomizer  
  
   // If no arguments, this is the calling process  
   if ( argc == 1 )  
   {  
      // Spawn processes in numeric order  
      for ( c = 0; c < 4; c++ ) {  
         _flushall();  
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],   
                                    process[c].name, NULL );  
      }  
  
      // Wait for randomly specified process, and respond when done   
      c = getrandom( 0, 3 );  
      printf( "Come here, %s.\n", process[c].name );  
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );  
      printf( "Thank you, %s.\n", process[c].name );  
  
   }  
   // If there are arguments, this must be a spawned process   
   else  
   {  
      // Delay for a period that's determined by process number  
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );  
      printf( "Hi, Dad. It's %s.\n", argv[1] );  
   }  
}  
```  
  
```Output  
Hi, Dad. It's Ann.  
Come here, Ann.  
Thank you, Ann.  
Hi, Dad. It's Beth.  
Hi, Dad. It's Carl.  
Hi, Dad. It's Dave.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)