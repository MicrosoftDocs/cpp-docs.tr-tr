---
title: fopen, _wfopen
ms.date: 4/2/2020
api_name:
- _wfopen
- fopen
- _o__wfopen
- _o_fopen
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
- fopen
- _wfopen
- _tfopen
- corecrt_wstdio/_wfopen
- stdio/fopen
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
ms.openlocfilehash: d468226028928e3edfe67cc7f9b9eec06e06bd56
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914886"
---
# <a name="fopen-_wfopen"></a>fopen, _wfopen

Bir dosya açar. Ek parametre doğrulama ve dönüş hata kodları gerçekleştiren bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [fopen_s, _wfopen_s](fopen-s-wfopen-s.md).

## <a name="syntax"></a>Sözdizimi

```C
FILE *fopen(
   const char *filename,
   const char *mode
);
FILE *_wfopen(
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Dosya adı.

*modundaysa*<br/>
Etkin erişim türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, Açık dosyaya bir işaretçi döndürür. Null işaretçi değeri bir hatayı gösterir. *Dosya adı* veya *mod* **null** ya da boş bir dize ise, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklanan geçersiz parametre işleyicisini tetikler. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **null** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Fopen** işlevi, *filename*tarafından belirtilen dosyayı açar. Varsayılan olarak, bir dar *dosya adı* dizesi ANSI kod sayfası (CP_ACP) kullanılarak yorumlanır. Windows masaüstü uygulamalarında, bu, [SetFileApisToOEM](/windows/win32/api/fileapi/nf-fileapi-setfileapistooem) IşLEVI kullanılarak OEM kod sayfasına (CP_OEMCP) değiştirilebilir. *Dosya ADıNıN* ANSI veya SISTEM varsayılan OEM kod sayfası kullanılarak yorumlanıp yorumlanmadığını anlamak için [AreFileApisANSI](/windows/win32/api/fileapi/nf-fileapi-arefileapisansi) işlevini kullanabilirsiniz. **_wfopen** , **fopen**'un geniş karakterli bir sürümüdür; **_wfopen** bağımsız değişkenler geniş karakterli dizelerdir. Aksi takdirde, **_wfopen** ve **fopen** aynı şekilde davranır. Yalnızca **_wfopen** kullanmak dosya akışında kullanılan kodlanmış karakter kümesini etkilemez.

**fopen** , yürütme noktasındaki dosya sisteminde geçerli olan yolları kabul eder; **fopen** , kodu yürüten sistem, yürütme sırasında paylaşıma veya eşlenmiş sürücüye erişime sahip olduğu sürece, eşlenen ağ SÜRÜCÜLERIYLE ilgili UNC yollarını ve yollarını kabul eder. **Fopen**için yollar oluşturduğunuzda, sürücülerin, yolların veya ağ paylaşımlarının yürütme ortamında kullanılabildiğinden emin olun. Bir yoldaki Dizin ayırıcıları olarak eğik çizgi (/) veya ters\\eğik çizgi () kullanabilirsiniz.

Dosya üzerinde herhangi bir ek işlem gerçekleştirmeden önce işaretçinin NULL olup olmadığını görmek için dönüş değerini her zaman denetleyin. Bir hata oluşursa, **errno** genel değişkeni ayarlanır ve belirli hata bilgilerini elde etmek için kullanılabilir. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="unicode-support"></a>Unicode Desteği

**fopen** Unicode dosya akışlarını destekler. Bir Unicode dosyası açmak için, aşağıdaki gibi, **fopen**için istenen kodlamayı belirten bir **CCS** bayrağı geçirin.

> **Dosya \*FP = fopen ("yenidosya. txt", "RT +, CCS =**_Encoding_**");**

*Kodlama* için izin verilen değerler **UNICODE**, **UTF-8**ve **UTF-16LE**' dir.

Bir dosya Unicode modunda açıldığında, giriş işlevleri dosyadan okunan verileri, **wchar_t**tür olarak depolanan UTF-16 verilerine çevirir. Unicode modunda açılan bir dosyaya yazan işlevler, türü **wchar_t**olarak depolanan UTF-16 verilerini içeren arabellekleri bekler. Dosya UTF-8 olarak kodlanmışsa, UTF-16 verileri yazıldığında UTF-8 ' e çevrilir ve dosyanın UTF-8 kodlu içeriği okunarak UTF-16 ' a çevrilir. Unicode modunda tek sayıda bayt okuma veya yazma girişimi bir [parametre doğrulama](../../c-runtime-library/parameter-validation.md) hatasına neden olur. Programınızda depolanan verileri UTF-8 olarak okumak veya yazmak için Unicode modu yerine bir metin veya ikili dosya modu kullanın. Gerekli tüm kodlama çevirilerinden siz sorumlusunuz.

Dosya zaten varsa ve okuma ya da ekleme için açılırsa, bayt sırası Işareti (BOM) dosyada varsa, kodlamayı belirler. BOM kodlaması, **CCS** bayrağıyla belirtilen kodlamaya göre önceliklidir. **CCS** kodlaması yalnızca bir BOM yoksa veya dosya yeni bir dosya olduğunda kullanılır.

> [!NOTE]
> BOM algılaması yalnızca Unicode modunda açılan dosyalar için geçerlidir (diğer bir deyişle, **CCS** bayrağını geçirerek).

Aşağıdaki tabloda, dosyadaki **fopen** ve byte sırası işaretlerine verilen çeşitli **CCS** bayrakları için kullanılan modlar özetlenmektedir.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>CCS bayrak ve BOM temelinde kullanılan kodlamalar

|CCS bayrağı|BOM (veya yeni dosya) yok|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**KODLAMALARı**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode modunda yazmak için açılan dosyalarda otomatik olarak yazılmış bir BOM vardır.

*Mod* **"a, CCS =**_Encoding_**"** ise, **fopen** önce dosyayı hem okuma hem de yazma erişimini kullanarak açmaya çalışır. Bu başarılı olursa, işlev, dosyanın kodlamasını belirlemede ürün reçetesini okur; Bu başarısız olursa, işlev dosya için varsayılan kodlamayı kullanır. Her iki durumda da **fopen** , dosyayı salt yazılır erişim kullanarak yeniden açar. (Bu yalnızca "a **"** modu için geçerlidir, **"a +"** modunda değildir.)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen**|**fopen**|**fopen**|**_wfopen**|

Karakter dizesi *modu* , aşağıdaki gibi, dosya için istenen erişim türünü belirtir.

|*modundaysa*|Erişim|
|-|-|
| **sağ** | Okuma için açılır. Dosya yoksa veya bulunamazsa, **fopen** çağrısı başarısız olur. |
| **anlatımı** | Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir. |
| **a** | Dosyanın sonuna (ekleme), yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaretini kaldırmadan açılır. Yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w +"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a +"** | Okuma ve ekleme için açılır. Ekleme işlemi, yeni veriler dosyaya yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma işlemi tamamlandıktan sonra EOF işaretleyicisi geri yüklenmez. Yoksa dosyayı oluşturur. |

**"A"** erişim türü veya **"a +"** erişim türü kullanılarak bir dosya açıldığında, dosyanın sonunda tüm yazma işlemleri gerçekleşir. Dosya işaretçisi, [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak herhangi bir yazma işlemi yapılmadan önce her zaman dosyanın sonuna geri taşınır. Bu nedenle, mevcut verilerin üzerine yazılamaz.

**"A"** modu, dosyaya EKLENMEDEN önce EOF işaretçisini kaldırmaz. Ekleme gerçekleştirildikten sonra, MS-DOS türü komutu yalnızca özgün EOF işaretine kadar olan verileri gösterir ve dosyaya eklenen verileri etkilemez. Dosyayı eklemeden önce, **"a +"** modu EOF işaretçisini kaldırır. Eklendikten sonra, MS-DOS türü komutu dosyadaki tüm verileri gösterir. **"A +"** modu, CTRL + Z EOF işaretleyicisi ile sonlandırılan bir akış dosyasına ekleme için gereklidir.

**"R +"**, **"w +"** veya **"a +"** erişim türü belirtildiğinde, hem okuma hem de yazma etkinleştirilir (dosya "güncelleştirme" için açık olur). Ancak, okumayı yazmaya geçtiğinizde, giriş işleminin bir EOF işaretleyicisi ile karşılaşmanız gerekir. EOF yoksa, bir dosya konumlandırma işlevine aradaki bir çağrı kullanmanız gerekir. Dosya konumlandırma işlevleri **fsetpos**, [fseek](fseek-fseeki64.md)ve [geri sarma](rewind.md). Yazmaya geçiş yaparken, **fflush** veya bir dosya konumlandırma işlevine yönelik bir araya giren çağrı kullanmanız gerekir.

Önceki değerlere ek olarak, yeni satır karakterleri için çeviri modunu belirtmek üzere aşağıdaki karakterler *moda* eklenebilir.

|*mod* değiştiricisi|Çeviri modu|
|-|-|
| **şı** | Metin (çevrilmiş) modunda aç. |
| **kenarı** | İkili (çevrilmemiş) modda aç; satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin modunda CTRL + Z, girişte bir EOF karakteri olarak yorumlanır. **"A +"** kullanılarak okuma/yazma için açılan dosyalarda, **fopen** , dosyanın sonunda bir CTRL + Z olup olmadığını denetler ve mümkünse onu kaldırır. Bu işlem yapılır çünkü bu, CTRL + Z ile biten bir dosya içinde gezinmek için [fseek](fseek-fseeki64.md) ve **fsöyleyin** kullanılması, [fseek](fseek-fseeki64.md) 'in dosyanın sonuna doğru şekilde davranmasına neden olabilir.

Metin modunda, satır başı satır besleme birleşimleri girişte tek satırlık akışlara çevrilir ve satır besleme karakterleri, çıkışdaki satır başı akış birleşimlerine çevrilir. Unicode Stream-g/ç işlevi metin modunda (varsayılan) çalışırken, kaynak veya hedef akışın çok baytlı karakterler dizisi olduğu varsayılır. Bu nedenle, Unicode akış girişi işlevleri çok baytlı karakterleri geniş karakterlere dönüştürür ( **mbtowc** işlevine yapılan bir çağrıda olduğu gibi). Aynı nedenden dolayı, Unicode akış çıkışı işlevleri çok baytlı karakterlere ( **wctomb** işlevine yapılan bir çağrıda olduğu gibi) çok fazla karakter dönüştürür.

**T** veya **b** *modda*verilmezse, varsayılan çeviri modu [_fmode](../../c-runtime-library/fmode.md)genel değişken tarafından tanımlanır. **T** veya **b** bağımsız değişkene öneki varsa, Işlev başarısız olur ve **null**değerini döndürür.

Unicode ve çok baytlı akış-g/ç 'de metin ve ikili modların nasıl kullanılacağı hakkında daha fazla bilgi için bkz. metin ve [Ikili mod dosya g/](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ç ve [Unicode akış g/ç ve metin ve ikili modlar](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

Ek davranışları belirtmek için aşağıdaki seçenekler *moda* eklenebilir.

|*mod* değiştiricisi|Davranış|
|-|-|
| **,** | Bir **fflush** veya **_flushall** çağrılırsa, dosya arabelleği içeriğinin doğrudan diske yazılması için ilişkili *dosya adı* için COMMIT bayrağını etkinleştirin. |
| **No** | İlişkili *dosya adı* için COMMIT bayrağını "No-COMMIT" olarak sıfırlayın. Bu varsayılandır. Ayrıca, programınızı COMMODE. OBJ ile bağlarsanız Genel tamamlama bayrağını da geçersiz kılar. Programınızı COMMODE ile açıkça bağmadığınız takdirde Genel tamamlama bayrağı varsayılan olarak "No-COMMIT" olur. OBJ (bkz. [bağlantı seçenekleri](../../c-runtime-library/link-options.md)). |
| **N** | Dosyanın alt süreçler tarafından devralınamayacağını belirtir. |
| **S** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir. |
| **R** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim |
| **T** | Geçici olarak bir dosya belirtir. Mümkünse, diske boşaltılmaz. |
| **TID** | Geçici olarak bir dosya belirtir. Son dosya işaretçisi kapatıldığında silinir. |
| **CCS =**_kodlama_ | Bu dosya için kullanılacak kodlanan karakter kümesini ( **UTF-8**, **UTF-16LE**veya **UNICODE**) belirtir. ANSI kodlaması istiyorsanız belirtilmemiş olarak bırakın. |

**Fopen** ve **_fdopen** için kullanılan *mod* dizesi için geçerli karakterler aşağıdaki gibi [_open](open-wopen.md) ve [_sopen](sopen-wsopen.md)kullanılan *öteleme* bağımsız değişkenlerine karşılık gelir.

|*Mod* dizesindeki karakterler|Açık/\_saçık için \_eşdeğer *oflag* değeri|
|-------------------------------|----------------------------------------------------|
|**a**|**\_O\_yalnızca** o &#124; ** \_o\_ekleme** (genellikle ** \_o\_** &#124; ** \_o\_** ** \_&#124;\_o**)|
|**a +**|**\_O\_rdwr** &#124; ** \_o\_Append** (genellikle ** \_o\_rdwr** &#124; ** \_o\_Append** &#124; ** \_o\_creat** )|
|**sağ**|**\_O\_yalnızca RD**|
|**r +**|**\_O\_rdwr**|
|**anlatımı**|**\_Yalnızca\_wronly** (genellikle ** \_o\_** &#124; ** \_o\_creat** &#124; ** \_\_o TRUNC**)|
|**w +**|**\_O\_rdwr** (genellikle ** \_o\_, rdwr** &#124; ** \_\_o creat** &#124; ** \_o\_TRUNC**)|
|**kenarı**|**\_O\_ikili**|
|**şı**|**\_O\_metni**|
|**,**|Yok|
|**No**|Yok|
|**S**|**\_O\_sıralı**|
|**R**|**\_O\_rastgele**|
|**T**|**\_O\_shortömürlü**|
|**TID**|**\_O\_geçici**|
|**CCS = UNICODE**|**\_O\_wtext**|
|**CCS = UTF-8**|**\_O\_UTF8**|
|**CCS = UTF-16LE**|**\_O\_UTF16**|

**RB** modunu kullanıyorsanız, kodunuzun bağlantı noktası oluşturmanız gerekmez ve büyük bir dosyanın çoğunu okumayı veya ağ performansından endişe etmeyi düşünüyorsanız, bellek eşlemeli Win32 dosyalarını bir seçenek olarak kullanıp kullanmayacağınızı de düşünebilirsiniz.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fopen**|\<stdio. h>|
|**_wfopen**|\<stdio. h> veya \<wchar. h>|

**_wfopen** bir Microsoft uzantısıdır. Uyumluluk hakkında daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**C**, **n**, **t**, **S**, **R**, **t**ve **D** *modu* seçenekleri, **fopen** ve **_fdopen** için Microsoft uzantılarıdır ve ANSI taşınabilirliği istendiği yerde kullanılmamalıdır.

## <a name="example-1"></a>Örnek 1

Aşağıdaki program iki dosya açar.  İlk dosyayı kapatmak için **fclose** kullanır ve kalan tüm dosyaları kapatmak için **_fcloseall** .

```C
// crt_fopen.c
// compile with: /W3
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   int numclosed;

   // Open for read (will fail if file "crt_fopen.c" does not exist)
   if( (stream  = fopen( "crt_fopen.c", "r" )) == NULL ) // C4996
   // Note: fopen is deprecated; consider using fopen_s instead
      printf( "The file 'crt_fopen.c' was not opened\n" );
   else
      printf( "The file 'crt_fopen.c' was opened\n" );

   // Open for write
   if( (stream2 = fopen( "data2", "w+" )) == NULL ) // C4996
      printf( "The file 'data2' was not opened\n" );
   else
      printf( "The file 'data2' was opened\n" );

   // Close stream if it is not NULL
   if( stream)
   {
      if ( fclose( stream ) )
      {
         printf( "The file 'crt_fopen.c' was not closed\n" );
      }
   }

   // All other files are closed:
   numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="example-2"></a>Örnek 2

