---
title: _spawn, _wspawn İşlevleri
ms.date: 11/04/2016
apilocation:
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- _spawn
- _tspawnlp
- _tspawnlpe
- _tspawnve
- _tspawnvp
- _tspawnvpe
- _tspawnl
- spawn
- _tspawnv
- _tspawnle
- wspawn
helpviewer_keywords:
- _tspawnve function
- _spawn functions
- _tspawnlpe function
- tspawnvpe function
- processes, creating
- tspawnve function
- _tspawnvp function
- spawn functions
- tspawnl function
- tspawnlp function
- _tspawnvpe function
- _tspawnl function
- tspawnvp function
- tspawnv function
- processes, executing new
- _tspawnv function
- tspawnle function
- process creation
- _tspawnlp function
- tspawnlpe function
- _tspawnle function
ms.assetid: bb47c703-5216-4e09-8023-8cf25bbf2cf9
ms.openlocfilehash: 044aaee376be02d0d3734ea8982a8c4db47f7d39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267864"
---
# <a name="spawn-wspawn-functions"></a>_spawn, _wspawn İşlevleri

Her biri `_spawn` işlevleri oluşturur ve yeni bir işlem yürütür:

|||
|-|-|
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|

İşlev adının sonuna harf değişimi belirler.

|Harfi|Değişken|
|-|-|
| `e`  | `envp`, dizi işaretçileri ortam ayarlarına, yeni işlemin geçirilir.  |
| `l`  | Komut satırı bağımsız değişkenleri için ayrı ayrı geçirilir `_spawn` işlevi. Bu sonekin, genellikle yeni bir işlem için parametre sayısı önceden bilindiğinde kullanılır.  |
| `p`  | `PATH` ortam değişkeni, yürütülecek dosyayı bulmak için kullanılır.  |
| `v`  | `argv`, dizi işaretçileri komut satırı bağımsız değişkenleri, geçirilen `_spawn` işlevi. Bu sonekin, genellikle bir dizi yeni bir işlem için parametre değişken olduğunda kullanılır.  |

## <a name="remarks"></a>Açıklamalar

