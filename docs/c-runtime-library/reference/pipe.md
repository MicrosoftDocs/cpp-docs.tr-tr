---
title: _pipe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _pipe
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- pipe
- _pipe
dev_langs:
- C++
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 95169aa5070493be76db6306f4d5863d6a2e654f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="pipe"></a>_pipe
Okuma ve yazma için bir kanal oluşturur.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _pipe(  
   int *pfds,  
   unsigned int psize,  
   int textmode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pfds`[2]  
 Okuma tutun ve dosya tanımlayıcıları yazmak için dizisi.  
  
 `psize`  
 Ayrılacak bellek miktarı.  
  
 `textmode`  
 Dosya modu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa 0 döndürür. Bir hatayı belirtmek için -1 döndürür. Hata, `errno` bu değerlerden birine ayarlayın:  
  
-   `EMFILE`, daha fazla hiçbir dosya tanımlayıcıları kullanılabilir olduğunu gösterir.  
  
-   `ENFILE`, bir sistem dosyası tablosu taşması gösterir.  
  
-   `EINVAL`, hangi gösterir ya da dizi `pfds` null işaretçinin veya geçersiz bir değer için `textmode` geçirildi.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_pipe` İşlev oluşturur bir *kanal*, diğer programlara bilgi aktarmak için bir program kullanan yapay bir g/ç kanaldan olduğu. Bir kanal dosya işaretçisini, bir dosya tanımlayıcısı veya her ikisini olmadığı ve okuma veya standart kitaplığını kullanarak giriş ve çıkış işlevler yazma için bir dosya benzer. Ancak, bir kanal belirli bir dosya veya aygıt göstermiyor. Bunun yerine, programın kendi bellek bağımsızdır ve tamamen işletim sistemi tarafından denetlenen bellekte geçici depolama temsil eder.  
  
 `_pipe` benzer `_open` ancak okumak ve yazmak için kanal açar ve iki dosya tanımlayıcıları biri yerine döndürür. Program, her iki tarafında kanal kullanın veya gerekli olmayan bir kapatın. Örneğin, bir komut gibi yürüttüğünde Windows Komut işlemcisi bir kanal oluşturur `PROGRAM1 | PROGRAM2`.  
  
 Standart çıktı tanımlayıcısının `PROGRAM1` kanal 's yazma tanımlayıcısına eklenir. Standart giriş tanımlayıcısı `PROGRAM2` kanal 's okuma tanımlayıcısına eklenir. Bu bilgi diğer programlara geçirmek için geçici dosyalar oluşturma ihtiyacını ortadan kaldırır.  
  
 `_pipe` İşlevi kanala iki dosya tanımlayıcıları döndürür `pfds` bağımsız değişkeni. Öğe `pfds`[0] okuma tanımlayıcısı ve öğeyi içeren `pfds`[1] yazma tanımlayıcısı içeriyor. Kanal dosya tanımlayıcıları diğer dosya tanımlayıcıları aynı şekilde kullanılır. (Düşük düzey giriş ve çıkış işlevleri `_read` ve `_write` okuma ve yazma için bir kanal.) Kanal son koşulunu algılamak için denetle bir `_read` isteği 0 okunan bayt sayısını döndürür.  
  
 `psize` Bağımsız değişkeni için kanal ayırmak için bayt cinsinden bellek miktarını belirtir. `textmode` Bağımsız değişkeni kanal çeviri modu belirtir. Bildirim sabiti `_O_TEXT` bir metin çeviri ve sabiti belirtir `_O_BINARY` ikili bir çeviri belirtir. (Bkz [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md) metin ve ikili modun açıklaması için.) Varsa `textmode` bağımsız değişken: 0, `_pipe` varsayılan mod değişkeni tarafından belirtilen varsayılan çeviri modu kullanan [_fmode](../../c-runtime-library/fmode.md).  
  
 Çoklu iş parçacığı kullanan programlarda hiçbir kilitleme gerçekleştirilir. Döndürülen dosya tanımlayıcıları yeni açıldığından ve sonra kadar herhangi bir iş parçacığı tarafından başvurulan değil `_pipe` çağrısı tamamlandığında.  
  
 Kullanılacak `_pipe` üst işlem ve bir alt işlem arasında iletişim kurmak için işlev, her işlem yalnızca bir tanımlayıcısı kanalda açık olmalıdır. Tanımlayıcıları opposites olmalıdır: üst açmak okuma bir tanımlayıcısı varsa sonra alt açmak yazma tanımlayıcısı olmalıdır. Bunu yapmanın en kolay yolu `OR` (`|`) `_O_NOINHERIT` ile bayrak `textmode`. Ardından, `_dup` veya `_dup2` alt öğesi olarak geçirmek istediğiniz kanal tanımlayıcısı devralınabilir bir kopyasını oluşturun. Özgün tanımlayıcısı kapatın ve alt işlem oluşturma. Spawn çağrısından döndürme üzerinde yinelenen tanımlayıcısı üst işleminde kapatın. Daha fazla bilgi için bu makalenin sonraki bölümlerinde örnek 2 bakın.  
  
 Tüm kendi tanımlayıcıları kapatılmış olduğunda Windows işletim sisteminde bir kanal yok. (Tüm okuma tanımlayıcıları kanal üzerinde kapatılmışsa kanala yazma bir hataya neden olur.) Tüm okuma ve yazma kanal bekleme işlemi oluncaya kadar yeterli veri veya g/ç isteği tamamlamak için yeterli arabellek alanı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_pipe`|\<io.h >|\<fcntl.h>,1 \<errno.h>2|  
  
 1 için `_O_BINARY` ve `_O_TEXT` tanımlar.  
  
 2 `errno` tanımlar.  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example-1"></a>Örnek 1  
  
```C  
// crt_pipe.c  
/* This program uses the _pipe function to pass streams of  
 * text to spawned processes.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <io.h>  
#include <fcntl.h>  
#include <process.h>  
#include <math.h>  
  
enum PIPES { READ, WRITE }; /* Constants 0 and 1 for READ and WRITE */  
#define NUMPROBLEM 8  
  
int main( int argc, char *argv[] )  
{  
  
   int fdpipe[2];  
   char hstr[20];  
   int pid, problem, c;  
   int termstat;  
  
   /* If no arguments, this is the spawning process */  
   if( argc == 1 )  
   {  
  
      setvbuf( stdout, NULL, _IONBF, 0 );  
  
      /* Open a set of pipes */  
      if( _pipe( fdpipe, 256, O_BINARY ) == -1 )  
          exit( 1 );  
  
      /* Convert pipe read descriptor to string and pass as argument   
       * to spawned program. Program spawns itself (argv[0]).  
       */  
      _itoa_s( fdpipe[READ], hstr, sizeof(hstr), 10 );  
      if( ( pid = _spawnl( P_NOWAIT, argv[0], argv[0],   
            hstr, NULL ) ) == -1 )  
          printf( "Spawn failed" );  
  
      /* Put problem in write pipe. Since spawned program is   
       * running simultaneously, first solutions may be done   
       * before last problem is given.  
       */  
      for( problem = 1000; problem <= NUMPROBLEM * 1000; problem += 1000)  
      {  
  
         printf( "Son, what is the square root of %d?\n", problem );  
         _write( fdpipe[WRITE], (char *)&problem, sizeof( int ) );  
  
      }  
  
      /* Wait until spawned program is done processing. */  
      _cwait( &termstat, pid, WAIT_CHILD );  
      if( termstat & 0x0 )  
         printf( "Child failed\n" );  
  
      _close( fdpipe[READ] );  
      _close( fdpipe[WRITE] );  
  
   }  
  
   /* If there is an argument, this must be the spawned process. */  
   else  
   {  
  
      /* Convert passed string descriptor to integer descriptor. */  
      fdpipe[READ] = atoi( argv[1] );  
  
      /* Read problem from pipe and calculate solution. */  
      for( c = 0; c < NUMPROBLEM; c++ )  
      {  
  
        _read( fdpipe[READ], (char *)&problem, sizeof( int ) );  
        printf( "Dad, the square root of %d is %3.2f.\n",  
                 problem, sqrt( ( double )problem ) );  
  
      }  
   }  
}  
```  
  
```Output  
Son, what is the square root of 1000?  
Son, what is the square root of 2000?  
Son, what iDad, the square root of 1000 is 31.62.  
Dad, the square root of 2000 is 44.72.  
s the square root of 3000?  
Dad, the square root of 3000 is 54.77.  
Son, what is the square root of 4000?  
Dad, the square root of 4000 is 63.25.  
Son, what is the square root of 5000?  
Dad, the square root of 5000 is 70.71.  
Son, what is the square root of 6000?  
SonDad, the square root of 6000 is 77.46.  
, what is the square root of 7000?  
Dad, the square root of 7000 is 83.67.  
Son, what is the square root of 8000?  
Dad, the square root of 8000 is 89.44.  
```  
  
## <a name="example-2"></a>Örnek 2  
 Bu, bir temel filtre uygulamasıdır. Filtre oluşturulan uygulamanın stdout yönlendiren bir kanal oluşturduktan sonra uygulama crt_pipe_beeper olarak çoğaltılır. Filtre ASCII 7 (bip) karakterleri kaldırır.  
  
```C  
// crt_pipe_beeper.c  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   int   i;  
   for(i=0;i<10;++i)  
      {  
         printf("This is speaker beep number %d...\n\7", i+1);  
      }  
   return 0;  
}  
```  
  
 Gerçek filtre uygulama:  
  
```C  
// crt_pipe_BeepFilter.C  
// arguments: crt_pipe_beeper.exe  
  
