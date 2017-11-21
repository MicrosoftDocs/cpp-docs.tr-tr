---
title: fopen, _wfopen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfopen
- fopen
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
- fopen
- _wfopen
- _tfopen
- corecrt_wstdio/_wfopen
- stdio/fopen
dev_langs: C++
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
caps.latest.revision: "56"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c5a81cdcba10d65c496a946fb8847fdb09b1ff70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fopen-wfopen"></a>fopen, _wfopen
Bir dosyayı açar. Ek parametre doğrulama ve return hata kodları gerçekleştirmek bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [fopen_s, _wfopen_s](../../c-runtime-library/reference/fopen-s-wfopen-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
FILE *fopen(   
   const char *filename,  
   const char *mode   
);  
FILE *_wfopen(   
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Dosya adı.  
  
 `mode`  
 Etkin bir erişim türü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri, açık olan dosyaya bir işaretçi döndürür. Null işaretçinin değeri bir hata gösterir. Varsa `filename` veya `mode` olan `NULL` veya boş bir dize bu işlevler açıklanan geçersiz parametre işleyicisi tetikleyicisi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `NULL` ve `errno` için `EINVAL`.  
  
 Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `fopen` İşlev tarafından belirtilen dosyayı açar `filename`. Varsayılan olarak, bir dar `filename` dize ANSI kod sayfası (CP_ACP) kullanarak yorumlanır. Windows masaüstü uygulamalarında bu OEM codepage (CP_OEMCP) kullanarak değiştirilebilir [SetFileApisToOEM](https://msdn.microsoft.com/library/windows/desktop/aa365534\(v=vs.85\).aspx) işlevi. Kullanabileceğiniz [AreFileApisANSI](https://msdn.microsoft.com/library/windows/desktop/aa363781\(v=vs.85\).aspx) belirlemek için işlev olup olmadığını `filename` ANSI ya da sistem varsayılan OEM kod sayfası kullanılarak yorumlanır. `_wfopen`bir joker karakter sürümü `fopen`; bağımsız değişkenleri `_wfopen` joker karakter dizelerdir. Aksi takdirde, `_wfopen` ve `fopen` aynı şekilde davranır. Yalnızca kullanmak `_wfopen` dosya akışı kullanılan kodlanmış karakter kümesi etkilemez.  
  
 `fopen`Geçerli yürütme noktasında dosya sistemi yolları kabul eder; `fopen` UNC yollarını ve ilgili yolları kodu yürütür sistem paylaşımına erişimi olduğu sürece eşlenen ağ sürücülerini veya sürücü, yürütme sırasında eşlenmiş kabul eder. İçin yollar oluşturmak zaman `fopen`, sürücüler, yolları veya ağ paylaşımlarına yürütme ortamında kullanılabilir olacağından emin olun. Eğik çizgi (/) veya ters eğik çizgi kullanabilirsiniz (\\) yolu dizin ayırıcı olarak.  
  
 Her zaman dosyanın herhangi bir ek işlemi gerçekleştirmeden önce işaretçisi NULL olup olmadığını görmek için dönüş değerini denetleyin. Bir hata oluşursa, genel değişkeni `errno` ayarlanır ve belirli hata bilgilerini elde etmek için kullanılabilir. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="unicode-support"></a>Unicode Desteği  
 `fopen`Unicode dosya akışları destekler. Geçişi bir Unicode dosyası açmak için bir `ccs` için istenen kodlamayı belirten bayrak `fopen`aşağıdaki gibi.  
  
 `FILE *fp = fopen("newfile.txt", "rt+, ccs=encoding");`  
  
 İzin verilen değerler, `encoding` olan `UNICODE`, `UTF-8`, ve `UTF-16LE`.  
  
 Unicode modda bir dosya açıldığında, giriş işlevleri UTF-16 veri türü olarak depolanan dosyadan okunan veriler çevir `wchar_t`. Unicode modunda açılmış bir dosyaya yazma işlevleri beklediğiniz UTF-16 veri türü olarak depolanan içeren arabellekleri `wchar_t`. Dosyanın UTF-8 olarak kodlanmıştır, sonra UTF-16 verileri UTF-8 yazılması ve onu okunduğunda dosyanın içeriğini UTF-8 kodlu UTF-16 çevrilir çevrilir. Okuma veya tek sayıda bayt Unicode modu nedenler yazma girişiminde bir [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) hata. Okumak veya programınız UTF-8 olarak depolanan veri yazmak için bir metin veya ikili dosya modu yerine Unicode modunu kullanın. Tüm gerekli kodlama çeviri sorumlu.  
  
 Dosya zaten var ve okuma veya ekleme açıldığında, bayt sırası işareti (dosyasında sunmak, BOM), kodlama belirler. Ürün reçetesi kodlama tarafından belirtilen kodlama üzerinden önceliklidir `ccs` bayrağı. `ccs` Kodlaması yalnızca kullanılan hiçbir BOM mevcut olduğunda veya dosyanın yeni bir dosyadır.  
  
> [!NOTE]
>  Ürün reçetesi algılama yalnızca uygulanır Unicode modunda açılan dosyaları (diğer bir deyişle, göre geçirme `ccs` bayrağı).  
  
 Aşağıdaki tabloda çeşitli için kullanılan modları özetler `ccs` verilen bayrakları `fopen` ve bayt sırası işaretleri dosyasında.  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Kodlamalar kullanılan temel alarak bayrağı ve ürün reçetesi ccs  
  
|`ccs`bayrağı|Hiçbir ürün reçetesi (veya yeni dosyası)|ÜRÜN REÇETESİ: UTF-8|ÜRÜN REÇETESİ: UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 Unicode modda yazmak için açılan dosyaları otomatik olarak yazılmış bir ürün reçetesi vardır.  
  
 Varsa `mode` olan "`a, ccs=<encoding>`", `fopen` ilk okuma ve yazma erişimi kullanarak dosyayı açmaya çalışır. Bu işlem başarılı olursa işlevi için dosya kodlamasını belirlemek için ürün reçetesi okur; Bu başarısız olursa, dosya için varsayılan kodlamayı işlevini kullanır. Her iki durumda da `fopen` sonra dosya salt yazılır erişimi kullanarak yeniden açılır. (Bu uygulandığı `a` modu değil yalnızca `a+` modu.)  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen`|`fopen`|`fopen`|`_wfopen`|  
  
 Karakter dizesi `mode` dosya için aşağıdaki gibi istenen erişim türünü belirtir.  
  
 `"r"`  
 Okuma için açılır. Dosya yok veya bulunamadı, `fopen` çağrısı başarısız olur.  
  
 `"w"`  
 Boş bir dosya yazma için açılır. Verilen dosya varsa, içeriği yok.  
  
 `"a"`  
 Yazma (yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaret kaldırmadan ekleyerek) dosya sonunda açar. Henüz yoksa dosyası oluşturur.  
  
 `"r+"`  
 Hem okuma ve yazma için açılır. Dosyanın mevcut olması gerekir.  
  
 `"w+"`  
 Hem okumak ve yazmak için boş bir dosya açar. Dosya varsa, içeriği yok.  
  
 `"a+"`  
 Okuma ve sonuna ekleme için açılır. Yeni veri dosyasına yazılmadan önce ekleme işlemi EOF işaret kaldırılmasını içerir. EOF işaret yazma tamamlandıktan sonra geri yüklenmez. Henüz yoksa dosyası oluşturur.  
  
 Ne zaman bir dosya açıldığında kullanarak `"a"` erişim türüne veya `"a+"` erişim türüne, tüm işlemleri ortaya dosyanın sonunda yazma. Dosya işaretçisini kullanarak konumlandırılmasına `fseek` veya `rewind`, ancak herhangi bir işlemi gerçekleştirildi yazmadan önce her zaman geri dosyanın sonuna taşınır. Bu nedenle, varolan verilerin üzerine yazılamıyor.  
  
 `"a"` Modu dosyasına ekler önce EOF işaret kaldırmaz. Sonuna ekleme gerçekleştikten sonra MS-DOS türü komutu yalnızca özgün EOF işaret kadar veri ve dosyanın sonuna hiçbir veri gösterir. Dosyaya ekler önce `"a+"` modunu EOF işaret kaldırabilirsiniz. Sonuna ekleme sonra MS-DOS türü komut dosyasında tüm verileri gösterir. `"a+"` Modu CTRL + Z EOF işaretçisi ile sonlandırılan bir akış dosyasına ekleme için gereklidir.  
  
 Zaman `"r+"`, `"w+"`, veya `"a+"` erişim türü belirtildi, hem okuma ve yazma etkin (dosya "güncelleştirmesi" açık olarak kabul edilir). Ancak, yazma için veri okuma geçiş yaptığınızda, giriş işlemi EOF işaret karşılaştığınız gerekir. Hiçbir EOF ise, müdahalede bulunan bir çağrı işlevi konumlandırma dosyaya kullanmanız gerekir. Dosya konumlandırma işlevlerdir `fsetpos`, `fseek`, ve `rewind`. Okunurken yazma geçiş yaptığınızda, müdahalede bulunan bir arama ya da kullanmalıdır `fflush` veya işlevi konumlandırma dosyası.  
  
 Önceki değerlerin yanı sıra için şu karakterleri eklenebilen `mode` satırbaşı karakterlerini çeviri modu belirtmek için.  
  
 `t`  
 Açık metin (modu çevrilmiş). Bu modda, CTRL + Z EOF karakter girişleri olarak yorumlanır. Açık olan dosyalardaki kullanarak okuma/yazma `"a+"`, `fopen` CTRL + Z dosya sonunda olup olmadığını denetler ve mümkünse kaldırır. Bu kullanılarak yapılır, çünkü `fseek` ve `ftell` CTRL + Z ile biter neden olabilecek bir dosyanın içinde taşımak için `fseek` yanlış dosyanın sonuna yakın davranır.  
  
 Metin modunda, satır başı satır besleme birleşimleri giriş üzerinde tek satır beslemeleri uygulamasına dönüştürülür ve satır besleme karakterler satır başı satır besleme birleşimleri çıktıyı dönüştürülür. Ne zaman bir Unicode akışı-g/Ç işlevi metin modunda (varsayılan), kaynak çalışır veya hedef akışı birden çok baytlı karakter dizisi olarak kabul edilir. Bu nedenle, Unicode akışı giriş işlevleri birden çok baytlı karakterler geniş karakter dönüştürme (olarak çağrısıyla varsa `mbtowc` işlevi). Aynı nedenden dolayı Unicode akışı çıkış işlevleri geniş karakterler birden çok baytlı karakterleri dönüştürme (olarak çağrısıyla varsa `wctomb` işlevi).  
  
 `b`  
 İkili (untranslated) modunda; aç satır başı ve satır besleme karakterler içeren çevirileri görüntülenmez.  
  
 Varsa `t` veya `b` verilmemiştir `mode`, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [_fmode](../../c-runtime-library/fmode.md). Varsa `t` veya `b` bağımsız değişkeni, işlev başarısız olur ve döndürür önekli `NULL`.  
  
 Metin ve ikili modlarda Unicode ve çok baytlı akış-g/Ç nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [metin ve ikili modlarda Unicode akışı g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
 `c`  
 İle ilişkili yürütme bayrağı etkinleştirmek `filename` böylece dosya arabellek içeriğini doğrudan ya da diske yazılan `fflush` veya `_flushall` olarak adlandırılır.  
  
 `n`  
 İle ilişkili yürütme bayrağını sıfırlama `filename` "no-uygulanmak." Bu varsayılandır. Ayrıca COMMODE.OBJ programınızla bağlarsanız genel tamamlama bayrağı geçersiz kılar. Açıkça COMMODE programınızla bağlantı sürece genel tamamlama bayrağı "no-commit" varsayılandır. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).  
  
 `N`  
 Dosya alt işlemler tarafından devralınan değil belirtir.  
  
 `S`  
 Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, sıralı erişim için diskten sınırlı gerekmez olduğunu belirtir.  
  
 `R`  
 Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, için rasgele erişim diskten sınırlı gerekmez olduğunu belirtir.  
  
 `T`  
 Dosya geçici belirtir. Mümkünse, bu değil temizlenip diske.  
  
 `D`  
 Dosya geçici belirtir. Son dosya işaretçisini kapatıldığında silinir.  
  
 `ccs=ENCODING`  
 Kodlanmış karakter kümesini belirtir (`UTF-8`, `UTF-16LE`, veya `UNICODE`) Bu dosya için. ANSI kodlamasını istiyorsanız belirtilmeyen bırakın.  
  
 Geçerli karakterleri `mode` kullanılan dize `fopen` ve `_fdopen` karşılık `oflag` kullanılan bağımsız değişkenler [_kurulum Aç](../../c-runtime-library/reference/open-wopen.md) ve [_sopen](../../c-runtime-library/reference/sopen-wsopen.md)gibi.  
  
|Mod dizedeki karakter|Eşdeğer `oflag` değeri`_open`/`_sopen`|  
|-------------------------------|----------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND`(genellikle `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND`(genellikle `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` )|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY`(genellikle `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR`(genellikle `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Yok.|  
|`n`|Yok.|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 Kullanıyorsanız `rb` modu, kod bağlantı noktası ve en büyük bir dosyanın okumayı gerekmez veya ağ performansı hakkında önemsemiyorsanız, bellek kullanmak için Win32 dosya isteğe bağlı olarak eşlenen olup olmadığını de düşünebilirsiniz.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fopen`|\<stdio.h >|  
|`_wfopen`|\<stdio.h > veya \<wchar.h >|  
  
 `_wfopen`bir Microsoft uzantısıdır. Uyumluluğu hakkında daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
 `c`, `n`, `t`, `S`, `R`, `T`, Ve `D` `mode` seçenekleri için Microsoft uzantıları olan `fopen` ve `_fdopen` ve burada kullanılmamalıdır ANSI taşınabilirlik istenen.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki programı iki dosyaları açar.  Kullandığı `fclose` ilk dosyayı kapatın ve `_fcloseall` tüm kalan dosyaları kapatın.  
  
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
  
## <a name="example"></a>Örnek  
 Aşağıdaki programı bir dosya oluşturur (veya varsa bir üzerine yazar), metin modunda Unicode kodlama sahip.  İki dizeyi dosyasına yazar ve dosyayı kapatır. Çıkış, çıktı bölümünden verileri içeren _wfopen_test.xml adlı bir dosyadır.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)