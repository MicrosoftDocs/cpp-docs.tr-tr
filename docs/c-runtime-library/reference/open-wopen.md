---
title: "_kurulum Aç, _wopen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _open
- _wopen
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
- _wopen
- _topen
- _open
dev_langs: C++
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
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2362db1db1686bcf87cb171b3f29da48226d54b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="open-wopen"></a>_open, _wopen
Bir dosyayı açar. Daha güvenli sürümlerinde kullanılabilir olmadığından, bu işlevler kullanım dışıdır; bkz: [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Dosya adı.  
  
 `oflag`  
 İzin verilen işlem türü.  
  
 `pmode`  
 İzin modu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri, açılan dosya için dosya tanımlayıcısı döndürür. Dönüş değeri -1, bir hata gösterir; Bu durumda `errno` aşağıdaki değerlerden birine ayarlayın.  
  
 `EACCES`  
 Yazma, dosyanın salt okunur bir dosyayı açmaya çalıştı paylaşma modunda belirtilen işlemleri izin verme ya da verilen yolu bir dizindir.  
  
 `EEXIST`  
 `_O_CREAT`ve `_O_EXCL` bayrakları belirtildi, ancak `filename` zaten mevcut.  
  
 `EINVAL`  
 Geçersiz `oflag` veya `pmode` bağımsız değişkeni.  
  
 `EMFILE`  
 Daha fazla hiçbir dosya tanımlayıcıları kullanılabilir (çok fazla dosya açık).  
  
 `ENOENT`  
 Dosya veya yol bulunamadı.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_open` İşlev tarafından belirtilen dosyayı açar `filename` okuma veya yazma belirtildiği için hazırlar `oflag`. `_wopen`bir joker karakter sürümü `_open`; `filename` bağımsız değişkeni `_wopen` bir joker karakter dizesidir. `_wopen`ve `_open` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_topen`|`_open`|`_open`|`_wopen`|  
  
 `oflag`bir veya daha fazla bildirim sabitlerden veya tanımlanan sabit birleşimleri bir tamsayı ifade biçimlendirilmiş \<fcntl.h >.  
  
 `_O_APPEND`  
 Dosya işaretçisini her yazma işleminden önce dosyanın sonuna taşır.  
  
 `_O_BINARY`  
 Dosya ikili (untranslated) modunda açılır. (Bkz [fopen](../../c-runtime-library/reference/fopen-wfopen.md) ikili mod açıklaması.)  
  
 `_O_CREAT`  
 Bir dosya oluşturur ve yazma için açar. Dosyanın belirtilen etkisizdir `filename` bulunmaktadır. `pmode` Bağımsız değişkeni gereklidir `_O_CREAT` belirtilir.  
  
 `_O_CREAT` &#124; `_O_SHORT_LIVED`  
 Dosya geçici olarak oluşturur ve mümkünse diske temizleme değil. `pmode` Bağımsız değişkeni gereklidir `_O_CREAT` belirtilir.  
  
 `_O_CREAT` &#124; `_O_TEMPORARY`  
 Geçici olarak bir dosya oluşturur; son dosya tanımlayıcısı kapatıldığında dosya silinir. `pmode` Bağımsız değişkeni gereklidir `_O_CREAT` belirtilir.  
  
 `_O_CREAT` &#124; `_O_EXCL`  
 Belirtilen dosya bir hata değeri döndürür `filename` bulunmaktadır. Yalnızca ile kullanıldığında geçerlidir `_O_CREAT`.  
  
 `_O_NOINHERIT`  
 Paylaşılan dosya tanımlayıcısı oluşturulmasını engeller.  
  
 `_O_RANDOM`  
 Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, için rasgele erişim diskten sınırlı gerekmez olduğunu belirtir.  
  
 `_O_RDONLY`  
 Yalnızca okumak için bir dosyayı açar. İle belirtilemez `_O_RDWR` veya `_O_WRONLY`.  
  
 `_O_RDWR`  
 Hem okumak ve yazmak için dosya açılır. İle belirtilemez `_O_RDONLY` veya `_O_WRONLY`.  
  
 `_O_SEQUENTIAL`  
 Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, sıralı erişim için diskten sınırlı gerekmez olduğunu belirtir.  
  
 `_O_TEXT`  
 Bir dosya (çevrilmiş) metin modunda açılır. (Daha fazla bilgi için bkz: [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_TRUNC`  
 Bir dosyayı açar ve onu uzunluğu sıfır olarak keser; Dosya yazma iznine sahip olmalıdır. İle belirtilemez `_O_RDONLY`. `_O_TRUNC`ile kullanılan `_O_CREAT` varolan bir dosyayı açar veya bir dosya oluşturur.  
  
> [!NOTE]
>  `_O_TRUNC` Bayrağı belirtilen dosyanın içeriğini yok eder.  
  
 `_O_WRONLY`  
 Yalnızca yazmak için dosya açılır. İle belirtilemez `_O_RDONLY` veya `_O_RDWR`.  
  
 `_O_U16TEXT`  
 Dosya Unicode UTF-16 modunda açılır.  
  
 `_O_U8TEXT`  
 Dosya Unicode UTF-8 modunda açılır.  
  
 `_O_WTEXT`  
 Dosya Unicode modunda açılır.  
  
 Dosya erişim modu belirtmek için ya da belirtmelisiniz `_O_RDONLY`, `_O_RDWR`, veya `_O_WRONLY`. Erişim modu için varsayılan değer yoktur.  
  
 Varsa `_O_WTEXT` bir dosya için okuma, açmak için kullanılan `_open` dosyasının başında okur ve bayt sırası işareti (BOM) için denetler. Bir ürün reçetesi ise, dosya UTF-8 veya UTF-16LE, ürün reçetesi bağlı olarak kabul edilir. Hiçbir BOM varsa, dosyayı ANSI kabul edilir. Ne zaman bir dosya açıldığında yazma için kullanarak `_O_WTEXT`, UTF-16 kullanılır. Ne olursa olsun, herhangi bir önceki ayar veya bayt sıra işareti, varsa `_O_U8TEXT` olan kullanıldığında, dosyayı her zaman UTF-8 olarak; açılır `_O_U16TEXT` olan kullanıldığında, dosyayı her zaman UTF-16 açılır.  
  
 Ne zaman bir dosya açıldığında Unicode modunda kullanarak `_O_WTEXT`, `_O_U8TEXT`, veya `_O_U16TEXT`, giriş işlevleri Çevir UTF-16 veri türü olarak depolanan dosyadan okunan veriler `wchar_t`. Unicode modunda açılmış bir dosyaya yazma işlevleri beklediğiniz UTF-16 veri türü olarak depolanan içeren arabellekleri `wchar_t`. Dosyanın UTF-8 olarak kodlanmıştır, sonra UTF-16 verileri UTF-8 yazılması ve onu okunduğunda dosyanın içeriğini UTF-8 kodlu UTF-16 çevrilir çevrilir. Okuma veya tek sayıda bayt Unicode modda yazma girişiminde bir parametre doğrulama hatasına neden olur. Okumak veya programınız UTF-8 olarak depolanan veri yazmak için bir metin veya ikili dosya modu yerine Unicode modunu kullanın. Tüm gerekli kodlama çeviri sorumlu.  
  
 Varsa `_open` çağrılır `_O_WRONLY|_O_APPEND` (ekleme modu) ve `_O_WTEXT`, `_O_U16TEXT`, veya `_O_U8TEXT`, ilk kez çalıştığında okuma ve yazma, dosyayı açmak ürün reçetesi okuyun ve sonra da yalnızca yazmak için kapatıp yeniden açın. Okuma ve yazma başarısız için dosyayı açmayı, yalnızca yazmak için dosyayı açar ve Unicode modu ayarı için varsayılan değeri kullanır.  
  
 İki veya daha fazla bildirim sabitleri forma kullanılan zaman `oflag` bağımsız değişkeni, sabitleri bit düzeyinde OR işleci ile birleştirilir ( `|` ). İkili ve metin modları tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 `pmode` Bağımsız değişkeni gereklidir yalnızca `_O_CREAT` belirtilir. Dosya zaten mevcutsa `pmode` göz ardı edilir. Aksi takdirde `pmode` yeni dosya ilk kez kapatıldığında ayarlanmış olan dosya izin ayarları, belirtir. `_open`Geçerli dosya izni maskesi uygular `pmode` önce izinleri ayarlayın. (Daha fazla bilgi için bkz: [_umask](../../c-runtime-library/reference/umask.md).) `pmode` birini veya her ikisini de tanımlanan aşağıdaki bildirim sabitleri içeren bir tamsayı ifade \<sys\stat.h >.  
  
 `_S_IREAD`  
 Yalnızca okuma izin verilir.  
  
 `_S_IWRITE`  
 Yazma izin verilir. (Geçerli, okuma ve yazma izin verir.)  
  
 `_S_IREAD`  `|`  `_S_IWRITE`  
 Okuma ve yazma izin verilir.  
  
 Her iki sabitleri verildiğinde olan bit düzeyinde OR işleci katılan ( `|` ). Windows, tüm dosyaları okunabilir; yalnızca yazma izni kullanılabilir değil. Bu nedenle, modları `_S_IWRITE` ve `_S_IREAD` `|` `_S_IWRITE` eşdeğerdir.  
  
 Bir değer, şunların bir birleşimi dışında `_S_IREAD` ve `_S_IWRITE` için belirtilen `pmode`— geçerli bir belirtin olsa bile `pmode` başka bir işletim sisteminde — veya herhangi bir diğer izin verilenden değer `oflag` değerleri belirtilirse, işlev hata ayıklama modunda bir onaylama oluşturur ve açıklandığı gibi geçersiz bir parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev dönüşleri -1 yürütülmesine izin veriliyorsa `errno` için `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_open`|\<io.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >|  
|`_wopen`|\<io.h > veya \<wchar.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >|  
  
 `_open`ve `_wopen` Microsoft uzantıları. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="output"></a>Çıkış  
  
```  
Open succeeded on input file  
Open succeeded on output file  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)