`_spawn` İşlevleri her oluşturun ve yeni bir işlem yürütür. Bunlar otomatik olarak algılamayı çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde işleyin. `_wspawn` İşlevleri olan geniş karakter sürümleri `_spawn` işlevleri; çok baytlı karakter dizelerini işlemez. Aksi takdirde, `_wspawn` işlevler öğesine aynı şekilde davranır, `_spawn` ortaklarınıza.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tspawnl`|`_spawnl`|`_spawnl`|`_wspawnl`|
|`_tspawnle`|`_spawnle`|`_spawnle`|`_wspawnle`|
|`_tspawnlp`|`_spawnlp`|`_spawnlp`|`_wspawnlp`|
|`_tspawnlpe`|`_spawnlpe`|`_spawnlpe`|`_wspawnlpe`|
|`_tspawnv`|`_spawnv`|`_spawnv`|`_wspawnv`|
|`_tspawnve`|`_spawnve`|`_spawnve`|`_wspawnve`|
|`_tspawnvp`|`_spawnvp`|`_spawnvp`|`_wspawnvp`|
|`_tspawnvpe`|`_spawnvpe`|`_spawnvpe`|`_wspawnvpe`|

Yeterli bellek yükleme ve yeni işlem yürütme için kullanılabilir olmalıdır. `mode` Bağımsız değişken önce ve sırasında arama işlemi tarafından gerçekleştirilecek eylemi `_spawn`. Aşağıdaki değerleri `mode` Process.h içinde tanımlanır:

|||
|-|-|
| `_P_OVERLAY`  | Katmanları arama bir işlem çağırma işlemine yok etme, yeni bir işlem ile (aynı efekt olarak `_exec` çağırır).  |
| `_P_WAIT`  | Yeni bir işlem yürütme işlemi tamamlanana kadar çağıran bir iş parçacığını askıya alır (zaman uyumlu `_spawn`).  |
| `_P_NOWAIT` veya `_P_NOWAITO`  | Yeni işlem aynı anda arama işlemi yürütmeye devam eder (zaman uyumsuz `_spawn`).  |
| `_P_DETACH`  | Arama işlemi yürütmeye devam eder; Yeni işlem konsolu veya klavye erişim olmaksızın arka planda çalıştırılır. Çağrılar `_cwait` yeni işlemine yönelik başarısız (zaman uyumsuz `_spawn`).  |

`cmdname` Bağımsız değişkeni, yeni bir işlem olarak yürütülür ve bir tam yolu (kök), bir kısmi yolundan (geçerli çalışma dizini) veya yalnızca bir dosya adı belirtebilirsiniz dosyayı belirtir. Varsa `cmdname` bir dosya adı uzantısına sahip değil veya bir nokta (.) ile bitmiyor `_spawn` işlevi ilk çalıştığında .com dosya adı uzantısı ve .exe dosya adı uzantısı, .bat dosya adı uzantısı ve son olarak .cmd dosya adı uzantısı.

Varsa `cmdname` uzantısı kullanılır bir dosya adı uzantısı, yalnızca sahiptir. Varsa `cmdname` nokta ile biten `_spawn` çağrı arar `cmdname` hiçbir dosya adı uzantısına sahip. `_spawnlp`, `_spawnlpe`, `_spawnvp`, Ve `_spawnvpe` işlevleri aramak için `cmdname` (aynı yordamları kullanarak) tarafından belirtilen dizinlerde `PATH` ortam değişkeni.

Varsa `cmdname` (diğer bir deyişle, göreli bir yol ise), bir sürücü tanımlayıcısı veya herhangi bir eğik çizgi içeren, `_spawn` çağrı için yalnızca belirtilen dosyasını arar; hiçbir yolu arama yapılır.

Geçmişte, bunlardan bazıları işlevler kümesi `errno` sıfır üzerinde başarılı durumuna; şu anki davranışı bırakmaktır `errno` C Standart tarafından belirtilen başarılı olma durumunda olduğu. Eski davranışını benzetmek ihtiyacınız varsa, ayarlayın `errno` bu işlevler çağırma önce sıfır.

> [!NOTE]
>  Uygun katmana başlatma ve sonlandırma emin olmak için kullanmayın `setjmp` veya `longjmp` işlevi girin veya bir katmana yordamı bırakın.

## <a name="arguments-for-the-spawned-process"></a>Üretilmiş işlem için bağımsız değişkenler

Bağımsız değişkenler için yeni işlem geçirilecek bağımsız değişken olarak karakter dizeleri bir veya daha fazla işaretçiden vermek `_spawn` çağırın. Bu karakter dizeleri üretilmiş işlem için bağımsız değişken listesi oluşturur. Toplam uzunluğu dizelerine işaretçilerdir yeni işlemin bağımsız değişken listesi 1024 baytı aşmamalıdır. Sondaki boş karakter ('\0') için her dizeye sayı yer almaz, ancak boşluk karakterleri (bağımsız değişkenler ayırmak için otomatik olarak eklenir) dahil edilir.

> [!NOTE]
>  Dizeler gömülü boşluklar beklenmeyen davranışlara neden olabilir; Örneğin, geçirme `_spawn` dize `"hi there"` iki bağımsız değişkeni, alma yeni işleminde sonuçlanır `"hi"` ve `"there"`. Amaç adlı bir dosyayı açma yeni işlem sahip ise "Merhaba yok", işlem başarısız olur. Bu dize Alıntısı tarafından kaçının: `"\"hi there\""`.

> [!IMPORTANT]
>  Kullanıcı girişi için geçmeyin `_spawn` açıkça içeriğini Denetlemeden. `_spawn` bir çağrı sonuçlanır [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) şekilde nitelenmemiş yol adları için olası güvenlik açıklarını müşteri adayı göz önünde bulundurun.

İşaretçiler bağımsız değişken olarak ayrı bağımsız değişkenler geçirebilirsiniz (içinde `_spawnl`, `_spawnle`, `_spawnlp`, ve `_spawnlpe`) veya bir işaretçiler dizisi olarak (içinde `_spawnv`, `_spawnve`, `_spawnvp`, ve `_spawnvpe`). En az bir bağımsız değişken geçmelidir `arg0` veya `argv`[0] için üretilmiş işlem. Komut satırında yazarsınız kural olarak, bu bağımsız değişken programın adı aynıdır. Farklı bir değer, bir hata üretmez.

`_spawnl`, `_spawnle`, `_spawnlp`, Ve `_spawnlpe` çağrıları genellikle burada bağımsız değişken sayısı bilinen önceden durumlarda kullanılır. `arg0` Bağımsız değişken ise genellikle bir işaretçiye `cmdname`. Bağımsız değişkenler `arg1` aracılığıyla `argn` yeni bağımsız değişken listesini oluşturan karakter dizelerine. Aşağıdaki `argn`, olmalıdır bir **NULL** bağımsız değişken listesinin sonunu işaretlemek için işaretçi.

`_spawnv`, `_spawnve`, `_spawnvp`, Ve `_spawnvpe` çağrıları, değişken sayıda bağımsız değişkenler için yeni bir işlem olduğunda yararlıdır. İşaretçiler bağımsız değişkenler, bir dizi olarak geçirilir `argv` *.* Bağımsız değişken `argv`[0] genellikle bir yol için bir işaretçi gerçek modda program adına korumalı modda mı ve `argv`[1] aracılığıyla `argv`[`n`] yeni bağımsız değişken listesini oluşturan karakter dizelerine. Bağımsız değişken `argv`[`n` + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonunu işaretlemek için işaretçi.

## <a name="environment-of-the-spawned-process"></a>Üretilmiş işlem ortamı

Açık dosyaların bir `_spawn` çağrı yapılır yeni işlem içinde açık kalır. İçinde `_spawnl`, `_spawnlp`, `_spawnv`, ve `_spawnvp` çağrıları, yeni işlem ortam çağırma işleminin devralır. Kullanabileceğiniz `_spawnle`, `_spawnlpe`, `_spawnve`, ve `_spawnvpe` ortam ayarları listesini geçirerek yeni bir işlem ortamı değiştirmek için çağrıları `envp` bağımsız değişken. Bağımsız değişken `envp` her öğesi (dışında son öğe) işaret eden bir boş sonlandırılmış dizeye bir ortam değişkeni tanımlama karakter işaretçileri dizisidir. Bu tür bir dize genellikle formundadır `NAME` = `value` burada `NAME` bir ortam değişkeni adıdır ve `value` bu değişkeni ayarlamak dize değeridir. (Unutmayın `value` çift tırnak işaretleri arasına değil.) Son öğenin `envp` dizisi olmalıdır **NULL**. Zaman `envp` kendisi **NULL**, üretilen işlemde üst işleme ortam ayarlarını devralır.

`_spawn` İşlevleri yeni işlem için çeviri modunu dahil olmak üzere açık dosyalar hakkındaki tüm bilgileri iletebilir. Bu bilgiler, gerçek modda geçirilir `C_FILE_INFO` ortamında girişi. Başlangıç kodu bu giriş normal olarak işler ve ortamdan siler. Ancak, bir `_spawn` işlevi C olmayan bir işlem olarak çoğaltılır, bu girdi ortamda kalır. Ortam bilgileri, gerçek modda ikili biçimde geçtiğinden yazdırma ortamı bu giriş için tanım dizesinde grafik karakterlerini gösterir. Normal işlemler üzerinde diğer herhangi bir etkisi olmamalıdır. Korumalı modda ortam bilgilerini metin biçiminde geçirilir ve bu nedenle herhangi bir grafik karakter içerir.

Açıkça temizleme gerekir (kullanarak `fflush` veya `_flushall`) veya herhangi bir akışı çağırmadan önce kapatmak bir `_spawn` işlevi.

Yapılan çağrılar tarafından oluşturulan yeni işlemleri `_spawn` yordamları sinyal ayarları korumak değil. Bunun yerine, üretilen işlemde sinyal ayarlarını varsayılan değere sıfırlar.

## <a name="redirecting-output"></a>Çıktı yeniden yönlendirme

Çağırıyorsanız `_spawn` bir DLL veya bir GUI uygulaması ve bir kanala çıkışı yönlendirmek istiyorsanız, iki seçeneğiniz vardır:

- Bir kanal oluşturmak için Win32 API kullanın. ardından çağırın [AllocConsole](/windows/console/allocconsole), başlangıç yapısı ve çağrı tanıtıcı değerlerini ayarlayın [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa).

- Çağrı [_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md) , bir kanal oluşturmak ve uygulamayı kullanarak çağırma **cmd.exe /c** (veya **command.exe /c**).

## <a name="example"></a>Örnek

```
// crt_spawn.c
// This program accepts a number in the range
// 1-8 from the command line. Based on the number it receives,
// it executes one of the eight different procedures that
// spawn the process named child. For some of these procedures,
// the CHILD.EXE file must be in the same directory; for
// others, it only has to be in the same path.
//

