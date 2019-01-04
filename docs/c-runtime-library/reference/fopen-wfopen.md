---
title: fopen, _wfopen
ms.date: 11/04/2016
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
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
ms.openlocfilehash: fb5f78411521dcbaddefda6c621b7fe44ce91736
ms.sourcegitcommit: cce52b2232b94ce8fd8135155b86e2d38a4e4562
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54031297"
---
# <a name="fopen-wfopen"></a>fopen, _wfopen

Bir dosya açar. Ek parametre doğrulama ve dönüş hata kodları gerçekleştirmek bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [fopen_s, _wfopen_s](fopen-s-wfopen-s.md).

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

*Dosya adı*<br/>
Dosya adı.

*Modu*<br/>
Etkinleştirilmiş erişim türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri açık dosyaya bir işaretçi döndürür. Bir null işaretçi değeri bir hata olduğunu gösterir. Varsa *filename* veya *modu* olduğu **NULL** ya da boş bir dize bu işlevleri açıklanan geçersiz parametre işleyicisi'ni tetikleme [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **NULL** ayarlayıp **errno** için **EINVAL**.

Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Fopen** işlevi tarafından belirtilen dosyayı açar *filename*. Varsayılan olarak, bir dar *filename* dize ANSI kod sayfasını (CP_ACP) kullanılarak yorumlanır. Windows masaüstü uygulamalarında bu OEM kod sayfasına (CP_OEMCP) kullanarak değiştirilebilir [SetFileApisToOEM](/windows/desktop/api/fileapi/nf-fileapi-setfileapistooem) işlevi. Kullanabileceğiniz [AreFileApisANSI](/windows/desktop/api/fileapi/nf-fileapi-arefileapisansi) belirlemek için işlev olup olmadığını *filename* ANSI veya sistem varsayılan OEM kod sayfası kullanılarak yorumlanır. **_wfopen** geniş karakterli sürümüdür **fopen**; bağımsız değişkenler **_wfopen** geniş karakterli dizelerdir. Aksi takdirde, **_wfopen** ve **fopen** aynı şekilde davranır. Yalnızca kullanarak **_wfopen** dosya akışında kullanılan kodlanan karakter kümesi etkilemez.

**fopen** geçerli; yürütme noktasında dosya sistemindeki yolları kabul eder **fopen** UNC yollarını ve içeren yolları paylaşımına erişimi kodu yürüten sistemin sahip olduğu sürece eşlenen ağ sürücülerini veya sürücü, yürütme sırasında eşlenen kabul eder. İşlevi için yol olduğunda **fopen**, sürücüler, yolların veya ağ paylaşımlarının yürütme ortamında kullanılabilir olacağından emin olun. Eğik çizgi (/) veya ters eğik çizgi kullanın (\\) bir yolda dizin ayırıcı olarak.

Her zaman dosya çubuğunda herhangi bir ek işlem gerçekleştirmeden önce işaretçinin NULL olup olmadığını görmek için dönüş değeri denetleyin. Bir hata oluşursa, genel değişken **errno** ayarlanır ve özel hata bilgisini almak için kullanılabilir. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="unicode-support"></a>Unicode Desteği

**fopen** Unicode dosya akışlarını destekler. Bir Unicode dosyasını açmak için başarılı bir **ccs** istenen kodlamayı belirten bayrak **fopen**aşağıdaki gibi.

> **Dosya *fp fopen = ("newfile.txt", "ccs rt +, =**_kodlama_**");**

İzin verilen değerler *kodlama* olan **UNICODE**, **UTF-8**, ve **UTF-16LE**.

Bir dosya Unicode modunda açıldığında, UTF-16 veri türü olarak depolanan içine dosyadan okunan veri giriş işlevleri çevir **wchar_t**. Unicode modunda açılan bir dosyaya yazma işlevleri beklediğiniz UTF-16 veri türü olarak depolanan içeren arabellek **wchar_t**. UTF-8 kodlanmış dosyası, ardından UTF-16 verileri UTF-8 yazılması ve okunduğunda, bu dosyanın içeriğini UTF-8 olarak kodlanmış UTF-16 çevrilir çevrilir. Okuma veya tek sayıda bayt Unicode modunda nedenlerdeki yazma girişiminde bir [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) hata. Programınız UTF-8 olarak depolanan verileri okuma veya yazma için bir Unicode modunda yerine bir metin veya ikili dosya modu kullanın. Tüm gerekli kodlama çeviri için sorumlu olursunuz.

Dosya zaten varsa ve okuma ya da ekleme için açıldığında, bayt sırası işareti (dosyasında varsa BOM), kodlamayı belirler. BOM kodlaması tarafından belirtilen kodlama üzerinde önceliklidir **ccs** bayrağı. **Ccs** kodlaması yalnızca kullanılır hiçbir BOM olmadığında veya dosya yeni bir dosyadır.

