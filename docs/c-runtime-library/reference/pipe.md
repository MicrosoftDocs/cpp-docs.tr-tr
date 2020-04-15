---
title: _pipe
ms.date: 4/2/2020
api_name:
- _pipe
- _o__pipe
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- pipe
- _pipe
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
ms.openlocfilehash: 5bac435bed26decee0069f5814d1f3d25a54470a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338494"
---
# <a name="_pipe"></a>_pipe

Okuma ve yazma için bir boru oluşturur.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _pipe(
   int *pfds,
   unsigned int psize,
   int textmode
);
```

### <a name="parameters"></a>Parametreler

*pfds*<br/>
Dosya tanımlayıcılarını basılı tutmak ve yazmak için iki **int'lik** bir dizi işaretçi.

*psize*<br/>
Rezerve etmek için bellek miktarı.

*Textmode*<br/>
Dosya modu.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür. Bir hatayı belirtmek için -1 döndürür. Hata da, **errno** şu değerlerden birine ayarlanır:

- **EMFILE**, başka dosya tanımlayıcısı olmadığını gösterir.

- **ENFILE**, bir sistem-dosya-tablo taşma gösterir.

- **EINVAL**, dizi *pfds* bir null işaretçi veya *textmode* için geçersiz bir değer geçirildiğini gösterir.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [errno, _doserrno, _sys_errlist ve _sys_nerr'a](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_pipe** işlevi, bir programın diğer programlara bilgi aktarmak için kullandığı yapay bir G/Ç kanalı olan bir *boru*oluşturur. Bir dosya işaretçisi, dosya tanımlayıcısı veya her ikisi de olduğundan bir dosyaya benzer ve Standart Kitaplık giriş ve çıktı işlevleri kullanılarak okunabilir veya yazılabilir. Ancak, bir boru belirli bir dosyayı veya aygıtı temsil etmez. Bunun yerine, programın kendi belleğinden bağımsız olan ve tamamen işletim sistemi tarafından denetlenir bellekte geçici depolama temsil eder.

**_pipe** **_open** benzer ama okuma ve yazma için boru açar ve bir yerine iki dosya tanımlayıcıları döndürür. Program borunun her iki tarafını da kullanabilir veya ihtiyaç duymuyor olanı kapatabilir. Örneğin, Windows'daki komut işlemcisi **PROGRAM1** | **PROGRAM2**gibi bir komut uyguluyor bir boru oluşturur.

**PROGRAM1'in** standart çıktı tanımlayıcısı borunun yazma tanımlayıcısına iliştirilir. **PROGRAM2'nin** standart giriş tanımlayıcısı, borunun okunan tanımlayıcısına iliştirilir. Bu, bilgileri diğer programlara aktarmak için geçici dosya oluşturma gereksinimini ortadan kaldırır.

**_pipe** işlevi *pfds* argümanında boruya iki dosya tanımlayıcısı döndürür. [0] *öğesi*okuma tanımlayıcısını, [1] *öğesi*ise yazma tanımlayıcısını içerir. Boru dosyası tanımlayıcıları diğer dosya tanımlayıcıları ile aynı şekilde kullanılır. (Düşük seviyeli giriş ve çıkış fonksiyonları **_read** ve **_write** bir borudan okuyup yazabilir.) Boru sonu koşulunu algılamak için, bayt sayısı okundukça 0 döndürecek **bir _read** isteği olup olmadığını denetleyin.

*Psize* bağımsız değişkeni, boru için rezerve etmek üzere baytlarda bulunan bellek miktarını belirtir. *Textmode* bağımsız değişkeni, borunun çeviri modunu belirtir. Manifesto **sabiti _O_TEXT** bir metin çevirisi, sabit **_O_BINARY** ise ikili çeviri belirtir. (Bkz. [fopen, metin](fopen-wfopen.md) ve ikili modların açıklaması için _wfopen.) *Textmode* bağımsız değişkeni 0 ise, **_pipe** varsayılan mod değişkeni tarafından belirtilen varsayılan çeviri modunu [_fmode.](../../c-runtime-library/fmode.md)

Çok iş parçacığı lı programlarda kilitleme yapılmaz. Döndürülen dosya tanımlayıcıları yeni açılır ve **_pipe** arama tamamlanana kadar herhangi bir iş parçacığı tarafından başvurulmamalıdır.

Bir üst işlem ve bir alt işlem arasında iletişim kurmak için **_pipe** işlevini kullanmak için, her işlem boru üzerinde yalnızca bir tanımlayıcı açık olmalıdır. Tanımlayıcılar zıt olmalıdır: ebeveynbir okuma tanımlayıcısı açıksa, o zaman çocuğun bir yazma tanımlayıcısı açık olmalıdır. Bunu yapmanın en kolay yolu bitwise**|** veya ( ) *textmode*ile **_O_NOINHERIT** bayrağı. Ardından, çocuğa aktarmak istediğiniz boru tanımlayıcısının devredilebilir bir kopyasını oluşturmak için **_dup** veya **_dup2** kullanın. Özgün tanımlayıcıyı kapatın ve ardından alt işlemi yumurtlayın. Yumurtlama çağrısından döndükten sonra, üst işlemdeki yinelenen tanımlayıcıyı kapatın. Daha fazla bilgi için, bu makalenin ilerleyen bilgilerine bakın.

Windows işletim sisteminde, tüm tanımlayıcıları kapatıldığında bir boru yok edilir. (Borudaki tüm okunan tanımlayıcılar kapatılmışsa, boruya yazmak hataya neden olur.) Borudaki tüm okuma ve yazma işlemleri, G/Ç isteğini tamamlamak için yeterli veri veya yeterli arabellek alanı olana kadar bekleyin.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_pipe**|\<io.h>|\<fcntl.h>,1 \<errno.h>2|

1 **_O_BINARY** ve **_O_TEXT** tanımlar için.

2 **errno** tanımları.

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

Bu temel bir filtre uygulamasıdır. Uygulamayı crt_pipe_beeper, yumurtlayan uygulamanın stdout'unu filtreye yönlendiren bir boru oluşturduktan sonra oluşturur. Filtre ASCII 7 (bip) karakterlerini kaldırır.

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
