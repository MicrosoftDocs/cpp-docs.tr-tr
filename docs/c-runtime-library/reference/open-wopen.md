---
title: _open, _wopen
ms.date: 11/04/2016
api_name:
- _open
- _wopen
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
ms.openlocfilehash: aad98844f4d9faf57c7bc5051eebabad09b860a4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951171"
---
# <a name="_open-_wopen"></a>_open, _wopen

Bir dosya açar. Daha güvenli sürümler kullanılabilir olduğundan bu işlevler kullanım dışıdır; bkz. [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md).

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

*kısaltın*<br/>
Dosya adı.

*oflag*<br/>
İzin verilen işlem türü.

*pmode*<br/>
İzin modu.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, açılan dosyanın dosya tanımlayıcısını döndürür. -1 ' in dönüş değeri bir hatayı gösterir; Bu durumda, **errno** aşağıdaki değerlerden birine ayarlanır.

|errno değeri|Koşul|
|-|-|
| **EACCES** | Dosya Paylaşım modu, yazma için salt okunurdur, belirtilen işlemlere izin vermiyor veya verilen yol bir dizin. |
| **EEXIST** | **_O_creat** ve **_O_hariç** bayraklar belirtildi, ancak *dosya adı* zaten var. |
| **EINVAL** | Geçersiz *oflag* veya *pmode* bağımsız değişkeni. |
| **EMFILE** | Başka dosya tanımlayıcısı yok (çok fazla dosya açık). |
| **ENOENT** | Dosya veya yol bulunamadı. |

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Open** işlevi, *filename* tarafından belirtilen dosyayı açar ve bu dosyayı okuma veya yazma için *hazırlar.* **_wopen** , **_open**öğesinin geniş karakterli bir sürümüdür; **_wopen** için *filename* bağımsız değişkeni geniş karakterli bir dizedir. **_wopen** ve **_open** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_topen**|**_Aç**|**_Aç**|**_wopen**|

*oflag* , bir veya daha fazla aşağıdaki bildirim sabitlerinden veya sabit kombinasyondan oluşturulan, fcntl. h > ' \<de tanımlanan bir tamsayı ifadesidir.

|*oflag* sabiti|Davranış|
|-|-|
| **_O_APPEND** | Her yazma işleminden önce dosya işaretçisini dosyanın sonuna kaydırır. |
| **_O_BINARY** | Dosyayı ikili (çevrilmemiş) modda açar. (İkili modun açıklaması için bkz. [fopen](fopen-wfopen.md) .) |
| **_O_CREAT** | Bir dosya oluşturur ve yazmak için açar. Dosya *adı* tarafından belirtilen dosya varsa herhangi bir etkiye sahip değildir. **_O_creat** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | Geçici olarak bir dosya oluşturur ve mümkünse disk boşaltılamaz. **_O_creat** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124; **_O_GEÇİCİDİR** | Geçici olarak bir dosya oluşturur; Dosya, son dosya tanımlayıcısı kapatıldığında silinir. **_O_creat** belirtildiğinde *pmode* bağımsız değişkeni gereklidir. |
| **_O_CREAT** &#124;` _O_EXCL` | Dosya *adı* tarafından belirtilen bir dosya varsa bir hata değeri döndürür. Yalnızca **_O_creat**ile kullanıldığında geçerlidir. |
| **_O_NOINHERIT** | Paylaşılan bir dosya tanımlayıcısının oluşturulmasını engeller. |
| **_O_RANDOM** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim |
| **_O_RDONLY** | Yalnızca okuma için bir dosya açar. **_O_rdwr** veya **_O_wronly**ile birlikte belirtilemez. |
| **_O_RDWR** | Hem okuma hem de yazma için bir dosya açar. **_O_rdonly** veya **_O_wronly**ile birlikte belirtilemez. |
| **_O_SEQUENTIAL** | Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir. |
| **_O_TEXT** | Metin (çevrilmiş) modunda bir dosya açar. (Daha fazla bilgi için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](fopen-wfopen.md).) |
| **_O_TRUNC** | Bir dosya açar ve sıfır uzunluğa kırpar; dosya yazma iznine sahip olmalıdır. **_O_rdonly**ile belirtilemez. **_O_creat** Ile kullanılan **_O_trunc** , var olan bir dosyayı açar veya bir dosya oluşturur. **Not:** **_O_trunc** bayrağı belirtilen dosyanın içeriğini yok eder. |
| **_O_WRONLY** | Yalnızca yazma için bir dosya açar. **_O_rdonly** veya **_O_rdwr**ile birlikte belirtilemez. |
| **_O_U16TEXT** | Unicode UTF-16 modunda bir dosya açar. |
| **_O_U8TEXT** | Unicode UTF-8 modunda bir dosya açar. |
| **_O_WTEXT** | Unicode modunda bir dosya açar. |

