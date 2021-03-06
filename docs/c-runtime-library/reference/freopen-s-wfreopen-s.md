---
description: 'Hakkında daha fazla bilgi edinin: freopen_s _wfreopen_s'
title: freopen_s, _wfreopen_s
ms.date: 2/23/2021
api_name:
- _wfreopen_s
- freopen_s
- _o__wfreopen_s
- _o_freopen_s
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- freopen_s
- _tfreopen_s
- _wfreopen_s
helpviewer_keywords:
- _tfreopen_s function
- _wfreopen_s function
- file pointers [C++], reassigning
- tfreopen_s function
- wfreopen_s function
- freopen_s function
ms.openlocfilehash: a2b9bf86d50972fcc820da3e53fd066717879ff3
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236744"
---
# <a name="freopen_s-_wfreopen_s"></a>`freopen_s`, `_wfreopen_s`

İle ilişkili olan dosyayı kapatır `oldStream` ve `stream` tarafından belirtilen dosyayı yeniden atar `fileName` .

Bu sürümlerinde [`freopen, _wfreopen`](freopen-wfreopen.md) , [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t freopen_s(
   FILE ** stream,
   const char * fileName,
   const char * mode,
   FILE* oldStream
);

errno_t _wfreopen_s(
   FILE ** stream,
   const wchar_t * fileName,
   const wchar_t * mode,
   FILE * oldStream
);
```

### <a name="parameters"></a>Parametreler

*`stream`*\
İşlev döndüğünde yeniden açılmış akışa işaret edecek bir out parametresi.

*`fileName`*\
Yeniden açılacak dosyanın yolu.

*` mode`*\
Yeniden açılmış akışın modu.

*`oldStream`*\
Yeniden açılacak akış. Temizlendi ve onunla ilişkili tüm dosyalar kapatılmıştır.

## <a name="return-value"></a>Döndürülen değer

Başarılı üzerinde sıfır; Aksi takdirde hata kodu. Bir hata oluşursa, özgün dosya kapatılır ve **`NULL`** *`stream`* *`stream`* Ayrıca **`NULL`**

Hata kodları hakkında daha fazla bilgi için bkz [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ..

## <a name="remarks"></a>Açıklamalar

**`freopen_s`** İşlev genellikle ile ilişkili önceden açılan akışları `stdin` `stdout` ve `stderr` başka bir dosyaya eklemek için kullanılır.

**`freopen_s`** İşlev, ile ilişkili olan dosyayı kapatır *`stream`* ve *`stream`* *yol* tarafından belirtilen dosyaya yeniden atar. **`_wfreopen_s`** , öğesinin geniş karakterli bir sürümüdür **`freopen_s`** ; *yolu* ve *` mode`* bağımsız değişkenler **`_wfreopen_s`** geniş karakterli dizelerdir. **`_wfreopen_s`** ve **`freopen_s`** aynı şekilde davranır.

*Pfile*, *Path*, *` mode`* veya varsa ya da *`stream`* **`NULL`** *yol* boş bir dize ise, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler öğesini **`errno`** olarak ayarlar **`EINVAL`** ve döndürür **`EINVAL`** .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|`TCHAR.H` rutin|_ `UNICODE & _MBCS` tanımlı değil|`_MBCS` tanımlı|`_UNICODE` tanımlı|
|---------------------|------------------------------------|--------------------|-----------------------|
|**`_tfreopen_s`**|**`freopen_s`**|**`freopen_s`**|**`_wfreopen_s`**|

**`freopen_s`** genellikle önceden açılan dosyaları **`stdin`** , **`stdout`** ve **`stderr`** Kullanıcı tarafından belirtilen dosyaları yeniden yönlendirmek için kullanılır. İle ilişkili yeni dosya, *`stream`* *` mode`* dosyası için istenen erişimin türünü belirten bir karakter dizesi olan ile açılır.

|*` mode`*|Access|
|-|-|
| **`"r"`** | Okuma için açılır. Dosya yoksa veya bulunamıyorsa, **`freopen_s`** çağrı başarısız olur. |
| **`"w"`** | Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir. |
| **`"a"`** | Dosyanın sonuna (ekleme), yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaretini kaldırmadan açılır. Mevcut değilse dosyayı oluşturur. |
| **`"r+"`** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **`"w+"`** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **`"a+"`** | Okuma ve ekleme için açılır. Ekleme işlemi, yeni veriler dosyaya yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma işlemi tamamlandıktan sonra EOF işaretleyicisi geri yüklenmez. Mevcut değilse dosyayı oluşturur. |

**`"w"`** Ve **`"w+"`** türlerini, var olan dosyaları yok etmek için dikkatli kullanın. C11 ' den başlayarak, **`"x"`** **`"w"`** **`"w+"`** dosyanın üzerine yazmak yerine işlevin başarısız olmasına neden olur.

Bir dosya **`"a"`** veya **`"a+"`** erişim türüyle açıldığında, dosyanın sonunda tüm yazma işlemleri gerçekleşir. Dosya işaretçisi veya kullanılarak yeniden konumlandırılabilse [`fseek`](fseek-fseeki64.md) de [`rewind`](rewind.md) , herhangi bir yazma işlemi yapılmadan önce dosya işaretçisi her zaman dosyanın sonuna taşınır. Bu nedenle, mevcut verilerin üzerine yazılamaz.

**`"a"`** Mod, dosyaya eklemeden önce EOF işaretçisini kaldırmaz. Ekleme gerçekleştirildikten sonra, MS-DOS türü komutu yalnızca özgün EOF işaretine kadar olan verileri gösterir ve dosyaya eklenen verileri etkilemez. **`"a+"`** Mod, dosyaya eklemeden önce EOF işaretçisini kaldırır. Eklendikten sonra, MS-DOS türü komutu dosyadaki tüm verileri gösterir. **`"a+"`** Mod, CTRL + Z EOF işaretleyicisi ile sonlandırılan bir akış dosyasına ekleme için gereklidir.

**`"r+"`**, **`"w+"`** Veya **`"a+"`** erişim türü belirtildiğinde, hem okuma hem de yazma için izin verilir (dosya "güncelleştirme" için açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, aradaki bir [`fsetpos`](fsetpos.md) , [`fseek`](fseek-fseeki64.md) veya [`rewind`](rewind.md) işlem olmalıdır. İsterseniz geçerli konum [`fsetpos`](fsetpos.md) veya işlem için belirtilebilir [`fseek`](fseek-fseeki64.md) . Yukarıdaki değerlere ek olarak, *` mode`* yeni satırlar için çeviri modunu belirtmek üzere dizeye aşağıdaki karakterlerden biri dahil edilebilir.

|*` mode`* icisi|Çeviri modu|
|-|-|
| **`t`** | Metin (çevrilmiş) modunda aç. |
| **`b`** | İkili (çevrilmemiş) modda aç; satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin (çevrilmiş) modunda, satır başı satır besleme (CR-LF) birleşimleri, girişte tek satırlık akış (LF) karakterlerine çevrilir; LF karakterleri çıkışındaki CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma veya yazma için açılan dosyalarda **`"a+"`** , çalışma zamanı kitaplığı dosyanın sonunda BIR CTRL + Z olup olmadığını denetler ve mümkünse onu kaldırır. Bu, [`fseek`](fseek-fseeki64.md) [`ftell`](ftell-ftelli64.md) bir dosya içinde hareket etmek için ve kullanılması, dosyanın sonuna doğru şekilde davranmasına neden olabileceğinden yapılır [`fseek`](fseek-fseeki64.md) . **`t`** Bir Microsoft uzantısı olduğundan, ANSI taşınabilirliği istediğinizde seçeneğini kullanmayın.

**`t`** Veya **`b`** içinde verilmezse *` mode`* , varsayılan çeviri modu genel değişken tarafından tanımlanır [`_fmode`](../../c-runtime-library/fmode.md) . **`t`** Veya **`b`** bağımsız değişkenin öneki varsa, işlev başarısız olur ve döndürür **`NULL`** .

Metin ve ikili modların bir tartışması için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**`freopen_s`**|`<stdio.h>`|
|**`_wfreopen_s`**|`<stdio.h>` veya `<wchar.h>`|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. ,, Ve konsolu ile ilişkili standart akış tutamaçları, **`stdin`** **`stdout`** **`stderr`** C çalışma zamanı işlevlerinin bunları UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. 

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_freopen_s.c
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.

#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   errno_t err;
   // Reassign "stderr" to "freopen.out":
   err = freopen_s( &stream, "freopen.out", "w", stderr );

   if( err != 0 )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); 
      fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>Ayrıca bkz.

[`Stream I/O`](../../c-runtime-library/stream-i-o.md)\
[`freopen, _wfreopen`](freopen-wfreopen.md)\
[`fclose, _fcloseall`](fclose-fcloseall.md)\
[`_fdopen, _wfdopen`](fdopen-wfdopen.md)\
[`_fileno`](fileno.md)\
[`fopen, _wfope`No](fopen-wfopen.md)\
[`_open, _wopen`](open-wopen.md)\
[`_setmode`](setmode.md)