Aşağıdaki program, Unicode kodlaması olan metin modundaki bir dosya (veya varsa üzerine yazar) oluşturur.  Daha sonra dosyaya iki dize yazar ve dosyayı kapatır. Çıktı, çıkış bölümündeki verileri içeren _wfopen_test. xml adlı bir dosyadır.

```C
// crt__wfopen.c
// compile with: /W3
// This program creates a file (or overwrites one if
// it exists), in text mode using Unicode encoding.
// It then writes two strings into the file
// and then closes the file.

#include <stdio.h>
#include <stddef.h>
#include <stdlib.h>
#include <wchar.h>

#define BUFFER_SIZE 50

int main(int argc, char** argv)
{
    wchar_t str[BUFFER_SIZE];
    size_t  strSize;
    FILE*   fileHandle;

    // Create an the xml file in text and Unicode encoding mode.
    if ((fileHandle = _wfopen( L"_wfopen_test.xml",L"wt+,ccs=UNICODE")) == NULL) // C4996
    // Note: _wfopen is deprecated; consider using _wfopen_s instead
    {
        wprintf(L"_wfopen failed!\n");
        return(0);
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"<xmlTag>\n");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"</xmlTag>");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Close the file.
    if (fclose(fileHandle))
    {
        wprintf(L"fclose failed!\n");
    }
    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
