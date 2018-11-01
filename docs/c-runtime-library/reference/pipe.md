---
title: _pipe
ms.date: 11/04/2016
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
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
ms.openlocfilehash: c5db59fecd84ae291e5651b1cec1be31c815e53a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453989"
---
# <a name="pipe"></a>_pipe

Okuma ve yazma için bir kanal oluşturur.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _pipe(
   int *pfds,
   unsigned int psize,
   int textmode
);
```

### <a name="parameters"></a>Parametreler

*PFD'ler*<br/>
İki işaretçi **int** tutun okuma ve yazma dosya tanımlayıcılarını.

*psize*<br/>
Ayrılacak bellek miktarı.

*metin modu*<br/>
Dosya modu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür. Hatayı belirtmek için -1 döndürür. Hata durumunda, **errno** şu değerlerden birine ayarlayın:

- **EMFILE**, hiçbir daha fazla dosya tanımlayıcısı bulunmadığını gösterir.

- **ENFILE**, bir sistem dosyası tablo taşmasını gösterir.

- **EINVAL**, belirten bir dizi ya da *PFD'ler* null bir işaretçiyse veya geçersiz bir değer için *metin modu* geçirildi.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Pipe** işlevi oluşturur bir *kanal*, bir programın başka programlara bilgi geçirmek için kullandığı yapay bir g/ç kanalının olduğu. Bir kanal, çünkü bir dosya işaretçisiyse, bir dosya tanımlayıcısı veya her ikisi de sahiptir ve okuma veya standart kitaplığını kullanarak giriş ve çıkış işlevleri için yazılan bir dosya benzer. Ancak, bir kanal belirli bir dosyayı veya cihazı temsil etmiyor. Bunun yerine, programın kendi bellek bağımsız ve tamamen işletim sistemi tarafından denetlenen bellekteki geçici depolama temsil eder.

**_pipe** benzer **_aç** ancak kanalı okuma ve yazma için açar ve bir yerine iki dosya tanımlayıcı döndürür. Programı her iki tarafını kullanabilir veya ihtiyaç duymadığı tarafı kapatabilir. Örneğin, komut işleyicisi, Windows gibi bir komut yürüttüğünde, bir kanal oluşturur **PROGRAM1** | **PROGRAM2**.

Standart çıkış tanımlayıcısı **PROGRAM1** kanalın yazma tanımlayıcısına iliştirilmiş. Standart giriş tanımlayıcısı **PROGRAM2** kanalın okuma tanımlayıcısına iliştirilmiş. Bu, diğer programlara bilgi geçirmek için geçici dosyalar oluşturma gereksinimini ortadan kaldırır.

**_Pipe** işlevi kanala iki dosya tanımlayıcısı döndürür *PFD'ler* bağımsız değişken. Öğe *PFD'ler*[0] okuma tanımlayıcısını ve öğeyi içeren *PFD'ler*[1] ise yazma tanımlayıcısını içerir. Kanal dosya tanımlayıcıları, diğer dosya tanımlayıcılarıyla aynı şekilde kullanılır. (Alt düzey giriş ve çıkış işlevleri **_read** ve **_write** okuyabileceği ve bir kanala yazılabilir.) Kanal bitiş koşulunu algılamak için denetle bir **_read** okunan bayt sayısı olarak 0 getiren isteği.

*Psize* bağımsız değişkeni kanala ayrılacak bayt cinsinden bellek miktarını belirtir. *Metin modu* bağımsız değişkeni kanal için çeviri modunu belirtir. Bildirim sabiti **_O_TEXT** metin çevirisi ve sabit belirtir **_o_bınary** ikili dönüşümü belirler. (Bkz [fopen, _wfopen](fopen-wfopen.md) metin ve ikili modların tanımı için.) Varsa *metin modu* bağımsız değişken: 0, **_pipe** varsayılan modlu değişkeninin belirttiği varsayılan çeviri modunu kullanır [_fmode](../../c-runtime-library/fmode.md).

Çok iş parçacıklı programlarda hiçbir kilitleme gerçekleştirilmez. Döndürülen dosya tanımlayıcıları yeni açılmıştır ve herhangi bir iş parçacığı tarafından başvurulmaması gereken **_pipe** çağrısı tamamlanmadan.

Kullanılacak **_pipe** bir üst işlem ve bir alt işlem arasında iletişim kurmak için işlev, her bir işlemin kanalda açık yalnızca bir tanımlayıcısı olmalıdır. Tanımlayıcıların birbirinin zıttı olması gerekir: üst açık bir okuma tanımlayıcısı varsa sonra alt açık bir yazma tanımlayıcısı olması gerekir. Bunu yapmanın en kolay yolu için bit düzeyinde veya (**|**) **_O_NOINHERIT** ile bayrak *metin modu*. Ardından, **_dup** veya **_dup2** alta geçirmek istediğiniz kanal tanımlayıcısının devralınabilir bir kopyasını oluşturmak için. Özgün tanımlayıcıyı kapatın ve sonra alt işlemi oluşturun. Oluşturma çağrısından dönüşte döndüren üzerinde üst işlemdeki yinelenen tanımlayıcıyı kapatın. Daha fazla bilgi için bu makaledeki örnek 2 bakın.

Windows işletim sisteminde, kendi tanımlayıcılarının tümü kapandığında kanal yokolur. (Kanal üzerindeki tüm okuma tanımlayıcıları kapatılmışsa, ardından kanala yazmak hataya neden olur.) Tüm okuma ve yazma kanal bekleme işlemi yeterli veri veya g/ç isteği tamamlamak için yeterli arabellek alanı oluncaya kadar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_pipe**|\<io.h >|\<fcntl.h >, 1 \<errno.h > 2|

1 için **_o_bınary** ve **_O_TEXT** tanımlar.

2 **errno** tanımlar.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

Bu temel bir filtre uygulamasıdır. Bu, oluşturulan uygulamanın stdout'unu filtreye yönlendiren bir kanal oluşturduktan sonra crt_pipe_beeper uygulamasını oluşturur. Filtre ASCII 7 (bip) karakterlerini kaldırır.

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

Gerçek filtre uygulaması:

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

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