#include <windows.h>  
#include <process.h>  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
#define   OUT_BUFF_SIZE 512  
#define   READ_FD 0  
#define   WRITE_FD 1  
#define   BEEP_CHAR 7  
  
char szBuffer[OUT_BUFF_SIZE];  
  
int Filter(char* szBuff, ULONG nSize, int nChar)  
{  
   char* szPos = szBuff + nSize -1;  
   char* szEnd = szPos;  
   int nRet = nSize;  
  
   while (szPos > szBuff)  
   {  
      if (*szPos == nChar)  
         {  
            memmove(szPos, szPos+1, szEnd - szPos);  
            --nRet;  
         }  
      --szPos;  
   }  
   return nRet;  
}  
  
int main(int argc, char** argv)  
{  
   int nExitCode = STILL_ACTIVE;  
   if (argc >= 2)  
   {  
      HANDLE hProcess;  
      int fdStdOut;  
      int fdStdOutPipe[2];  
  
      // Create the pipe  
      if(_pipe(fdStdOutPipe, 512, O_NOINHERIT) == -1)  
         return   1;  
  
      // Duplicate stdout file descriptor (next line will close original)  
      fdStdOut = _dup(_fileno(stdout));  
  
      // Duplicate write end of pipe to stdout file descriptor  
      if(_dup2(fdStdOutPipe[WRITE_FD], _fileno(stdout)) != 0)  
         return   2;  
  
      // Close original write end of pipe  
      _close(fdStdOutPipe[WRITE_FD]);  
  
      // Spawn process  
      hProcess = (HANDLE)_spawnvp(P_NOWAIT, argv[1],   
       (const char* const*)&argv[1]);  
  
      // Duplicate copy of original stdout back into stdout  
      if(_dup2(fdStdOut, _fileno(stdout)) != 0)  
         return   3;  
  
      // Close duplicate copy of original stdout  
      _close(fdStdOut);  
  
      if(hProcess)  
      {  
         int nOutRead;  
         while   (nExitCode == STILL_ACTIVE)  
         {  
            nOutRead = _read(fdStdOutPipe[READ_FD],   
             szBuffer, OUT_BUFF_SIZE);  
            if(nOutRead)  
            {  
               nOutRead = Filter(szBuffer, nOutRead, BEEP_CHAR);  
               fwrite(szBuffer, 1, nOutRead, stdout);  
            }  
  
            if(!GetExitCodeProcess(hProcess,(unsigned long*)&nExitCode))  
               return 4;  
         }  
      }  
   }  
   return nExitCode;  
}  
```  
  
```Output  
This is speaker beep number 1...  
This is speaker beep number 2...  
This is speaker beep number 3...  
This is speaker beep number 4...  
This is speaker beep number 5...  
This is speaker beep number 6...  
This is speaker beep number 7...  
This is speaker beep number 8...  
This is speaker beep number 9...  
This is speaker beep number 10...  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)