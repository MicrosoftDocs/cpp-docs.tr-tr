---
title: _open, _wopen
ms.date: 11/04/2016
apiname:
- _open
- _wopen
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
- _wopen
- _topen
- _open
helpviewer_keywords:
- opening files, for file I/O
- topen function
- _open function
- _topen function
- _wopen function
- files [C++], opening
- wopen function
- open function
ms.assetid: 13f6a0c3-d1aa-450d-a7aa-74abc91b163e
ms.openlocfilehash: 2395b1aa48b7802a508ab0cb8be1ef35a1a81564
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612999"
---
# <a name="open-wopen"></a>_open, _wopen

Bir dosya açar. Bu işlevlerin daha güvenli sürümleri kullanılabilir olmadığından kullanım dışıdır; bkz: [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int _open(
   const char *filename,
   int oflag [,
   int pmode]
);
int _wopen(
   const wchar_t *filename,
   int oflag [,
   int pmode]
);
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Dosya adı.

*oflag*<br/>
İzin verilen işlemleri türü.

*pmode*<br/>
İzni modu.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, açık dosya için bir dosya tanımlayıcısını döndürür. -1 dönüş değeri bir hata gösterir. Bu durumda **errno** aşağıdaki değerlerden birine ayarlayın.

|errno değeri|Koşul|
|-|-|
**SPAWN**|Yazma, dosyanın salt okunur bir dosyayı açmaya çalıştığınız paylaşma modunda belirtilen işlemine izin vermiyor veya verilen yolun bir dizindir.
**EEXIST**|**_O_CREAT** ve **_O_EXCL** bayrakları belirtildi, ancak *filename* zaten mevcut.
**EINVAL**|Geçersiz *oflag* veya *pmode* bağımsız değişken.
**EMFILE**|Daha fazla hiçbir dosya tanımlayıcısı kullanılabilir (çok fazla dosya açık).
**ENOENT**|Dosya veya yol bulunamadı.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Aç** işlevi tarafından belirtilen dosyayı açar *filename* okuma veya yazma, belirtildiği için hazırlar *oflag*. **_wopen** geniş karakterli sürümüdür **_aç**; *filename* bağımsız değişkeni **_wopen** geniş karakterli bir dizedir. **_wopen** ve **_aç** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_topen**|**_aç**|**_aç**|**_wopen**|

*oflag* bir tamsayı ifade, bir veya daha fazla aşağıdaki bildirim sabitleri veya tanımlanan sabit birleşimleri biçimlendirilmiş \<fcntl.h >.

|*oflag* sabit|Davranış|
|-|-|
**_O_APPEND**|Dosya işaretçisini dosyanın her yazma işleminden önce sonuna taşır.
**_O_BINARY**|Dosya ikili (çevrilmemiş) modda açılır. (Bkz [fopen](fopen-wfopen.md) ikili modu açıklaması.)
**_O_CREAT**|Bir dosya oluşturur ve yazma için açar. Dosya belirtilen hiçbir etkisi *filename* bulunmaktadır. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT** &AMP;#124; **_O_SHORT_LIVED**|Geçici olarak bir dosya oluşturur ve mümkünse diske temizleme değil. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT** &AMP;#124; **_O_TEMPORARY**|Geçici olarak bir dosya oluşturur. son dosya tanımlayıcısı kapatıldığında dosya silinir. *Pmode* bağımsız değişkeni gereklidir **_O_CREAT** belirtilir.
**_O_CREAT**&AMP;#124; ` _O_EXCL`|Bir hata değeri tarafından belirtilen dosya döndürür *filename* bulunmaktadır. Yalnızca ile kullanıldığında geçerlidir **_O_CREAT**.
**_O_NOINHERIT**|Paylaşılan dosya tanımlayıcısı oluşturulmasını engeller.
**_O_RANDOM**|Önbelleğe alma iyileştirildiğini, ancak rastgele erişim için diskten sınırlı olduğunu belirtir.
**_O_RDONLY**|Yalnızca okumak için bir dosya açar. İle belirtilemez **_O_RDWR** veya **_O_WRONLY**.
**_O_RDWR**|Hem okuma ve yazma için bir dosya açar. İle belirtilemez **_O_RDONLY** veya **_O_WRONLY**.
**_O_SEQUENTIAL**|Önbelleğe alma iyileştirildiğini, ancak sıralı erişim için diskten sınırlı olduğunu belirtir.
**_O_TEXT**|Metin (çevrilmiş) modunda bir dosya açar. (Daha fazla bilgi için [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](fopen-wfopen.md).)
**_O_TRUNC**|Bir dosyayı açar ve uzunluğu sıfır kendisine keser; Dosya yazma iznine sahip olmalıdır. İle belirtilemez **_O_RDONLY**. **_O_TRUNC** ile kullanılan **_O_CREAT** varolan bir dosyayı açar veya bir dosya oluşturur. **Not:** **_O_TRUNC** bayrağı belirtilen dosyanın içeriğini yok eder.
**_O_WRONLY**|Yalnızca yazmak için bir dosya açar. İle belirtilemez **_O_RDONLY** veya **_O_RDWR**.
**_O_U16TEXT**|Unicode UTF-16 modunda bir dosya açar.
**_O_U8TEXT**|Unicode UTF-8 modunda bir dosya açar.
**_O_WTEXT**|Bir dosya Unicode modunda açar.

Dosya erişim modu belirtmek için ya da belirtmeniz gerekir **_O_RDONLY**, **_O_RDWR**, veya **_O_WRONLY**. Erişim modu için varsayılan değer yoktur.

Varsa **_O_WTEXT** okumak, bir dosyayı açmak için kullanılan **_aç** dosyasının başında okur ve bir bayt sırası işareti (BOM) denetler. Bir ürün reçetesi varsa, dosyayı UTF-8 veya UTF-16LE, ürün reçetesi bağlı olarak kabul edilir. Hiçbir BOM olmadığında, dosya ANSI kabul edilir. Ne zaman bir dosya açıldığında yazma için kullanarak **_O_WTEXT**, UTF-16 kullanılır. Bakılmaksızın herhangi önceki ayar veya bayt sıra işareti, varsa **_O_U8TEXT** olan kullanıldığında, dosyanın her zaman UTF-8; açılır **_O_U16TEXT** olan kullanıldığında, dosya her zaman UTF-16 açılır.

Ne zaman bir dosya açıldığında Unicode modunda kullanarak **_O_WTEXT**, **_O_U8TEXT**, veya **_O_U16TEXT**, giriş işlevleri Çevir UTF-16 verileri dosyadan okunan veriler türü olarak depolanan **wchar_t**. Unicode modunda açılan bir dosyaya yazma işlevleri beklediğiniz UTF-16 veri türü olarak depolanan içeren arabellek **wchar_t**. UTF-8 kodlanmış dosyası, ardından UTF-16 verileri UTF-8 yazılması ve okunduğunda, bu dosyanın içeriğini UTF-8 olarak kodlanmış UTF-16 çevrilir çevrilir. Girişimi okumak veya tek sayıda bayt Unicode modunda yazmak için bir parametre doğrulama hatasına neden olur. Programınız UTF-8 olarak depolanan verileri okuma veya yazma için bir Unicode modunda yerine bir metin veya ikili dosya modu kullanın. Tüm gerekli kodlama çeviri için sorumlu olursunuz.

Varsa **_aç** çağrılır **_O_WRONLY** | **_O_APPEND** (ekleme modu) ve **_O_WTEXT**, **_O_ U16TEXT**, veya **_O_U8TEXT**, ilk çalıştığında dosyası okuma ve yazma için açılamadı ÜR okuyun ve ardından yalnızca yazmak için yeniden açın. Dosya başarısız yazma ve okuma için açılırken, yalnızca yazmak için dosyayı açar ve varsayılan değer Unicode modu ayarını kullanır.

İki veya daha fazla bildirim sabitleri için form kullanılan zaman *oflag* bağımsız değişkeni, sabitleri, bit düzeyinde OR işleci ile birleştirilir ( **&#124;** ). İkili ve metin modları için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

*Pmode* bağımsız değişkeni gereklidir yalnızca **_O_CREAT** belirtilir. Dosya zaten varsa *pmode* göz ardı edilir. Aksi takdirde, *pmode* ilk kez yeni dosya kapatıldığında, ayarlanmış olan dosya izin ayarlarını belirtir. **_open** geçerli bir dosya izni maskesi için uygular *pmode* önce izinleri ayarlayın. (Daha fazla bilgi için [_umask](umask.md).) *pmode* birini veya her ikisini Şunda tanımlı olan aşağıdaki bildirim sabitleri içeren bir tamsayı ifade \<sys\stat.h >.

|*pmode*|Açıklama|
|-|-|
**_S_IREAD**|Yalnızca okuma izin verilir.
**_S_IWRITE**|Yazma izin verilir. (Aslında, okuma ve yazma verir.)
**_S_IREAD** &AMP;#124; **_S_IWRITE**|Okuma ve yazma izin verilir.

Her iki sabitleri verildiğinde, bit düzeyinde OR işleci ile birleştirilir ( **&#124;** ). Windows tüm dosyaları okunabilir; Salt yazma izni kullanılamıyor. Bu nedenle, modları **_s_ıwrıte** ve **_s_ıread** | **_s_ıwrıte** eşdeğerdir.

Bir değer varsa bileşimi dışında **_s_ıread** ve **_s_ıwrıte** için belirtilen *pmode*— geçerli bir belirtse bile *pmode*başka bir işletim sisteminde — veya herhangi bir izin verilen'den başka değer varsa *oflag* değerleri belirtilirse, işlev hata ayıklama modunda bir onaylama işlemi oluşturur ve içindeaçıklandığıgibigeçersizparametreişleyicisiçağırır[Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_aç**|\<io.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >|
|**_wopen**|\<io.h > veya \<wchar.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >|

**_open** ve **_wopen** Microsoft uzantılarıdır. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_open.c
// compile with: /W3
/* This program uses _open to open a file
* named CRT_OPEN.C for input and a file named CRT_OPEN.OUT
* for output. The files are then closed.
*/
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int fh1, fh2;

   fh1 = _open( "CRT_OPEN.C", _O_RDONLY ); // C4996
   // Note: _open is deprecated; consider using _sopen_s instead
   if( fh1 == -1 )
      perror( "Open failed on input file" );
   else
   {
      printf( "Open succeeded on input file\n" );
      _close( fh1 );
   }

   fh2 = _open( "CRT_OPEN.OUT", _O_WRONLY | _O_CREAT, _S_IREAD |
                            _S_IWRITE ); // C4996
   if( fh2 == -1 )
      perror( "Open failed on output file" );
   else
   {
      printf( "Open succeeded on output file\n" );
      _close( fh2 );
   }
}
```

### <a name="output"></a>Çıkış

```Output
Open succeeded on input file
Open succeeded on output file
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
