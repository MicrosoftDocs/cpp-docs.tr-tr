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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 4b9fa6542996b2c16128a841e2611b85e995be2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346416"
---
# <a name="fopen-_wfopen"></a>fopen, _wfopen

Bir dosyayı açar. Ek parametre doğrulama ve iade hata kodları gerçekleştiren bu işlevlerin daha güvenli sürümleri kullanılabilir; [fopen_s, _wfopen_s](fopen-s-wfopen-s.md)bakın.

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

*Modu*<br/>
Etkin bir erişim.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri açık dosyaya bir işaretçi döndürür. Null işaretçi değeri bir hata gösterir. *Dosya adı* veya *mod* **NULL** veya boş bir dize ise, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklanan geçersiz parametre işleyicisini tetikler. Yürütme devam etmesine izin verilirse, bu işlevler **NULL** döndürdü ve **EINVAL** **için errno** ayarlayın.

Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Açıklamalar

**Fopen** işlevi *dosya adı*ile belirtilen dosyayı açar. Varsayılan olarak, dar bir *dosya adı* dizesi ANSI kod sayfası (CP_ACP) kullanılarak yorumlanır. Windows Masaüstü uygulamalarında bu, [SetFileApisToOEM](/windows/win32/api/fileapi/nf-fileapi-setfileapistooem) işlevini kullanarak OEM kod sayfası (CP_OEMCP) olarak değiştirilebilir. *Dosya adının* ANSI veya sistem varsayılan OEM kod sayfası kullanılarak yorumlanıp yorumlanmadığını belirlemek için [AreFileApisANSI](/windows/win32/api/fileapi/nf-fileapi-arefileapisansi) işlevini kullanabilirsiniz. **_wfopen** **fopen**geniş karakterli bir sürümüdür; **_wfopen** bağımsız değişkenler geniş karakterli dizeleridir. Aksi takdirde, **_wfopen** ve **fopen** aynı şekilde çalışır. Sadece **_wfopen** kullanmak, dosya akışında kullanılan kodlanmış karakter kümesini etkilemez.

**fopen** yürütme noktasında dosya sisteminde geçerli olan yolları kabul eder; **fopen,** kodu çalıştıran sistem yürütme sırasında paylaşıma veya eşlenen sürücüye erişebildiğim sürece eşlenen ağ sürücülerini içeren UNC yollarını ve yollarını kabul eder. **Fopen**için yollar inşa ettiğinizde, sürücülerin, yolların veya ağ paylaşımların yürütme ortamında kullanılabilir olduğundan emin olun. Bir yoltaki dizin ayırıcıları olarak ileri\\eğik çizgi (/) veya ters eğik çizgi () kullanabilirsiniz.

Dosyada ek işlemler gerçekleştirmeden önce işaretçinin NULL olup olmadığını görmek için her zaman iade değerini denetleyin. Bir hata oluşursa, genel değişken **errno** ayarlanır ve belirli hata bilgilerini elde etmek için kullanılabilir. Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="unicode-support"></a>Unicode Desteği

**fopen** Unicode dosya akışlarını destekler. Unicode dosyasını açmak için, **fopen**için istenen kodlamayı belirten bir **ccs** bayrağını aşağıdaki gibi geçirin.

> **FILE \*fp = fopen("newfile.txt", "rt+, ccs=**_kodlama_**");**

*Kodlamaizin* izin verilen değerleri **UNICODE**, **UTF-8**ve **UTF-16LE'dir.**

Unicode modunda bir dosya açıldığında, giriş işlevleri dosyadan okunan verileri **wchar_t**türü olarak depolanan UTF-16 verilerine çevirir. Unicode modunda açılan bir dosyaya yazılan **işlevler,** wchar_t türü olarak depolanan UTF-16 verileri içeren arabellekleri bekler. Dosya UTF-8 olarak kodlanırsa, UTF-16 verileri yazıldığında UTF-8'e çevrilir ve dosyanın UTF-8 kodlanmış içeriği okunduğunda UTF-16'ya çevrilir. Unicode modunda tek sayıda bayt okuma veya yazma girişimi [parametre doğrulama](../../c-runtime-library/parameter-validation.md) hatasına neden olur. Programınızda UTF-8 olarak depolanan verileri okumak veya yazmak için Unicode modu yerine metin veya ikili dosya modu kullanın. Gerekli kodlama çevirisiden siz sorumlusunuz.

Dosya zaten varsa ve okumak veya ekolarak açılmak üzere açılmışsa, Dosyada varsa Byte Order Mark (BOM) kodlamayı belirler. BOM **kodlaması, ccs** bayrağı tarafından belirtilen kodlamadan önce gelir. **Ccs** kodlaması yalnızca ürün bir ürün dürbonu olmadığında veya dosya yeni bir dosya olduğunda kullanılır.

