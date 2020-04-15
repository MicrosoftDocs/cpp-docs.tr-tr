---
title: fopen_s, _wfopen_s
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 80d04e75637cfab9795bf5dfb9da9786cf4ebd71
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346489"
---
# <a name="fopen_s-_wfopen_s"></a>fopen_s, _wfopen_s

Bir dosyayı açar. [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı [gibi, fopen _wfopen](fopen-wfopen.md) bu sürümlerinde güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Sözdizimi

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

*pFile*<br/>
Açılan dosyanın işaretçisini alacak dosya işaretçisine işaretçi.

*filename*<br/>
Dosyaadı.

*Modu*<br/>
Erişim türüne izin verilir.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu. Bu hata kodları hakkında daha fazla bilgi için [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

### <a name="error-conditions"></a>Hata Koşulları

|*pFile*|*filename*|*Modu*|Dönüş Değeri|*pFile* Içeriği|
|-------------|----------------|------------|------------------|------------------------|
|**Null**|herhangi bir|herhangi bir|**Eınval**|Değişme -den|
|herhangi bir|**Null**|herhangi bir|**Eınval**|Değişme -den|
|herhangi bir|herhangi bir|**Null**|**Eınval**|Değişme -den|

## <a name="remarks"></a>Açıklamalar

**fopen_s** ve **_wfopen_s** tarafından açılan dosyalar sharable değildir. Bir dosyanın kullanılabilir olmasını istiyorsanız, [_fsopen kullanın,](fsopen-wfsopen.md) _wfsopen uygun paylaşım modu sabiti ile birlikte (örneğin, okuma/yazma paylaşımı için **_SH_DENYNO.**

**fopen_s** işlevi *dosya adı*ile belirtilen dosyayı açar. **_wfopen_s** **fopen_s**geniş karakterli bir versiyonudur; **_wfopen_s** bağımsız değişkenler geniş karakterli dizeleridir. **_wfopen_s** ve **fopen_s** aynı şekilde aynı şekilde davranan.

**fopen_s,** yürütme noktasında dosya sisteminde geçerli olan yolları kabul eder; Eşlenen ağ sürücülerini içeren UNC yolları ve yolları, kodu çalıştıran sistem yürütme sırasında paylaşımveya eşlenen ağ sürücüsüne erişebildiğim sürece **fopen_s** tarafından kabul edilir. **fopen_s**için yollar oluştursanız, yürütme ortamında sürücülerin, yolların veya ağ paylaşımlarının kullanılabilirliği hakkında varsayımlarda bulunmayın. Bir yoltaki dizin ayırıcıları olarak ileri\\eğik çizgi (/) veya ters eğik çizgi () kullanabilirsiniz.

Bu işlevler parametrelerini doğrular. *pFile*, *filename*, veya *mod* null işaretçisi ise, bu işlevler [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre özel durum oluşturur.

Dosyaüzerinde başka işlemler gerçekleştirmeden önce işlevin başarılı olup olmadığını görmek için her zaman iade değerini denetleyin. Bir hata oluşursa, hata kodu döndürülür ve genel değişken **errno** ayarlanır. Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="unicode-support"></a>Unicode desteği

**fopen_s** Unicode dosya akışlarını destekler. Yeni veya varolan unicode dosyasını açmak için, **fopen_s**için istenen kodlamayı belirten bir *ccs* bayrağını geçirin:

**fopen_s(&fp, "newfile.txt", "rw, ccs=**_kodlama_**");**

*Kodlamaizin* izin verilen değerleri **UNICODE**, **UTF-8**ve **UTF-16LE'dir.** *Kodlama*için değer belirtilmemişse, **fopen_s** ANSI kodlamakullanır.

Dosya zaten varsa ve okumak veya ekolarak açılmak üzere açılmışsa, dosyada varsa Byte Order Mark (BOM) kodlamayı belirler. ÜRÜN REÇetesi *kodlaması, ccs* bayrağı tarafından belirtilen kodlamadan önce gelir. *Ccs* kodlaması yalnızca ürün bir ürün dürbonu olmadığında veya dosya yeni bir dosyaysa kullanılır.

> [!NOTE]
> BOM algılama yalnızca Unicode modunda açılan dosyalar için geçerlidir; yani, *ccs* bayrağı geçerek.

Aşağıdaki tablo, **fopen_s** verilen çeşitli *ccs* bayrakları ve dosyadaki Byte Order Marks için modları özetler.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>CCS Bayrak ve BOM'a Göre Kullanılan Kodlamalar

|ccs bayrağı|Hiçbir BOM (veya yeni dosya)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**Unicode**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode modunda yazılmak üzere açılan dosyaların kendilerine otomatik olarak yazılmış bir ÜRÜN BOM'u vardır.

*Mod* **"a, ccs=**_kodlama_**"** ise, **fopen_s** önce hem okuma erişimi hem de yazma erişimi ile dosyayı açmaya çalışır. Başarılı olursa, işlev dosya için kodlama belirlemek için ÜRÜN REM okur; başarısız olursa, işlev dosya için varsayılan kodlama kullanır. Her iki durumda da **fopen_s,** yalnızca yazma erişimiyle dosyayı yeniden açar. (Bu yalnızca **bir** mod için geçerlidir, **a+** değil.)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

Karakter dize *modu,* dosya için istenen erişim türünü aşağıdaki gibi belirtir.

|*Modu*|Erişim|
|-|-|
| **"r"** | Okumak için açılır. Dosya yoksa veya bulunamıyorsa, **fopen_s** arama başarısız olur. |
| **"w"** | Yazmak için boş bir dosya yı açar. Verilen dosya varsa, içeriği yok edilir. |
| **"a"** | Dosyaya yeni veriler yazılmadan önce dosya sonu (EOF) işaretçisini kaldırmadan dosyanın sonunda (ek) yazıiçin açılır. Yoksa dosyayı oluşturur. |
| **"r+"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w+"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a+"** | Okuma ve ekolarak açılır. Ek işlem, dosyaya yeni veriler yazılmadan önce EOF işaretçisinin kaldırılmasını içerir. EOF işaretçisi, yazma tamamlandıktan sonra geri yüklenmez. Yoksa dosyayı oluşturur. |

Bir dosya **"a"** veya **"a+"** erişim türü kullanılarak açıldığında, tüm yazma işlemleri dosyanın sonunda gerçekleşir. Dosya işaretçisi [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak varolan verilerin üzerine yazılamaması için herhangi bir yazma işlemi gerçekleştirilmeden önce her zaman dosyanın sonuna geri taşınır.

**"a"** modu, dosyaya ekilmeden önce EOF işaretçisini kaldırmaz. Ek olay dan sonra, MS-DOS TYPE komutu yalnızca özgün EOF işaretçisine kadar olan verileri gösterir ve dosyaya eklenen verileri göstermez. **"a+"** modu, dosyaya ekilmeden önce EOF işaretçisini kaldırır. Ekledikten sonra, MS-DOS TYPE komutu dosyadaki tüm verileri gösterir. CTRL+Z EOF işaretçisi kullanılarak sonlandırılan bir akış dosyasına ek olarak **"a+"** modu gereklidir.

**"r+"**, **"w+"** veya **"a+"** erişim türü belirtildiğinde, hem okuma hem de yazmaya izin verilir. (Dosyanın "güncelleştirme" için açık olduğu söylenir.) Ancak, okumadan yazmaya geçtiğiniz zaman, giriş işlemi bir EOF işaretçisi ile karşılaşmalıdır. EOF yoksa, dosya konumlandırma işlevine ara veren bir çağrı kullanmanız gerekir. Dosya konumlandırma işlevleri **fsetpos**, [fseek](fseek-fseeki64.md), ve [geri sarma](rewind.md). Yazmadan okumaya geçtiğiniz zaman, **fflush** veya dosya konumlandırma işlevi için araya giren bir çağrı kullanmanız gerekir.

Yukarıdaki değerlere ek olarak, aşağıdaki karakterler yeni satır karakterleri için çeviri modunu belirtmek için *moda* eklenebilir:

|*mod* değiştirici|Çeviri modu|
|-|-|
| **T** | Metin (çevrilmiş) modunda açın. |
| **B** | İkili (çevrilmemiş) modda açık; satır döndürme ve satır besleme karakterlerini içeren çeviriler bastırılır. |

Metin (çevrilmiş) modda CTRL+Z girişte dosya sonu karakteri olarak yorumlanır. **"a+"** ile okumak/yazmak için açılan **dosyalarda, fopen_s** dosyanın sonunda ctrl+Z olup olmadığını kontrol eder ve mümkünse kaldırır. CtRL+Z ile biten bir dosya içinde hareket etmek için [fseek](fseek-fseeki64.md) ve **ftell** kullanarak, [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış hareket neden olabilir, çünkü bu yapılır.

Ayrıca, metin modunda, satır satır beslemesi birleşimleri girişte tek satır beslemelerine ve satır besleme karakterleri çıkışta satır satır beslemesi birleşimlerine çevrilir. Unicode akışı-I/Ç işlevi metin modunda (varsayılan) çalıştığında, kaynak veya hedef akışı çok bayt karakter dizisi olarak kabul edilir. Bu nedenle, Unicode akış giriş işlevleri çok bayt karakterleri geniş karakterlere dönüştürür **(mbtowc** işlevine bir çağrı gibi). Aynı nedenle, Unicode akış çıkışı işlevleri geniş karakterleri çok bayt karakterlere dönüştürür **(wctomb** işlevine bir çağrı gibi).

**T** veya **b** *modunda*verilmiyorsa, varsayılan çeviri modu _fmode genel [değişken](../../c-runtime-library/fmode.md)tarafından tanımlanır. **T** veya **b** bağımsız değişkene önceden belirlenmişse, işlev başarısız olur ve **NULL**döndürür.

Unicode ve multibayt akış-I/O metin ve ikili modları kullanma hakkında daha fazla bilgi için Metin [ve İkili Modları Metin ve İkili Modlarda Metin ve İkili Modlar'da Metin ve İkili Modlar Dosya I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [Unicode Stream G/Ç'ye](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)bakın.

|*mod* değiştirici|Davranış|
|-|-|
| **C** | Fflush veya **_flushall** çağrıldığında, dosya arabellesinin içeriğinin doğrudan diske **fflush** yazılması için ilişkili *dosya adı* için işleme bayrağını etkinleştirin. |
| **n** | İlişkili *dosya adı* için işleme bayrağını "işlemeyok" olarak sıfırla. Bu varsayılandır. Ayrıca, programınızı COMMODE.OBJ'ye bağlarsanız, genel işleme bayrağını da geçersiz kılar. Programınızı açıkça COMMODE'a bağlamadığınız sürece genel işleme bayrağı varsayılanı "işleyiş yok"dur. OBJ (bkz. [Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)). |
| **N** | Dosyanın alt işlemler tarafından devralınmadığını belirtir. |
| **S** | Önbelleğe almanın diskten sıralı erişim için en iyi duruma getirilmiş, ancak bu amaçla değil, en iyi duruma getirilmiştir. |
| **R** | Önbelleğe almanın diskten rasgele erişim için en iyi duruma getirilmiş, ancak bu amaçla kullanılmadığını belirtir. |
| **T** | Bir dosyayı geçici olarak belirtir. Mümkünse diske kızdırılmez. |
| **D** | Bir dosyayı geçici olarak belirtir. Son dosya işaretçisi kapatıldığında silinir. |
| **ccs=**_kodlama_ | Bu dosya için kullanılacak kodlanmış karakter kümesini **(UTF-8,** **UTF-16LE**veya **UNICODE)** belirtir. ANSI kodlaması istiyorsanız belirtilmemiş bırakın. |

**fopen_s** ve [_fdopen](fdopen-wfdopen.md) kullanılan *mod* dizesinin geçerli karakterleri, [_open](open-wopen.md) ve [_sopen'da](sopen-wsopen.md)kullanılan *oflag* bağımsız değişkenlerine aşağıdaki gibi karşılık gelir.

|*Mod* dizesindeki karakterler|_open/_sopen için eşdeğer *oflag* değeri|
|-------------------------------|----------------------------------------------------|
|**A**|**_O_WRONLY** &#124; **_O_APPEND** (genellikle **_O_CREAT** &#124;** _O_APPEND **&#124;**'_O_CREAT _O_WRONLY)**|
|**a+**|**_O_RDWR** &#124; **_O_APPEND** (genellikle **_O_RDWR** **&#124; _O_APPEND** &#124; **_O_CREAT)**|
|**R**|**_O_RDONLY**|
|**r+**|**_O_RDWR**|
|**W**|**_O_WRONLY** (genellikle **_O_WRONLY &#124;** **_O_CREAT** &#124;** _O_TRUNC**)|
|**w+**|**_O_RDWR** **(genellikle** _O_RDWR &#124; &#124; **_O_TRUNC** **_O_CREAT)**|
|**B**|**_o_bınary**|
|**T**|**_o_text**|
|**C**|None|
|**n**|None|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs=UNICODE**|**_O_WTEXT**|
|**ccs=UTF-8**|**_O_UTF8**|
|**ccs=UTF-16LE**|**_O_UTF16**|

Eğer **rb** modu kullanıyorsanız, kodunuzu bağlantı noktası gerekmez ve dosyanın çok okumak ve / veya ağ performansı umurumda değil bekliyoruz, bellek win32 dosyaları eşlenen de bir seçenek olabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fopen_s**|\<stdio.h>|
|**_wfopen_s**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

**c**, **n**ve **t** *modu* seçenekleri **fopen_s** ve [_fdopen](fdopen-wfdopen.md) için Microsoft uzantılarıdır ve ANSI taşınabilirliğinin istendiği yerlerde kullanılmamalıdır.

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

   // Open for read (will fail if file "crt_fopen_s.c" does not exist)
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

   // Close stream if it is not NULL
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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
