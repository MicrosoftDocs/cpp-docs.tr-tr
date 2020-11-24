---
title: fopen_s, _wfopen_s
description: Ve için API 'YI açıklar `fopen_s``_wfopen_s`
ms.date: 11/20/2020
api_name:
- _wfopen_s
- fopen_s
- _o__wfopen_s
- _o_fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: 1d6d0b739db1177b903c0e8aa8e6f55e49c1df16
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483171"
---
# <a name="fopen_s-_wfopen_s"></a>`fopen_s`, `_wfopen_s`

Bir dosya açar. Bu sürümlerinde [`fopen, _wfopen`](fopen-wfopen.md) , [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Söz dizimi

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Parametreler

*`pFile`*\
Açılan dosyanın işaretçisini alacak dosya işaretçisine yönelik bir işaretçi.

*`filename`*\
Kısaltın.

*`mode`*\
İzin verilen erişim türü.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu. Bu hata kodları hakkında daha fazla bilgi için bkz [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ..

### <a name="error-conditions"></a>Hata koşulları

|*`pFile`*|*`filename`*|*`mode`*|Dönüş Değeri|İçeriği *`pFile`*|
|-------------|----------------|------------|------------------|------------------------|
|**`NULL`**|herhangi biri|herhangi biri|**`EINVAL`**|değiştirilmediği|
|herhangi biri|**`NULL`**|herhangi biri|**`EINVAL`**|değiştirilmediği|
|herhangi biri|herhangi biri|**`NULL`**|**`EINVAL`**|değiştirilmediği|

## <a name="remarks"></a>Açıklamalar

Tarafından açılan **`fopen_s`** ve **`_wfopen_s`** paylaşılabilir olmayan dosyalar. Bir dosyanın paylaşılabilir olmasını istiyorsanız, [`_fsopen, _wfsopen`](fsopen-wfsopen.md) uygun paylaşım modu sabiti ile kullanın (örneğin, **`_SH_DENYNO`** okuma/yazma paylaşımı için).

İşlevi, dosya **`fopen_s`** *adıyla* belirtilen dosyayı açar. **`_wfopen_s`** , öğesinin geniş karakterli bir sürümüdür **`fopen_s`** ; bağımsız değişkenler **`_wfopen_s`** geniş karakterli dizelerdir. **`_wfopen_s`** ve **`fopen_s`** aynı şekilde davranır.

**`fopen_s`** yürütme noktasındaki dosya sisteminde geçerli olan yolları kabul eder; **`fopen_s`** Kodu yürüten sistemin, yürütme sırasında paylaşıma veya eşlenmiş ağ sürücüsüne erişimi olduğu sürece, eşlenen ağ sürücüleriyle ılgılı UNC yolları ve yolları kabul edilir. İçin yollar oluştururken **`fopen_s`** , yürütme ortamında sürücülerin, yolların veya ağ paylaşımlarının kullanılabilirliği hakkında varsayımlar yapmayın. Bir yoldaki Dizin ayırıcıları olarak eğik çizgi (/) veya ters eğik çizgi ( \\ ) kullanabilirsiniz.

Bu işlevler, parametrelerini doğrular. *`pFile`*, *`filename`* , Veya *`mode`* bir null işaretçisiyse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre özel durumu oluşturur.

Dosyada başka bir işlem yapmadan önce işlevin başarılı olup olmadığını görmek için her zaman döndürülen değeri denetleyin. Bir hata oluşursa, hata kodu döndürülür ve genel değişken **`errno`** ayarlanır. Daha fazla bilgi için bkz. [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="unicode-support"></a>Unicode desteği

**`fopen_s`** Unicode dosya akışlarını destekler. Yeni veya var olan bir Unicode dosyasını açmak için istenen kodlamayı belirten bir *CCS* bayrağı geçirin **`fopen_s`** :

**`fopen_s(&fp, "newfile.txt", "rw, ccs=**_encoding_**");`**

*Kodlama* için izin verilen değerler **`UNICODE`** , **`UTF-8`** , ve **`UTF-16LE`** . İçin hiçbir değer belirtilmemişse *`encoding`* **`fopen_s`** ANSI kodlaması kullanır.

Dosya zaten varsa ve okuma ya da ekleme için açılırsa, dosyada varsa, bayt sırası Işareti (BOM), kodlamayı belirler. BOM kodlaması, bayrak tarafından belirtilen kodlamaya göre önceliklidir *`ccs`* . *`ccs`* Kodlama yalnızca BIR bom yoksa veya dosya yeni bir dosya ise kullanılır.

> [!NOTE]
> BOM-algılama yalnızca Unicode modunda açılan dosyalar için geçerlidir; Yani, *`ccs`* bayrağını geçirerek.

Aşağıdaki tabloda, *`ccs`* ' a verilen çeşitli bayrakların **`fopen_s`** ve dosyadaki bayt sırası işaretlerinin modları özetlenmektedir.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>CCS bayrak ve BOM temelinde kullanılan kodlamalar

|CCS bayrağı|BOM (veya yeni dosya) yok|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**`UNICODE`**|**`UTF-16LE`**|**`UTF-8`**|**`UTF-16LE`**|
|**`UTF-8`**|**`UTF-8`**|**`UTF-8`**|**`UTF-16LE`**|
|**`UTF-16LE`**|**`UTF-16LE`**|**`UTF-8`**|**`UTF-16LE`**|

Unicode modunda yazmak için açılan dosyalarda otomatik olarak yazılmış bir BOM vardır.

*`mode`* **`"a, ccs=` _encoding_ Kodlama `"`** ise, **`fopen_s`** önce dosyayı hem okuma erişimi hem de yazma erişimiyle açmaya çalışır. Başarılı olursa, işlev, dosyanın kodlamasını belirlemede ürün reçetesini okur; başarısız olursa, işlev dosya için varsayılan kodlamayı kullanır. Her iki durumda da, **`fopen_s`** dosyayı salt yazılır erişimle yeniden açar. (Bu **`a`** yalnızca mod için geçerlidir, değil **`a+`** .)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**`_tfopen_s`**|**`fopen_s`**|**`fopen_s`**|**`_wfopen_s`**|

Karakter dizesi, *`mode`* aşağıdaki gibi dosya için istenen erişim türünü belirtir.

|*`mode`*|Access|
|-|-|
| **`"r"`** | Okuma için açılır. Dosya yoksa veya bulunamıyorsa, **`fopen_s`** çağrı başarısız olur. |
| **`"w"`** | Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir. |
| **`"a"`** | Dosyanın sonuna (ekleme), yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaretini kaldırmadan açılır. Mevcut değilse dosyayı oluşturur. |
| **`"r+"`** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w +"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **`"a+"`** | Okuma ve ekleme için açılır. Ekleme işlemi, yeni veriler dosyaya yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma işlemi tamamlandıktan sonra EOF işaretleyicisi geri yüklenmez. Mevcut değilse dosyayı oluşturur. |

Bir dosya **`"a"`** veya **`"a+"`** erişim türü kullanılarak açıldığında, dosyanın sonunda tüm yazma işlemleri oluşur. Dosya işaretçisi veya kullanılarak yeniden konumlandırılabilir [`fseek`](fseek-fseeki64.md) [`rewind`](rewind.md) , ancak mevcut verilerin üzerine yazılmaması için herhangi bir yazma işlemi yapılmadan önce her zaman dosyanın sonuna geri taşınır.

**`"a"`** Mod, dosyaya eklemeden önce EOF işaretçisini kaldırmaz. Ekleme gerçekleştirildikten sonra, MS-DOS `TYPE` komutu yalnızca özgün EOF işaretine kadar olan verileri gösterir ve dosyaya eklenen verileri etkilemez. **`"a+"`** Mod, dosyaya eklemeden önce EOF işaretçisini kaldırır. Ekleme yapıldıktan sonra, MS-DOS `TYPE` komutu dosyadaki tüm verileri gösterir. **`"a+"`** Mod, EOF işaretleyicisi ile sonlandırılan bir akış dosyasına ekleme için gereklidir `CTRL+Z` .

**`"r+"`**, **`"w+"`** Veya **`"a+"`** erişim türü belirtildiğinde, hem okuma hem de yazma için izin verilir. (Dosyanın "Güncelleştir" için açık olduğu söylenir.) Ancak, okumayı yazmaya geçtiğinizde, giriş işlemi bir EOF işaretleyicisi içinde gelmelidir. EOF işaretleyicisi yoksa, bir dosya konumlandırma işlevine aradaki bir çağrı kullanmanız gerekir. Dosya konumlandırma işlevleri **`fsetpos`** , ve ' dir [`fseek`](fseek-fseeki64.md) [`rewind`](rewind.md) . Yazmaya geçiş yaparken, **`fflush`** bir dosya konumlandırma işlevine ya da bir araya giren çağrı kullanmanız gerekir.

Yukarıdaki değerlere ek olarak, *`mode`* yeni satır karakterlerinin çeviri modunu belirtmek için aşağıdaki karakterler içine eklenebilir:

|*`mode`* icisi|Çeviri modu|
|-|-|
| **`t`** | Metin (çevrilmiş) modunda aç. |
| **`b`** | İkili (çevrilmemiş) modda aç; satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin (çevrilmiş) modunda, `CTRL+Z` girişte dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılan dosyalarda **`"a+"`** , **`fopen_s`** dosyanın sonunda bir olup olmadığını denetler `CTRL+Z` ve mümkünse kaldırır. Bu işlem, [`fseek`](fseek-fseeki64.md) **`ftell`** ile biten bir dosya içinde hareket etmek için ve kullanılması `CTRL+Z` , [`fseek`](fseek-fseeki64.md) dosyanın sonunda yanlış davranmasına neden olabilir.

Ayrıca, metin modunda, satır başı/satır besleme birleşimleri girişte tek satırlık akışlara çevrilir ve satır besleme karakterleri, çıkışdaki satır başı akış birleşimlerine çevrilir. Unicode Stream-g/ç işlevi metin modunda (varsayılan) çalışırken, kaynak veya hedef akışın çok baytlı karakterler dizisi olduğu varsayılır. Unicode akış girişi işlevleri çok baytlı karakterleri geniş karakterlere (işlevine yapılan bir çağrıda olduğu gibi **`mbtowc`** ) dönüştürür. Aynı nedenden dolayı, Unicode akış çıkışı işlevleri çok baytlı karakterlere (işlevine yapılan bir çağrıda olduğu gibi) çok fazla karakter dönüştürür **`wctomb`** .

**`t`** Veya **`b`** içinde verilmezse *`mode`* , varsayılan çeviri modu [_fmode](../../c-runtime-library/fmode.md)genel değişken tarafından tanımlanır. **`t`** Veya **`b`** bağımsız değişkenin öneki varsa, işlev başarısız olur ve döndürür **`NULL`** .

Unicode ve çok baytlı akışta metin ve ikili modlar kullanma hakkında daha fazla bilgi için bkz. metin ve ikili [mod dosyası g/](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ç ve [Unicode akış g/ç ve metin ve ikili modlar](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

|*`mode`* icisi|Davranış|
|-|-|
| **`c`** | Dosya arabelleğinin içeriklerinin, ya da çağrılırsa doğrudan diske yazılması için, ilişkili *dosya adı* için COMMIT bayrağını etkinleştirin **`fflush`** **`_flushall`** . |
| **`n`** | İlişkili *dosya adı* için COMMIT bayrağını "No-COMMIT" olarak sıfırlayın. Bu varsayılan seçenektir. Ayrıca, programınızı COMMODE. OBJ ile bağlarsanız Genel tamamlama bayrağını da geçersiz kılar. Programınızı COMMODE ile açıkça bağmadığınız takdirde Genel tamamlama bayrağı varsayılan olarak "No-COMMIT" olur. OBJ (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)). |
| **`n`** | Dosyanın alt süreçler tarafından devralınamayacağını belirtir. |
| **`S`** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir. |
| **`R`** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim |
| **`t`** | Geçici olarak bir dosya belirtir. Mümkünse, diske boşaltılmıyor. |
| **`D`** | Geçici olarak bir dosya belirtir. Son dosya işaretçisi kapatıldığında silinir. |
| **`ccs=**`_şifreleme_ | Bu dosya için kullanılacak kodlanan karakter kümesini (bir **`UTF-8`** , **`UTF-16LE`** veya veya **`UNICODE`** ) belirtir. ANSI kodlaması istiyorsanız belirtilmemiş olarak bırakın. |

' *`mode`* De kullanılan dize için geçerli karakterler **`fopen_s`** ve [`_fdopen`](fdopen-wfdopen.md) *`oflag`* [`_open`](open-wopen.md) aşağıdaki gibi, ve ' de kullanılan bağımsız değişkenlere karşılık gelir [`_sopen`](sopen-wsopen.md) .

|Dizedeki karakterler *`mode`*|*`oflag`* İçin eşdeğer değer`_open`/`_sopen`|
|-------------------------------|----------------------------------------------------|
|**`a`**|**`_O_WRONLY`** &#124; **`_O_APPEND`** (genellikle **`_O_WRONLY`** &#124; **`_O_CREAT`** &#124; **`_O_APPEND`** )|
|**`a+`**|**`_O_RDWR`** &#124; **`_O_APPEND`** (genellikle **`_O_RDWR`** &#124; **`_O_APPEND`** &#124; **`_O_CREAT`** )|
|**`R`**|**`_O_RDONLY`**|
|**`r+`**|**`_O_RDWR`**|
|**`w`**|**`_O_WRONLY`** (genellikle **`_O_WRONLY`** &#124; **`_O_CREAT`** &#124; **_O_TRUNC**)|
|**`w+`**|**`_O_RDWR`** (genellikle **`_O_RDWR`** &#124; **`_O_CREAT`** &#124; **_O_TRUNC**)|
|**`b`**|**`_O_BINARY`**|
|**`t`**|**`_O_TEXT`**|
|**`c`**|Yok|
|**`n`**|Yok|
|**`S`**|**`_O_SEQUENTIAL`**|
|**`R`**|**`_O_RANDOM`**|
|**`t`**|**`_O_SHORTLIVED`**|
|**`D`**|**`_O_TEMPORARY`**|
|**`ccs=UNICODE`**|**`_O_WTEXT`**|
|**`ccs=UTF-8`**|**`_O_UTF8`**|
|**`ccs=UTF-16LE`**|**`_O_UTF16`**|

**`rb`** Modunu kullanıyorsanız, kodunuzun bağlantı noktasına bağlantı oluşturmanız gerekmiyorsa, dosyanın çoğunu okumayı veya ağ performansını önemsemezseniz, bellek eşlemeli Win32 dosyaları da bir seçenek olabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**`fopen_s`**|`<stdio.h>`|
|**`_wfopen_s`**|`<stdio.h>` veya `<wchar.h>`|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

**`c`**, Ve **`n`** seçenekleri, **`t`** *`mode`* ve için MICROSOFT uzantılarıdır **`fopen_s`** [`_fdopen`](fdopen-wfdopen.md) ve ANSI taşınabilirliği istendiği yerde kullanılmamalıdır.

## <a name="example"></a>Örnek

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" doesn't exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it isn't NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)\
[`fclose, _fcloseall`](fclose-fcloseall.md)\
[`_fdopen, _wfdopen`](fdopen-wfdopen.md)\
[`ferror`](ferror.md)\
[`_fileno`](fileno.md)\
[`freopen, _wfreopen`](freopen-wfreopen.md)\
[`_open, _wopen`](open-wopen.md)\
[`_setmode`](setmode.md)
