---
title: fopen_s, _wfopen_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wfopen_s
- fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
dev_langs:
- C++
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
caps.latest.revision: 41
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6883fc46d10ebb577a41039f4eda2083b187ad31
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="fopens-wfopens"></a>fopen_s, _wfopen_s

Bir dosyayı açar. Bu sürümleri [fopen, _wfopen](fopen-wfopen.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Açılan dosyayı işaretçisine alacak dosya işaretçisini gösteren bir işaretçi.

*Dosya adı*<br/>
Dosya adı.

*Modu*<br/>
İzin verilen erişim türü.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; hatasında bir hata kodu. Bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu hata kodları hakkında daha fazla bilgi.

### <a name="error-conditions"></a>Hata koşulları

|*pFile*|*Dosya adı*|*Modu*|Dönüş Değeri|İçeriği *pFile*|
|-------------|----------------|------------|------------------|------------------------|
|**NULL**|tüm|tüm|**EINVAL**|Değişmedi|
|tüm|**NULL**|tüm|**EINVAL**|Değişmedi|
|tüm|tüm|**NULL**|**EINVAL**|Değişmedi|

## <a name="remarks"></a>Açıklamalar

Tarafından açılan dosyaları **fopen_s** ve **_wfopen_s** paylaşılabilir değildir. Bir dosyanın paylaşılabilir olması gerekiyorsa kullanın [_fsopen, _wfsopen](fsopen-wfsopen.md) uygun Paylaşım modu sabiti ile — Örneğin, **_SH_DENYNO** okuma/yazma paylaşım.

**Fopen_s** işlev tarafından belirtilen dosyayı açar *filename*. **_wfopen_s** bir joker karakter sürümü **fopen_s**; bağımsız değişkenleri **_wfopen_s** joker karakter dizelerdir. **_wfopen_s** ve **fopen_s** Aksi takdirde aynı şekilde davranır.

**fopen_s** geçerli yürütme; noktasında dosya sistemi yolları kabul eder UNC yollarını ve eşlenen ağ sürücülerini içeren yollar kabul edilir tarafından **fopen_s** kodu yürütmesini sistem paylaşımına erişimi olduğundan veya ağ sürücüsü, yürütme sırasında eşlenmiş sürece. İçin yollar oluşturmak zaman **fopen_s**, sürücüler, yollar, kullanılabilirliği hakkında özelliklerinin yapmayın veya ağ paylaşımları yürütme ortamında. Eğik çizgi (/) veya ters eğik çizgi kullanabilirsiniz (\\) yolu dizin ayırıcı olarak.

Bu işlevler kendi parametreleri doğrulayın. Varsa *pFile*, *filename*, veya *modu* null işaretçi açıklandığı gibi geçersiz bir parametre özel durum, bu işlevler üret [parametre doğrulama ](../../c-runtime-library/parameter-validation.md).

Her zaman dosyanın başka herhangi bir işlemi gerçekleştirmeden önce işlevi başarılı olup olmadığını görmek için dönüş değerini denetleyin. Bir hata oluşursa, döndürülen hata kodu ve genel değişkeni **errno** ayarlanır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="unicode-support"></a>Unicode desteği

**fopen_s** Unicode dosya akışları destekler. Yeni veya varolan bir Unicode dosyası açmak için geçirmek bir *ccs* için istenen kodlamayı belirten bayrak **fopen_s**:

**fopen_s (& fp, "newfile.txt", "rw, ccs =**_kodlama_**");**

İzin verilen değerler, *kodlama* olan **UNICODE**, **UTF-8**, ve **UTF-16LE**. İçin hiçbir değer var. belirtilmişse, *kodlama*, **fopen_s** ANSI kodlamasını kullanır.

Dosya zaten var ve okuma veya ekleme için açılan bayt sırası işareti (BOM), varsa, dosya kodlamasını belirler. Ürün reçetesi kodlama tarafından belirtilen kodlama üzerinden önceliklidir *ccs* bayrağı. *Ccs* kodlaması yalnızca kullanılan hiçbir BOM yoksa veya dosyanın yeni bir dosya olup olmadığını olduğunda.

> [!NOTE]
> Ürün reçetesi algılama yalnızca Unicode modunda açılmış dosyalar için de geçerlidir; diğer bir deyişle, göre geçirme *ccs* bayrağı.

Modları çeşitli için aşağıdaki tabloda özetlenmiştir *ccs* verilen bayrakları **fopen_s** ve bayt sırası işaretleri dosyasındaki için.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Kodlamalar kullanılan temel alarak bayrağı ve ürün reçetesi ccs

|Bayrak ccs|Hiçbir ürün reçetesi (veya yeni dosyası)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode modda yazmak için açılan dosyaları otomatik olarak yazılmış bir ürün reçetesi vardır.

Varsa *modu* olan **"ccs =**_kodlama_**"**, **fopen_s** ilk ile hem de okuma dosyayı açmayı denediğinde erişim ve yazma erişimi. Başarılı olursa, işlevi için dosya kodlamasını belirlemek için ürün reçetesi okur; işlem başarısız olursa, dosya için varsayılan kodlamayı işlevini kullanır. Her iki durumda da **fopen_s** yalnızca yazma erişimi olan dosya yeniden açar. (Bu uygulandığı **bir** modu yalnızca değil **bir +**.)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

Karakter dizesi *modu* dosya için aşağıdaki gibi istenen erişim türünü belirtir.

|*Modu*|Access|
|-|-|
**"r"**|Okuma için açılır. Dosya yok veya bulunamadı, **fopen_s** çağrısı başarısız olur.
**"w"**|Boş bir dosya yazma için açılır. Verilen dosya varsa, içeriği yok.
**"a"**|Yazma (yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaret kaldırmadan ekleyerek) dosya sonunda açar. Henüz yoksa dosyası oluşturur.
**"r +"**|Hem okuma ve yazma için açılır. Dosyanın mevcut olması gerekir.
**"w +"**|Hem okumak ve yazmak için boş bir dosya açar. Dosya varsa, içeriği yok.
**"bir +"**|Okuma ve sonuna ekleme için açılır. Yeni veri dosyasına yazılmadan önce ekleme işlemi EOF işaret kaldırılmasını içerir. EOF işaret yazma tamamlandıktan sonra geri yüklenmez. Henüz yoksa dosyası oluşturur.

Ne zaman bir dosya açıldığında kullanarak **"a"** veya **"bir +"** erişim türüne, tüm işlemleri ortaya dosyanın sonunda yazma. Dosya işaretçisini kullanarak konumlandırılmasına [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md), ancak herhangi bir işlemi gerçekleştirilir böylece varolan verilerin üzerine yazmadan önce her zaman geri dosyanın sonuna taşınır.

**"A"** modu kaldırmaz EOF işaret dosyasına ekleyerek önce. Sonuna ekleme gerçekleştikten sonra MS-DOS türü komutu yalnızca özgün EOF işaret kadar veri ve dosyanın sonuna olmayan herhangi bir veri gösterir. **"Bir +"** modunu kaldırabilirsiniz EOF işaret dosyasına ekleyerek önce. Sonuna ekleme sonra MS-DOS türü komut dosyasında tüm verileri gösterir. **"Bir +"** modu CTRL + Z EOF işaret kullanarak sonlandırılır bir akış dosyasına ekleme için gereklidir.

Zaman **"r +"**, **"w +"**, veya **"bir +"** erişim türü belirtildi, hem okuma ve yazma izin verilir. (Dosya "güncelleştirmesi" açık olarak kabul edilir.) Ancak, yazma için veri okuma geçiş yaptığınızda, giriş işlemi EOF işaret karşılaştığınız gerekir. Hiçbir EOF ise, müdahalede bulunan bir dosya konumlandırma işlevi çağrısı kullanmanız gerekir. Dosya konumlandırma işlevlerdir **fsetpos**, [fseek](fseek-fseeki64.md), ve [geri sarma](rewind.md). Okunurken yazma geçiş yaptığınızda, müdahalede bulunan bir arama ya da kullanmalıdır **fflush** veya dosya konumlandırma işlevi.

Yukarıdaki değerleri yanı sıra şu karakterler eklenebilir *modu* satırbaşı karakterlerini çeviri modu belirtmek için:

|*mod* değiştiricisi|Çeviri modu|
|-|-|
**T**|Açık metin (modu çevrilmiş).
**b**|İkili (untranslated) modunda; aç satır başı ve satır besleme karakterler içeren çevirileri görüntülenmez.

Metin (çevrilmiş) modunda CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma ile açılan dosyaları içinde **"bir +"**, **fopen_s** CTRL + Z dosya sonunda olup olmadığını denetler ve, mümkünse kaldırır. Bu kullanılarak yapılır, çünkü [fseek](fseek-fseeki64.md) ve **ftell** bir CTRL + Z ile biter neden olabilir. bir dosyanın içinde taşımak için [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış bir şekilde davranır.

Ayrıca, metin modunda, satır başı satır besleme birleşimleri giriş üzerinde tek satır beslemeleri uygulamasına dönüştürülür ve satır besleme karakterler satır başı satır besleme birleşimleri çıktıyı dönüştürülür. Ne zaman bir Unicode akışı-g/Ç işlevi metin modunda (varsayılan), kaynak çalışır veya hedef akışı birden çok baytlı karakter dizisi olarak kabul edilir. Bu nedenle, Unicode akışı giriş işlevleri birden çok baytlı karakterler geniş karakter dönüştürme (olarak varsa çağrısı ile **mbtowc** işlevi). Aynı nedenden dolayı Unicode akışı çıkış işlevleri geniş karakterler birden çok baytlı karakterleri dönüştürme (olarak varsa çağrısı ile **wctomb** işlevi).

Varsa **t** veya **b** verilmemiştir *modu*, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [_fmode](../../c-runtime-library/fmode.md). Varsa **t** veya **b** bağımsız değişkeni, işlev başarısız olur ve döndürür önekli **NULL**.

Metin ve ikili modlarda Unicode ve çok baytlı akış-g/Ç kullanma hakkında daha fazla bilgi için bkz: [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [metin ve ikili modlarda Unicode akışı g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

|*mod* değiştiricisi|Davranış|
|-|-|
**c**|İle ilişkili yürütme bayrağı etkinleştirmek *filename* böylece dosya arabellek içeriğini doğrudan ya da diske yazılan **fflush** veya **_flushall** olarak adlandırılır.
**n**|İle ilişkili yürütme bayrağını sıfırlama *filename* "no-uygulanmak." Bu varsayılandır. Ayrıca COMMODE.OBJ programınızla bağlarsanız genel tamamlama bayrağı geçersiz kılar. Açıkça COMMODE programınızla bağlantı sürece genel tamamlama bayrağı "no-commit" varsayılandır. OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)).
**N**|Dosya alt işlemler tarafından devralınan değil belirtir.
**S**|Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, sıralı erişim için diskten sınırlı gerekmez olduğunu belirtir.
**R**|Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, için rasgele erişim diskten sınırlı gerekmez olduğunu belirtir.
**T**|Dosya geçici belirtir. Mümkünse, bu değil temizlenip diske.
**D**|Dosya geçici belirtir. Son dosya işaretçisini kapatıldığında silinir.
**ccs =**_kodlama_|Kodlanmış karakter kümesini belirtir (birini **UTF-8**, **UTF-16LE**, veya **UNICODE**) Bu dosya için. ANSI kodlamasını istiyorsanız belirtilmeyen bırakın.

Geçerli karakterleri *modu* kullanılan dize **fopen_s** ve [_fdopen](fdopen-wfdopen.md) karşılık *oflag* kullanılan bağımsız değişkenler [_ Açık](open-wopen.md) ve [_sopen](sopen-wsopen.md)gibi.

|İçindeki karakterleri *modu* dize|Eşdeğer *oflag* _kurulum Aç/_sopen için değer|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (genellikle **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_APPEND **)|
|**bir +**|**_O_RDWR** &#124; **_O_APPEND** (genellikle **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r +**|**_O_RDWR**|
|**W**|**_O_WRONLY** (genellikle **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_TRUNC **)|
|**w +**|**_O_RDWR** (genellikle **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**T**|**_O_TEXT**|
|**c**|Yok.|
|**n**|Yok.|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs UNICODE =**|**_O_WTEXT**|
|**ccs = UTF-8**|**_O_UTF8**|
|**ccs UTF-16LE =**|**_O_UTF16**|

Kullanıyorsanız **rb** modu, kodunuzu bağlantı noktası ve çok sayıda dosya okumayı gerekmez ve/veya ağ performansı hakkında önemli değil, bellekle eşlenen Win32 dosyalar bir seçenek de olabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fopen_s**|\<stdio.h >|
|**_wfopen_s**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

**c**, **n**, ve **t** *modu* seçenekleri için Microsoft uzantıları olan **fopen_s** ve [_fdopen](fdopen-wfdopen.md) ve burada ANSI taşınabilirlik istenen kullanılmamalıdır.

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
