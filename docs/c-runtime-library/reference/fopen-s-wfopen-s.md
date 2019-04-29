---
title: fopen_s, _wfopen_s
ms.date: 11/04/2016
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
ms.openlocfilehash: 1309f991b8251bde7d614aa274d8d2e9da7a8ed3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333332"
---
# <a name="fopens-wfopens"></a>fopen_s, _wfopen_s

Bir dosya açar. Bu sürümleri [fopen, _wfopen](fopen-wfopen.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Açılan dosya işaretçisi alacak dosya işaretçisini bir işaretçi.

*Dosya adı*<br/>
Dosya adı.

*Modu*<br/>
İzin verilen erişim türü.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; bir hata kodu. Bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu hata kodları hakkında daha fazla bilgi.

### <a name="error-conditions"></a>Hata koşulları

|*pFile*|*Dosya adı*|*Modu*|Dönüş Değeri|İçeriğini *pFile*|
|-------------|----------------|------------|------------------|------------------------|
|**NULL**|Tüm|Tüm|**EINVAL**|değişmedi|
|Tüm|**NULL**|Tüm|**EINVAL**|değişmedi|
|Tüm|Tüm|**NULL**|**EINVAL**|değişmedi|

## <a name="remarks"></a>Açıklamalar

Tarafından açılan dosyaları **fopen_s** ve **_wfopen_s** paylaşılabilir değildir. Bir dosyanın paylaşılabilir olması gerekiyorsa kullanın [_fsopen, _wfsopen](fsopen-wfsopen.md) uygun Paylaşım modu sabiti ile — Örneğin, **_SH_DENYNO** okuma/yazma paylaşımı.

**Fopen_s** işlevi tarafından belirtilen dosyayı açar *filename*. **_wfopen_s** geniş karakterli sürümüdür **fopen_s**; bağımsız değişkenler **_wfopen_s** geniş karakterli dizelerdir. **_wfopen_s** ve **fopen_s** aynı şekilde davranır.

**fopen_s** geçerli; yürütme noktasında dosya sistemindeki yolları kabul eder UNC yollarını ve eşlenen ağ sürücülerini içeren yolları kabul edildiği tarafından **fopen_s** kodu yürüten sistemin paylaşımına erişimi olduğundan veya ağ sürücüsü, yürütme sırasında eşlenen sürece. İşlevi için yol olduğunda **fopen_s**, sürücüler, yollar, kullanılabilirliği hakkında varsayımlar yapmayın veya ağ paylaşımları yürütme ortamında. Eğik çizgi (/) veya ters eğik çizgi kullanın (\\) bir yolda dizin ayırıcı olarak.

Bu işlevler kendi parametrelerini doğrular. Varsa *pFile*, *filename*, veya *modu* null bir işaretçiyse, açıklanan şekilde geçersiz parametre özel durum, bu işlevleri oluşturmak [parametre doğrulama ](../../c-runtime-library/parameter-validation.md).

Her zaman dosyanın başka bir işlem gerçekleştirmeden önce işlevi başarılı olup olmadığını görmek için dönüş değeri denetleyin. Bir hata oluşursa hata kodunu döndürülür ve genel değişkeni **errno** ayarlanır. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="unicode-support"></a>Unicode desteği

**fopen_s** Unicode dosya akışlarını destekler. Yeni veya mevcut bir Unicode dosyasını açmak için başarılı bir *ccs* istenen kodlamayı belirten bayrak **fopen_s**:

**fopen_s(&fp, "newfile.txt", "rw, ccs=**_encoding_**");**

İzin verilen değerler *kodlama* olan **UNICODE**, **UTF-8**, ve **UTF-16LE**. Var. için hiçbir değer belirtilmemişse *kodlama*, **fopen_s** ANSI kodlaması kullanır.

Dosya zaten varsa ve okuma ya da ekleme için açıldığında, bayt sırası işareti (BOM), dosya içinde varsa kodlamayı belirler. BOM kodlaması tarafından belirtilen kodlama üzerinde önceliklidir *ccs* bayrağı. *Ccs* kodlaması yalnızca kullanılır hiçbir BOM yoksa veya dosyanın yeni bir dosya olup olmadığını olduğunda.

> [!NOTE]
> BOM saptama, yalnızca Unicode modunda açılan dosyalar için geçerlidir; diğer bir deyişle, geçirilerek *ccs* bayrağı.

Aşağıdaki tabloda özetlenmiştir modları için çeşitli *ccs* verildiğinden bayrakları **fopen_s** ve dosyadaki bayt sırası işaretleri için.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Ccs bayrağı ve BOM temelinde kullanılan Kodlamalar

|ccs bayrağı|Hiçbir BOM (ya da yeni dosya)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode modunda yazmak için açılan dosyaları, kendilerine otomatik yazılan bir BOM vardır.

Varsa *modu* olduğu **"ccs =**_kodlama_**"**, **fopen_s** önce dosyayı hem okuma hem de ile açmayı denediğinde erişimi ve yazma erişimi. Başarılı olursa, işlev dosyanın kodlamasını belirlemek için BOM'u okur; işlem başarısız olursa, işlev dosya için varsayılan kodlamayı kullanır. Her iki durumda da **fopen_s** dosyayı salt yazılır erişimle yeniden açar. (Bu durum geçerlidir **bir** modu yalnızca değil **a +**.)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

Karakter dizesi *modu* dosya için şu şekilde istenen erişim türünü belirtir.

|*Modu*|Access|
|-|-|
| **"r"** | Okuma için açar. Dosya mevcut değil ya da bulunamıyorsa **fopen_s** çağrısı başarısız olur. |
| **"w"** | Yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir. |
| **"a"** | (Ekleme dosyaya yeni veri yazılmadan önce dosya sonu (EOF) işaretçisini kaldırmadan) dosyanın sonunda yazma için açar. Henüz yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma ve yazma için açar. Dosyanın mevcut olması gerekir. |
| **"w +"** | Hem okuma ve yazma için boş bir dosya açar. Dosya varsa içeriği yok edilir. |
| **"a+"** | Okuma ve ekleme için açar. Ekleme işlemi, dosyaya yeni veri yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma tamamlandıktan sonra EOF işaretçisi geri yüklenmez. Henüz yoksa dosyayı oluşturur. |

Ne zaman bir dosya açıldığında kullanarak **"a"** veya **"a +"** erişim türü, tüm yazma işlemleri dosyanın sonunda gerçekleşir. Dosya işaretçisini kullanarak konumlandırılabilir [fseek](fseek-fseeki64.md) veya [rewind](rewind.md), ancak herhangi bir işlemi gerçekleştirilir böylece var olan verilerin üzerine yazma önce her zaman geri dosyanın sonuna kadar taşınır.

**"A"** modu kaldırmaz EOF işaretçisi önce dosyasına ekleme. Ekleme oluştuktan sonra MS-DOS TYPE komutu özgün EOF işaretçisi verileri ve dosyaya eklenen herhangi bir veriyi değil yalnızca gösterir. **"A +"** modu EOF işaret metnini kaldırır önce dosyasına ekleme. Ekleme işleminde sonra MS-DOS TYPE komutu dosyasında tüm verileri gösterir. **"A +"** modu CTRL + Z EOF işaret metnini kullanarak sonlandırılmış bir akış dosyasına ekleme için gereklidir.

Zaman **"r +"**, **"w +"**, veya **"a +"** erişim türü belirtildiğinde, hem okumaya hem yazmaya izin verilir. (Dosya için "güncelleştir" için açıldığı söylenir). Ancak, yazma okumaya geçtiğinizde giriş işlemi bir EOF işaretçisi ile karşılaşmalıdır. EOF yoksa, bir dosyada konumlanma işlevine bir çağrı göndermelisiniz kullanmanız gerekir. Dosya konumlama işlevleri **fsetpos**, [fseek](fseek-fseeki64.md), ve [rewind](rewind.md). Yazmadan okumaya geçtiğinizde, bir çağrı göndermelisiniz kullanmalısınız **fflush** veya dosyada konumlanma bir işlev.

Yukarıdaki değerlerden ek olarak, şu karakterler eklenebilir *modu* yeni satır karakterlerinin çeviri modu belirtmek için:

|*modu* değiştiricisi|Çeviri modu|
|-|-|
| **T** | Açık metin (çevrilmiş) modunda. |
| **b** | İkili (çevrilmemiş) modda; açık satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin (çevrilmiş) modunda, CTRL + Z girişteki bir dosya sonu karakteri olarak yorumlanır. Okuma/yazma için açılmış dosyalarında **"a +"**, **fopen_s** CTRL + Z dosya sonunda olup olmadığını denetler ve eğer mümkünse bunu kaldırır. Kullanıldığından yapıldığını [fseek](fseek-fseeki64.md) ve **ftell** bir CTRL + Z ile biter neden olabilir bir dosya içinde hareket etmek [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış davranmasına.

Ayrıca, metin modunda, satır başı satır besleme kombinasyonları girişte karakterlerine çevrilir ve satır başı besleme karakterleri için çıkış satır başı satır besleme kombinasyonlarına çevrilir. Ne zaman bir Unicode akışı g/Ç işlevi metin modunda (varsayılan), kaynak çalışır veya hedef akışın bir dizi çok baytlı karakter olduğu varsayılır. Bu nedenle Unicode akışı girdi işlevleri çok baytlı karakter geniş karakterlere dönüştürür (bir çağrıda olduğu gibi **mbtowc** işlevi). Aynı nedenden dolayı Unicode akış çıkışı işlevleri geniş karakterleri çok baytlı karakterlere dönüştürür (bir çağrıda olduğu gibi **wctomb** işlevi).

Varsa **t** veya **b** verilmez *modu*, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [_fmode](../../c-runtime-library/fmode.md). Varsa **t** veya **b** bağımsız değişken, işlev başarısız olur ve döndürür önekli **NULL**.

Metin ve ikili modlarda Unicode ve çok baytlı akış g/Ç kullanma hakkında daha fazla bilgi için bkz. [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [metin ve ikili modlarda Unicode Stream g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

|*modu* değiştiricisi|Davranış|
|-|-|
| **c** | İlişkili için bayrak kaydetmeyi etkinleştir *filename* dosya tamponunun içeriği doğrudan diske yazılır, böylece **fflush** veya **_flushall** çağrılır. |
| **n** | İlişkili tamamlama bayrağı sıfırlar *filename* için "no-commit." Bu varsayılandır. Ayrıca programınızı COMMODE.OBJ ile bağlarsanız genel tamamlama bayrağını geçersiz kılar. Programınızı COMMODE ile açıkça bağlantı sürece, küresel kaydetme bayrağı varsayılan "no-commit". OBJ (bkz [bağlantı seçenekleri](../../c-runtime-library/link-options.md)). |
| **N** | Dosyanın alt işlemler tarafından devralınmadığını belirtir. |
| **S** | Önbelleğe alma iyileştirildiğini, ancak sıralı erişim için diskten sınırlı olduğunu belirtir. |
| **R** | Önbelleğe alma iyileştirildiğini, ancak rastgele erişim için diskten sınırlı olduğunu belirtir. |
| **T** | Bir dosyayı geçici olarak belirtir. Mümkünse, boşaltılmaz diske. |
| **D** | Bir dosyayı geçici olarak belirtir. Son dosya işaretçisi kapatıldığında silinir. |
| **ccs =**_kodlama_ | Kodlanmış karakter kümesini belirtir (biri **UTF-8**, **UTF-16LE**, veya **UNICODE**) Bu dosya için. Bırakın, ANSI kodlaması isterseniz belirtmeden. |

Geçerli karakterler için *modu* kullanılan dize **fopen_s** ve [_fdopen](fdopen-wfdopen.md) karşılık *oflag* kullanılan bağımsız değişkenleri [_ Açık](open-wopen.md) ve [_sopen](sopen-wsopen.md)aşağıdaki gibi.

|Öğesindeki karakterler *modu* dize|Eşdeğer *oflag* _aç/_sopen değeri|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (genellikle **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_APPEND **)|
|**a+**|**_O_RDWR** &#124; **_O_APPEND** (usually **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r +**|**_O_RDWR**|
|**w**|**_O_WRONLY** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_TRUNC**)|
|**w +**|**_O_RDWR** (usually **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**T**|**_O_TEXT**|
|**c**|Yok.|
|**n**|None|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs UNICODE =**|**_O_WTEXT**|
|**ccs=UTF-8**|**_O_UTF8**|
|**ccs=UTF-16LE**|**_O_UTF16**|

Kullanıyorsanız **rb** modu, kodunuzu ve çok sayıda dosyayı okumayı bekleyen gerekmez ve/veya ağ performansı hakkında düşünmeniz gerekmez, bellekle eşlenen Win32 dosyalar da bir seçenek olabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fopen_s**|\<stdio.h >|
|**_wfopen_s**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

**c**, **n**, ve **t** *modu* seçenekleri için Microsoft genişletmeleridir **fopen_s** ve [_fdopen](fdopen-wfdopen.md) ve ANSI taşınabilirliğinin istendiği durumlarda kullanılmamalıdır.

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
