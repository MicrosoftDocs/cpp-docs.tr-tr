---
title: fopen_s, _wfopen_s
ms.date: 11/04/2016
api_name:
- _wfopen_s
- fopen_s
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
ms.openlocfilehash: 2a400918a171c0009e40be8a20b814e8ded336ce
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957133"
---
# <a name="fopen_s-_wfopen_s"></a>fopen_s, _wfopen_s

Bir dosya açar. Fopen 'un bu sürümlerinde [_wfopen](fopen-wfopen.md) , [CRT 'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

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
Açılan dosyanın işaretçisini alacak dosya işaretçisine yönelik bir işaretçi.

*kısaltın*<br/>
Kısaltın.

*modundaysa*<br/>
İzin verilen erişim türü.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatada hata kodu. Bu hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

### <a name="error-conditions"></a>Hata koşulları

|*pFile*|*kısaltın*|*modundaysa*|Dönüş Değeri|*Pfile* içeriği|
|-------------|----------------|------------|------------------|------------------------|
|**DEĞER**|Kaydedilmemiş|Kaydedilmemiş|**EINVAL**|değiştirilmediği|
|Kaydedilmemiş|**DEĞER**|Kaydedilmemiş|**EINVAL**|değiştirilmediği|
|Kaydedilmemiş|Kaydedilmemiş|**DEĞER**|**EINVAL**|değiştirilmediği|

## <a name="remarks"></a>Açıklamalar

**Fopen_s** ve **_wfopen_s** tarafından açılan dosyalar paylaşılabilir değildir. Bir dosyanın paylaşılabilir olmasını istiyorsanız, uygun paylaşım modu sabiti ile [_fsopen, _wfsopen](fsopen-wfsopen.md) kullanın; örneğin, okuma/yazma paylaşımı Için **_Sh_denyno** .

**Fopen_s** işlevi, *filename*tarafından belirtilen dosyayı açar. **_wfopen_s** , **fopen_s**öğesinin geniş karakterli bir sürümüdür; **_wfopen_s** bağımsız değişkenleri geniş karakterli dizelerdir. **_wfopen_s** ve **fopen_s** aynı şekilde davranır.

**fopen_s** , yürütme noktasındaki dosya sisteminde geçerli olan yolları kabul eder; Kodu yürüten sistemin, yürütme sırasında paylaşıma veya eşlenmiş ağ sürücüsüne erişimi olduğu sürece, eşlenen ağ sürücülerine sahip UNC yolları ve yolları **fopen_s** tarafından kabul edilir. **Fopen_s**için yollar oluşturduğunuzda, yürütme ortamında sürücülerin, yolların veya ağ paylaşımlarının kullanılabilirliği hakkında varsayımlar yapmayın. Bir yoldaki Dizin ayırıcıları olarak eğik çizgi (/) veya ters\\eğik çizgi () kullanabilirsiniz.

Bu işlevler, parametrelerini doğrular. *Pfile*, *filename*veya *Mode* null bir Işaretçisiyse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz bir parametre özel durumu oluşturur.

Dosyada başka bir işlem gerçekleştirmeden önce işlevin başarılı olup olmadığını görmek için her zaman döndürülen değeri denetleyin. Bir hata oluşursa, hata kodu döndürülür ve **errno** genel değişkeni ayarlanır. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="unicode-support"></a>Unicode desteği

**Fopen_s** Unicode dosya akışlarını destekler. Yeni veya var olan bir Unicode dosyasını açmak için, **fopen_s**için istenen kodlamayı belirten bir *CCS* bayrağı geçirin:

**fopen_s (& FP, "NewFile. txt", "RW, CCS =** _Encoding_ **");**

*Kodlama* için izin verilen değerler **UNICODE**, **UTF-8**ve **UTF-16LE**' dir. *Kodlama*için hiçbir değer belirtilmemişse, **fopen_s** ANSI kodlaması kullanır.

Dosya zaten varsa ve okuma ya da ekleme için açılırsa, dosyada varsa, bayt sırası Işareti (BOM), kodlamayı belirler. BOM kodlaması, *CCS* bayrağıyla belirtilen kodlamaya göre önceliklidir. *CCS* kodlaması yalnızca bir BOM yoksa veya dosya yeni bir dosya ise kullanılır.

> [!NOTE]
> BOM-algılama yalnızca Unicode modunda açılan dosyalar için geçerlidir; diğer bir deyişle, *CCS* bayrağını geçirerek.