#include <stdio.h>
#include <process.h>

char *my_env[] =
{
   "THIS=environment will be",
   "PASSED=to child.exe by the",
   "_SPAWNLE=and",
   "_SPAWNLPE=and",
   "_SPAWNVE=and",
   "_SPAWNVPE=functions",
   NULL
};

int main( int argc, char *argv[] )
{
   char *args[4];

   // Set up parameters to be sent:
   args[0] = "child";
   args[1] = "spawn??";
   args[2] = "two";
   args[3] = NULL;

   if (argc <= 2)
   {
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );
      exit( 1 );
   }

   switch (argv[1][0])   // Based on first letter of argument
   {
   case '1':
      _spawnl( _P_WAIT, argv[2], argv[2], "_spawnl", "two", NULL );
      break;
   case '2':
      _spawnle( _P_WAIT, argv[2], argv[2], "_spawnle", "two",
               NULL, my_env );
      break;
   case '3':
      _spawnlp( _P_WAIT, argv[2], argv[2], "_spawnlp", "two", NULL );
      break;
   case '4':
      _spawnlpe( _P_WAIT, argv[2], argv[2], "_spawnlpe", "two",
                NULL, my_env );
      break;
   case '5':
      _spawnv( _P_OVERLAY, argv[2], args );
      break;
   case '6':
      _spawnve( _P_OVERLAY, argv[2], args, my_env );
      break;
   case '7':
      _spawnvp( _P_OVERLAY, argv[2], args );
      break;
   case '8':
      _spawnvpe( _P_OVERLAY, argv[2], args, my_env );
      break;
   default:
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );
      exit( 1 );
   }
   printf( "from SPAWN!\n" );
}
```

```Output
child process output
from SPAWN!
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../c-runtime-library/process-and-environment-control.md)<br/>
[abort](../c-runtime-library/reference/abort.md)<br/>
[atexit](../c-runtime-library/reference/atexit.md)<br/>
[_exec, _wexec İşlevleri](../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_flushall](../c-runtime-library/reference/flushall.md)<br/>
[_getmbcp](../c-runtime-library/reference/getmbcp.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)<br/>
[_setmbcp](../c-runtime-library/reference/setmbcp.md)<br/>
[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)