> [!NOTE]
> BOM saptama yalnızca geçerli Unicode modunda açılan dosyalar için (diğer bir deyişle, geçirilerek **ccs** bayrağı).

Aşağıdaki tabloda çeşitli için kullanılan modları özetlenmektedir **ccs** verilen bayrakları **fopen** ve dosyadaki bayt sırası işaretleri.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Ccs bayrağı ve BOM temelinde kullanılan Kodlamalar

|ccs bayrağı|Hiçbir BOM (ya da yeni dosya)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

Unicode modunda yazmak için açılan dosyalarda, kendilerine otomatik yazılan bir BOM vardır.

Varsa *modu* olduğu **"ccs =**_kodlama_**"**, **fopen** hem okuma hem de'ı kullanarak dosyayı açmak ilk olarak çalışır hem de yazma erişimi. Bu işlem başarılı olursa, işlev dosyanın kodlamasını belirlemek için BOM'u okur; Bu başarısız olursa, işlev dosya için varsayılan kodlamayı kullanır. Her iki durumda da **fopen** ardından dosyayı salt yazılır erişim kullanarak yeniden açılır. (Bu durum geçerlidir **"a"** modu için değil, yalnızca **"a +"** modu.)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen**|**fopen**|**fopen**|**_wfopen**|

Karakter dizesi *modu* dosya için şu şekilde istenen erişim türünü belirtir.

|*Modu*|Access|
|-|-|
| **"r"** | Okuma için açar. Dosya mevcut değil ya da bulunamıyorsa **fopen** çağrısı başarısız olur. |
| **"w"** | Yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir. |
| **"a"** | (Ekleme dosyaya yeni veri yazılmadan önce dosya sonu (EOF) işaretçisini kaldırmadan) dosyanın sonunda yazma için açar. Henüz yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma ve yazma için açar. Dosyanın mevcut olması gerekir. |
| **"w +"** | Hem okuma ve yazma için boş bir dosya açar. Dosya varsa içeriği yok edilir. |
| **"a +"** | Okuma ve ekleme için açar. Ekleme işlemi, dosyaya yeni veri yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma tamamlandıktan sonra EOF işaretçisi geri yüklenmez. Henüz yoksa dosyayı oluşturur. |

Ne zaman bir dosya açıldığında kullanarak **"a"** erişim türü veya **"a +"** erişim türü, tüm yazma işlemleri dosyanın sonunda gerçekleşir. Dosya işaretçisini kullanarak konumlandırılabilir [fseek](fseek-fseeki64.md) veya [rewind](rewind.md), ancak herhangi bir işlemi gerçekleştirildi yazma önce her zaman geri dosyanın sonuna kadar taşınır. Bu nedenle, var olan verilerin üzerine yazılamaz.

**"A"** modu, dosyaya ekleme yapmadan önce EOF işaretçisi kaldırmaz. Ekleme oluştuktan sonra MS-DOS TYPE komutu özgün EOF işaretçisi verileri ve dosyaya eklenen herhangi bir veriyi değil yalnızca gösterir. Dosyaya eklemeden önce **"a +"** modu EOF işaret metnini kaldırır. Ekleme işleminde sonra MS-DOS TYPE komutu dosyasında tüm verileri gösterir. **"A +"** modu CTRL + Z EOF işaretiyle biten bir akış dosyasına ekleme için gereklidir.

Zaman **"r +"**, **"w +"**, veya **"a +"** erişim türü belirtildiğinde, hem okumaya hem yazmaya etkinleştirilir (dosyanın "güncelleştirme" açık olarak kabul edilir). Ancak, yazma okumaya geçtiğinizde giriş işlemi bir EOF işaretçisi ile karşılaşmalıdır. EOF yoksa, bir dosyaya işlevi bulan bir çağrı göndermelisiniz kullanmanız gerekir. Dosya konumlama işlevleri **fsetpos**, [fseek](fseek-fseeki64.md), ve [rewind](rewind.md). Yazmadan okumaya geçtiğinizde, bir çağrı göndermelisiniz kullanmalısınız **fflush** veya bir dosyaya işlevi bulan.

Daha önceki değerlere ek olarak, şu karakterlerden eklenerek *modu* yeni satır karakterlerinin çeviri modu belirtmek için.