Dosya erişim modunu belirtmek için, **_O_rdonly**, **_O_RDWR**veya **_O_WRONLY**seçeneklerinden birini belirtmeniz gerekir. Erişim modu için varsayılan değer yoktur.

**_O_wtext** bir dosyayı okumak üzere açmak için kullanılırsa, **_Aç** dosyanın başlangıcını okur ve bir bayt sırası işareti (BOM) denetler. Bir BOM varsa, dosya, ürün reçetesine bağlı olarak UTF-8 veya UTF-16LE olarak değerlendirilir. Bir BOM yoksa, dosya ANSI olarak değerlendirilir. Bir dosya, **_O_wtext**kullanılarak yazma için açıldığında, UTF-16 kullanılır. Önceki bir ayar veya bayt sırası işaretinden bağımsız olarak, **_O_u8text** kullanılıyorsa, dosya her zaman UTF-8 olarak açılır; **_O_u16text** kullanılıyorsa, dosya her zaman UTF-16 olarak açılır.

Bir dosya, **_O_wtext**, **_O_U8TEXT**veya **_O_u16text**kullanılarak Unicode modda açıldığında, giriş işlevleri dosyadan okunan verileri **wchar_t**türünde depolanan UTF-16 verilerine çevirir. Unicode modunda açılan bir dosyaya yazan işlevler **wchar_t**türü olarak depolanan UTF-16 verileri içeren arabellekler bekler. Dosya UTF-8 olarak kodlanmışsa, UTF-16 verileri yazıldığında UTF-8 ' e çevrilir ve dosyanın UTF-8 kodlu içeriği okunarak UTF-16 ' a çevrilir. Unicode modunda tek sayıda bayt okuma veya yazma girişimi bir parametre doğrulama hatasına neden olur. Programınızda depolanan verileri UTF-8 olarak okumak veya yazmak için Unicode modu yerine bir metin veya ikili dosya modu kullanın. Gerekli tüm kodlama çevirilerinden siz sorumlusunuz.

**_Open** değeri **_O_WRONLY** |  **_O_APPEND** (Append modu) ve **_O_WTEXT**, **_O_U16TEXT**veya **_O_U8TEXT**ile çağrılırsa, önce dosyayı okumak ve yazmak için açmaya çalışır, sonra ürün reçetesini okuyabilir, sonra yeniden açın yalnızca yazma. Dosyayı okuma ve yazma için açmak başarısız olursa, dosyayı yalnızca yazma için açar ve Unicode modu ayarı için varsayılan değeri kullanır.

*Oflag* bağımsız değişkenini oluşturmak için iki veya daha fazla bildirim sabiti kullanıldığında sabitler BIT düzeyinde OR işleci ( **&#124;** ) ile birleştirilir. İkili ve metin modlarıyla ilgili bir tartışma için bkz. [metin ve Ikili mod dosya g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

*Pmode* bağımsız değişkeni yalnızca **_O_creat** belirtildiğinde gereklidir. Dosya zaten varsa *pmode* yok sayılır. Aksi halde, *pmode* , yeni dosya ilk kez kapatıldığında ayarlanan dosya izin ayarlarını belirtir. **_Aç** izinleri ayarlamadan önce geçerli dosya izni maskesini *pmode* 'a uygular. (Daha fazla bilgi için bkz. [_umask](umask.md).) *pmode* , SYS\Stat.h > içinde \<tanımlanan aşağıdaki bildirim sabitlerinden birini veya her ikisini de içeren bir tamsayı ifadesidir.

|*pmode*|Açıklama|
|-|-|
| **_S_IREAD** | Yalnızca okuma izni verilir. |
| **_S_IWRITE** | Yazma izni veriliyor. (Aslında, okuma ve yazma izni verir.) |
| **_S_İREAD** &#124; **_S_İWRİTE** | Okuma ve yazma izni verildi. |

Her iki sabit de verildiğinde, bit düzeyinde OR işleci ( **&#124;** ) ile birleştirilir. Windows 'da tüm dosyalar okunabilir; salt yazılır izin kullanılamıyor. Bu nedenle, **_s_iwrite** ve **_s_iread** |  **_s_iwrite** modları eşdeğerdir.

*Pmode*Için bazı **_S_iread** ve **_s_iwrite** birleşimi dışında bir değer belirtilmişse, başka bir işletim sisteminde geçerli bir *pmode* belirtse bile *veya izin verilen bir değer* Belirtilen işlev, hata ayıklama modunda bir onaylama işlemi oluşturur ve [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa işlev-1 döndürür ve **errno** öğesini **EINVAL**olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_Aç**|\<GÇ. h >|\<fcntl. h >, \<sys\types.h >, \<SYS\Stat.h >|
|**_wopen**|\<GÇ. h > veya \<wchar. h >|\<fcntl. h >, \<sys\types.h >, \<SYS\Stat.h >|

**_open** ve **_Wopen** , Microsoft uzantılarıdır. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