> [!NOTE]
> BOM algılama yalnızca Unicode modunda açılan dosyalar için geçerlidir (diğer bir deyişle **ccs** bayrağını geçirerek).

Aşağıdaki tablo, dosyadaki **fopen** ve Byte Order Marks için verilen çeşitli **ccs** bayrakları için kullanılan modları özetler.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>CCS Bayrak ve BOM'a Göre Kullanılan Kodlamalar

|ccs bayrağı|Hiçbir BOM (veya yeni dosya)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**Unicode**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode modunda yazılmak üzere açılan dosyaların kendilerine otomatik olarak yazılmış bir ÜRÜN KODU vardır.

*Mod* **"a, ccs=**_kodlama_**"** ise, **fopen** önce hem okuma hem de yazma erişimini kullanarak dosyayı açmaya çalışır. Bu başarılı olursa, işlev dosya için kodlama belirlemek için ÜRÜN REM okur; bu başarısız olursa, işlev dosya için varsayılan kodlama kullanır. Her iki durumda da, **fopen** daha sonra yalnızca yazma erişimini kullanarak dosyayı yeniden açar. (Bu yalnızca **"a"** modu için geçerlidir, **"a+"** modu için değil.)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen**|**Fopen**|**Fopen**|**_wfopen**|

Karakter dize *modu,* dosya için istenen erişim türünü aşağıdaki gibi belirtir.

|*Modu*|Erişim|
|-|-|
| **"r"** | Okumak için açılır. Dosya yoksa veya bulunamıyorsa, **fopen** çağrısı başarısız olur. |
| **"w"** | Yazmak için boş bir dosya yı açar. Verilen dosya varsa, içeriği yok edilir. |
| **"a"** | Dosyaya yeni veriler yazılmadan önce dosya sonu (EOF) işaretçisini kaldırmadan dosyanın sonunda (ek) yazıiçin açılır. Yoksa dosyayı oluşturur. |
| **"r+"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w+"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a+"** | Okuma ve ekolarak açılır. Ek işlem, dosyaya yeni veriler yazılmadan önce EOF işaretçisinin kaldırılmasını içerir. EOF işaretçisi, yazma tamamlandıktan sonra geri yüklenmez. Yoksa dosyayı oluşturur. |

Bir dosya **"a"** erişim türü veya **"a+"** erişim türü kullanılarak açıldığında, tüm yazma işlemleri dosyanın sonunda gerçekleşir. Dosya işaretçisi [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak herhangi bir yazma işlemi gerçekleştirilmeden önce her zaman dosyanın sonuna geri taşınır. Bu nedenle, varolan veriler üzerine yazılamaz.

**"a"** modu, dosyaya eklenene kadar EOF işaretçisini kaldırmaz. Ek olay dan sonra, MS-DOS TYPE komutu yalnızca özgün EOF işaretçisine kadar olan verileri gösterir ve dosyaya eklenen verileri göstermez. Dosyaya ekolarak **önce "a+"** modu EOF işaretçisini kaldırır. Ekledikten sonra, MS-DOS TYPE komutu dosyadaki tüm verileri gösterir. CTRL+Z EOF işaretçisi ile sonlandırılan bir akış dosyasına ekolarak **"a+"** modu gereklidir.

**"r+"**, **"w+"** veya **"a+"** erişim türü belirtildiğinde, hem okuma hem de yazma etkindir (dosyanın "güncelleştirme" için açık olduğu söylenir). Ancak, okumadan yazmaya geçtiğiniz zaman, giriş işlemi bir EOF işaretçisi ile karşılaşmalıdır. EOF yoksa, dosya konumlandırma işlevine ara veren bir çağrı kullanmanız gerekir. Dosya konumlandırma işlevleri **fsetpos**, [fseek](fseek-fseeki64.md), ve [geri sarma](rewind.md). Yazmadan okumaya geçtiğiniz zaman, **fflush** veya dosya konumlandırma işlevi için araya giren bir çağrı kullanmanız gerekir.

Önceki değerlere ek olarak, aşağıdaki karakterler yeni satır karakterleri için çeviri modunu belirtmek için *moda* eklenebilir.

|*mod* değiştirici|Çeviri modu|
|-|-|
| **T** | Metin (çevrilmiş) modunda açın. |
| **B** | İkili (çevrilmemiş) modda açık; satır döndürme ve satır besleme karakterlerini içeren çeviriler bastırılır. |

Metin modunda CTRL+Z girişte EOF karakteri olarak yorumlanır. **"a+"** kullanılarak okumak/yazmak için açılan dosyalarda, dosyanın sonunda ctrl+Z için **fopen** denetler ve mümkünse kaldırır. CtRL+Z ile biten bir dosya içinde hareket etmek için [fseek](fseek-fseeki64.md) ve **ftell'i** [kullanmak, fseek'in](fseek-fseeki64.md) dosyanın sonuna yakın yanlış hareket etmesini niçin yapabilir.