Aşağıdaki tabloda, **fopen_s** öğesine ve dosyadaki bayt sırası işaretlerine verilen çeşitli *CCS* bayraklarının modları özetlenmektedir.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>CCS bayrak ve BOM temelinde kullanılan kodlamalar

|CCS bayrağı|BOM (veya yeni dosya) yok|BOM UTF-8|BOM UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**KODLAMALARI**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode modunda yazmak için açılan dosyalarda otomatik olarak yazılmış bir BOM vardır.

*Mod* **"a, CCS =** _Encoding_ **"** ise, **fopen_s** önce dosyayı hem okuma erişimi hem de yazma erişimiyle açmaya çalışır. Başarılı olursa, işlev, dosyanın kodlamasını belirlemede ürün reçetesini okur; başarısız olursa, işlev dosya için varsayılan kodlamayı kullanır. Her iki durumda da, **fopen_s** sonra dosyayı salt yazılır erişimle yeniden açar. (Bu yalnızca **bir** mod için geçerlidir, **+** değil.)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

Karakter dizesi *modu* , aşağıdaki gibi, dosya için istenen erişim türünü belirtir.

|*modundaysa*|Access|
|-|-|
| **"r"** | Okuma için açılır. Dosya yoksa veya bulunamazsa, **fopen_s** çağrısı başarısız olur. |
| **"w"** | Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir. |
| **a** | Dosyanın sonuna (ekleme), yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaretini kaldırmadan açılır. Yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w +"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a +"** | Okuma ve ekleme için açılır. Ekleme işlemi, yeni veriler dosyaya yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma işlemi tamamlandıktan sonra EOF işaretleyicisi geri yüklenmez. Yoksa dosyayı oluşturur. |