|*modu* değiştiricisi|Çeviri modu|
|-|-|
| **T** | Açık metin (çevrilmiş) modunda. |
| **b** | İkili (çevrilmemiş) modda; açık satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin modunda, CTRL + Z girişteki bir EOF karakteri olarak yorumlanır. Kullanarak okuma/yazma için açılmadı dosyalarında **"a +"**, **fopen** CTRL + Z dosya sonunda olup olmadığını denetler ve mümkünse bunu kaldırır. Kullanıldığından yapıldığını [fseek](fseek-fseeki64.md) ve **ftell** CTRL + Z ile biter neden olabilecek bir dosya içinde hareket etmek [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış davranmasına.

Metin modunda, satır başı satır besleme kombinasyonları girişte karakterlerine çevrilir ve satır başı besleme karakterleri için çıkış satır başı satır besleme kombinasyonlarına çevrilir. Ne zaman bir Unicode akışı g/Ç işlevi metin modunda (varsayılan), kaynak çalışır veya hedef akışın bir dizi çok baytlı karakter olduğu varsayılır. Bu nedenle Unicode akışı girdi işlevleri çok baytlı karakter geniş karakterlere dönüştürür (bir çağrıda olduğu gibi **mbtowc** işlevi). Aynı nedenden dolayı Unicode akış çıkışı işlevleri geniş karakterleri çok baytlı karakterlere dönüştürür (bir çağrıda olduğu gibi **wctomb** işlevi).

Varsa **t** veya **b** verilmez *modu*, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [_fmode](../../c-runtime-library/fmode.md). Varsa **t** veya **b** bağımsız değişken, işlev başarısız olur ve döndürür önekli **NULL**.

Metin ve ikili modlarda Unicode ve çok baytlı akış g/Ç kullanma hakkında daha fazla bilgi için bkz. [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [metin ve ikili modlarda Unicode Stream g/ç](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

Aşağıdaki seçenekler eklenerek *modu* ek davranışları belirtmek için.

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

Geçerli karakterler için *modu* kullanılan dize **fopen** ve **_fdopen** karşılık *oflag* içindekullanılanbağımsızdeğişkenler[_aç](open-wopen.md) ve [_sopen](sopen-wsopen.md)aşağıdaki gibi.

|Öğesindeki karakterler *modu* dize|Eşdeğer *oflag* değerini \_açın /\_sopen|
|-------------------------------|----------------------------------------------------|
|**a**|**\_O\_WRONLY** &#124;  **\_O\_ekleme** (genellikle  **\_O\_WRONLY** &#124;  **\_O\_CREAT** &#124;  **\_O\_ekleme**)|
|**bir +**|**\_O\_RDWR** &#124;  **\_O\_ekleme** (genellikle  **\_O\_RDWR** &#124;  **\_ O\_ekleme** &#124;  **\_O\_CREAT** )|
|**r**|**\_O\_RDONLY**|
|**r +**|**\_O\_RDWR**|
|**w**|**\_O\_WRONLY** (genellikle  **\_O\_WRONLY** &#124;  **\_O\_CREAT** &#124;  **\_O\_TRUNC**)|
|**w +**|**\_O\_RDWR** (genellikle  **\_O\_RDWR** &#124;  **\_O\_CREAT** &#124;  **\_ O\_TRUNC**)|
|**b**|**\_O\_İKİLİ**|
|**T**|**\_O\_METİN**|
|**c**|Hiçbiri|
|**n**|Hiçbiri|
|**S**|**\_O\_SIRALI**|
|**R**|**\_O\_RASGELE**|
|**T**|**\_O\_SHORTLIVED**|
|**D**|**\_O\_GEÇİCİ**|
|**ccs UNICODE =**|**\_O\_WTEXT**|
|**ccs = UTF-8**|**\_O\_UTF8**|
|**ccs UTF-16LE =**|**\_O\_UTF16**|

Kullanıyorsanız **rb** modu sahip olmadığınız kodunuzu bağlantı noktasına ve çoğu büyük dosyaları okumayı bekleyen ya da ağ performansını önemsemiyorsanız, ayrıca bellek kullanmak için Win32 dosya bir seçenek olarak eşlemli düşünebilirsiniz.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fopen**|\<stdio.h >|
|**_wfopen**|\<stdio.h > veya \<wchar.h >|

**_wfopen** bir Microsoft uzantısıdır. Uyumluluk hakkında daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**c**, **n**, **t**, **S**, **R**, **T**, ve **D**  *modu* seçenekleri için Microsoft genişletmeleridir **fopen** ve **_fdopen** ve ANSI taşınabilirliğinin istendiği durumlarda kullanılmamalıdır.

## <a name="example-1"></a>Örnek 1

Aşağıdaki program iki dosya açmaktadır.  Kullandığı **fclose** birinci dosyayı kapatmak için ve **_fcloseall** kalan dosyaları kapatmak için.

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

Aşağıdaki program bir dosya oluşturur (veya varsa üzerine yazmaktadır), kodlaması Unicode olan metin modunda.  İki dizeyi alana yazar ve dosyayı kapatır. Çıktı çıktı bölümünden veri içeren _wfopen_test.xml adlı bir dosyadır.

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