Metin modunda, satır satır beslemesi birleşimleri girişte tek satır beslemelerine, satır besleme karakterleri ise çıkışta satır satır beslemesi birleşimlerine çevrilir. Unicode akışı-I/Ç işlevi metin modunda (varsayılan) çalıştığında, kaynak veya hedef akışı çok bayt karakter dizisi olarak kabul edilir. Bu nedenle, Unicode akış giriş işlevleri çok bayt karakterleri geniş karakterlere dönüştürür **(mbtowc** işlevine bir çağrı gibi). Aynı nedenle, Unicode akış çıkışı işlevleri geniş karakterleri çok bayt karakterlere dönüştürür **(wctomb** işlevine bir çağrı gibi).

**T** veya **b** *modunda*verilmiyorsa, varsayılan çeviri modu _fmode genel [değişken](../../c-runtime-library/fmode.md)tarafından tanımlanır. **T** veya **b** bağımsız değişkene önceden belirlenmişse, işlev başarısız olur ve **NULL**döndürür.

Unicode ve multibayt akış-I/O metin ve ikili modların nasıl kullanılacağı hakkında daha fazla bilgi için Metin [ve İkili Modlar'daki Metin ve İkili Moddosyası I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [Unicode Stream I/O'ya](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)bakın.

Aşağıdaki seçenekler, ek davranışlar belirtmek için *moda* eklenebilir.

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

**fopen** ve **_fdopen** kullanılan *mod* dizeiçin geçerli karakterler [_open](open-wopen.md) ve [_sopen](sopen-wsopen.md)kullanılan *oflag* bağımsız değişkenleri karşılık , aşağıdaki gibi.

|*Mod* dizesindeki karakterler|Açık/\_açık \_için eşdeğer *oflag* değeri|
|-------------------------------|----------------------------------------------------|
|**A**|**\_O\_WRONLY** &#124; ** \_O\_APPEND** (genellikle ** \_O\_WRONLY** &#124; ** \_O\_CREAT** &#124; ** \_O\_APPEND)**|
|**a+**|**\_O\_RDWR** &#124; ** \_O\_APPEND** (genellikle ** \_O\_RDWR** &#124; ** \_O\_APPEND** &#124; ** \_O\_CREAT)**|
|**R**|**\_O\_RDONLY**|
|**r+**|**\_O\_RDWR**|
|**W**|**\_O\_WRONLY** (genellikle ** \_\_O WRONLY** &#124; ** \_\_O CREAT** &#124; ** \_O\_TRUNC)**|
|**w+**|**\_O\_RDWR** (genellikle ** \_\_O RDWR** &#124; ** \_\_O CREAT** &#124; ** \_O\_TRUNC)**|
|**B**|**\_O\_İkİlİ**|
|**T**|**\_O\_TEKSTİl**|
|**C**|None|
|**n**|None|
|**S**|**\_O\_ARDI**|
|**R**|**\_O\_RASGELE**|
|**T**|**\_O\_KISA ÖMÜRLÜ**|
|**D**|**\_O\_GEÇİcİ**|
|**ccs=UNICODE**|**\_O\_WTEXT**|
|**ccs=UTF-8**|**\_O\_UTF8**|
|**ccs=UTF-16LE**|**\_O\_UTF16**|

**RB** modunu kullanıyorsanız, kodunuzu taşımanız gerekmez ve büyük bir dosyanın çoğunu okumayı düşünüyorsanız veya ağ performansı yla ilgili endişeleriniz yoksa, bellek eşlenmiş Win32 dosyalarını bir seçenek olarak kullanıp kullanmamayı da düşünebilirsiniz.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Fopen**|\<stdio.h>|
|**_wfopen**|\<stdio.h> \<veya wchar.h>|

**_wfopen** bir Microsoft uzantısıdır. Uyumluluk hakkında daha fazla bilgi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

**C**, **n**, **t**, S , **R**, **T**ve **D** *mod seçenekleri* **fopen** ve **_fdopen** için Microsoft uzantılarıdır ve ANSI taşınabilirliğinin istendiği yerlerde kullanılmamalıdır. **R**

## <a name="example-1"></a>Örnek 1

Aşağıdaki program iki dosya açar.  İlk dosyayı kapatmak için **fclose** kullanır ve kalan tüm dosyaları kapatmak için **_fcloseall.**

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

Aşağıdaki program, Unicode kodlaması olan metin modunda bir dosya oluşturur (veya varsa bir dosyanın üzerine yazar.  Daha sonra dosyaya iki dizeleri yazar ve dosyayı kapatır. Çıktı, çıkış bölümünden verileri içeren _wfopen_test.xml adlı bir dosyadır.

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