Bir dosya **"a"** veya **"a +"** erişim türü kullanılarak açıldığında, dosyanın sonunda tüm yazma işlemleri oluşur. Dosya işaretçisi, [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak mevcut verilerin üzerine yazılmaması için herhangi bir yazma işlemi yapılmadan önce her zaman dosyanın sonuna geri taşınır.

**"A"** modu, dosyaya ekleme yapmadan önce EOF işaretçisini kaldırmaz. Ekleme gerçekleştirildikten sonra, MS-DOS türü komutu yalnızca özgün EOF işaretine kadar olan verileri gösterir ve dosyaya eklenen verileri etkilemez. **"A +"** modu, dosyaya ekleme yapmadan önce EOF işaretçisini kaldırır. Eklendikten sonra, MS-DOS türü komutu dosyadaki tüm verileri gösterir. **"A +"** modu, CTRL + Z EOF işaretleyicisi kullanılarak sonlandırılan bir akış dosyasına ekleme için gereklidir.

**"R +"** , **"w +"** veya **"a +"** erişim türü belirtildiğinde, hem okuma hem de yazma için izin verilir. (Dosyanın "Güncelleştir" için açık olduğu söylenir.) Ancak, okumayı yazmaya geçtiğinizde, giriş işleminin bir EOF işaretleyicisi ile karşılaşmanız gerekir. EOF yoksa, bir dosya konumlandırma işlevine aradaki bir çağrı kullanmanız gerekir. Dosya konumlandırma işlevleri **fsetpos**, [fseek](fseek-fseeki64.md)ve [geri sarma](rewind.md). Yazmaya geçiş yaparken, **fflush** veya dosya konumlandırma işlevine yönelik bir araya giren çağrı kullanmanız gerekir.

Yukarıdaki değerlere ek olarak, yeni satır karakterleri için çeviri modunu belirtmek üzere *moduna* aşağıdaki karakterler dahil edilebilir:

|*mod* değiştiricisi|Çeviri modu|
|-|-|
| **şı** | Metin (çevrilmiş) modunda aç. |
| **b** | İkili (çevrilmemiş) modda aç; satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin (çevrilmiş) modunda CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. **"A +"** ile okuma/yazma için açılan dosyalarda, **FOPEN_S** dosyanın sonunda CTRL + Z olup olmadığını denetler ve mümkünse onu kaldırır. Bu işlem, bir CTRL + Z ile biten bir dosya içinde gezinmek için [fseek](fseek-fseeki64.md) ve **fsöyleyin** kullanılması nedeniyle, [fseek](fseek-fseeki64.md) 'in dosyanın sonunda düzgün şekilde davranmasına neden olabilir.

Ayrıca, metin modunda, satır başı satır besleme birleşimleri, girişte tek satırlık akışlara çevrilir ve satır besleme karakterleri, çıkışdaki satır başı akış birleşimlerine çevrilir. Unicode Stream-g/ç işlevi metin modunda (varsayılan) çalışırken, kaynak veya hedef akışın çok baytlı karakterler dizisi olduğu varsayılır. Bu nedenle, Unicode akış girişi işlevleri çok baytlı karakterleri geniş karakterlere dönüştürür ( **mbtowc** işlevine yapılan bir çağrıda olduğu gibi). Aynı nedenden dolayı, Unicode akış çıkışı işlevleri çok baytlı karakterlere ( **wctomb** işlevine yapılan bir çağrıda olduğu gibi) çok fazla karakter dönüştürür.

**T** veya **b** *modunda*verilmezse, varsayılan çeviri modu, [_fmode](../../c-runtime-library/fmode.md)genel değişkeni tarafından tanımlanır. **T** veya **b** bağımsız değişkene öneki varsa, Işlev başarısız olur ve **null**değerini döndürür.

Unicode ve çok baytlı akışta metin ve ikili modlar kullanma hakkında daha fazla bilgi için bkz. metin ve ikili [mod dosyası g/](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ç ve [Unicode akış g/ç ve metin ve ikili modlar](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

|*mod* değiştiricisi|Davranış|
|-|-|
| **c** | Bir **fflush** veya **_flushall** çağrılırsa, dosya arabelleği içeriğinin doğrudan diske yazılması için ilişkili *dosya adı* için COMMIT bayrağını etkinleştirin. |
| **n** | İlişkili *dosya adı* için COMMIT bayrağını "No-COMMIT" olarak sıfırlayın. Bu varsayılandır. Ayrıca, programınızı COMMODE. OBJ ile bağlarsanız Genel tamamlama bayrağını da geçersiz kılar. Programınızı COMMODE ile açıkça bağmadığınız takdirde Genel tamamlama bayrağı varsayılan olarak "No-COMMIT" olur. OBJ (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)). |
| **N** | Dosyanın alt süreçler tarafından devralınamayacağını belirtir. |
| **S** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir. |
| **R** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim |
| **ŞI** | Geçici olarak bir dosya belirtir. Mümkünse, diske boşaltılmaz. |
| **D** | Geçici olarak bir dosya belirtir. Son dosya işaretçisi kapatıldığında silinir. |
| **CCS =** _kodlama_ | Bu dosya için kullanılacak kodlanan karakter kümesini ( **UTF-8**, **UTF-16LE**veya **UNICODE**) belirtir. ANSI kodlaması istiyorsanız belirtilmemiş olarak bırakın. |

**Fopen_s** ve [_fdopen](fdopen-wfdopen.md) 'da kullanılan *mod* dizesi için geçerli karakterler, aşağıdaki gibi, [_open](open-wopen.md) ve [_sopen](sopen-wsopen.md)içinde kullanılan *oflag* bağımsız değişkenlerine karşılık gelir.

|*Mod* dizesindeki karakterler|_Open/_sopen için eşdeğer *oflag* değeri|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_wronly** &#124; **_O_APPEND** (genellikle **_O_WRONLY** &#124; **_O_CREAT** &#124;* * _O_APPEND * *)|
|**a +**|**_O_rdwr** &#124; **_O_APPEND** (genellikle **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r +**|**_O_RDWR**|
|**anlatımı**|**_O_wronly** (genellikle **_O_WRONLY** &#124; **_O_CREAT** &#124;* * _O_TRUNC * *)|
|**w +**|**_O_rdwr** (genellikle **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**şı**|**_O_TEXT**|
|**c**|Yok.|
|**n**|Yok.|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**ŞI**|**_O_SHORTÖMÜRLÜ**|
|**D**|**_O_GEÇICIDIR**|
|**CCS = UNICODE**|**_O_WTEXT**|
|**ccs=UTF-8**|**_O_UTF8**|
|**CCS = UTF-16LE**|**_O_UTF16**|

**RB** modunu kullanıyorsanız, kodunuzun bağlantı noktası olması gerekmez ve dosyanın çok fazla okunması ve/veya ağ performansının önemli olması beklenmediğinden, bellek eşlemeli Win32 dosyaları da bir seçenek olabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fopen_s**|\<stdio. h >|
|**_wfopen_s**|\<stdio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

**C**, **n**ve **t** *modu* seçenekleri **fopen_s** ve [_fdopen](fdopen-wfdopen.md) için Microsoft uzantılarıdır ve ANSI taşınabilirliği istendiği yerde kullanılmamalıdır.

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
