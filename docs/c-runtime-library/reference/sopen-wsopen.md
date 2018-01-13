---
title: _sopen, _wsopen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _sopen
- _wsopen
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
- _wsopen
- wsopen
- _sopen
- _tsopen
dev_langs: C++
helpviewer_keywords:
- sopen function
- sharing files
- opening files, for sharing
- _sopen function
- wsopen function
- files [C++], opening
- files [C++], sharing
- _wsopen function
ms.assetid: a9d4cccf-06e9-414d-96fa-453fca88cc1f
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bce1d0aac8b6b4d835b956a9ac05eece4e2e6428
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sopen-wsopen"></a>_sopen, _wsopen
Bir dosya paylaşımı için açılır. Daha güvenli bu işlevlerin sürümleri — bkz [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _sopen(  
   const char *filename,  
   int oflag,  
   int shflag [,  
   int pmode ]   
);  
int _wsopen(  
   const wchar_t *filename,  
   int oflag,  
   int shflag [,  
   int pmode ]   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Dosya adı.  
  
 `oflag`  
 İzin verilen işlem türü.  
  
 `shflag`  
 İzin verilen paylaşım türü.  
  
 `pmode`  
 İzni ayarı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri, açılan dosya için dosya tanımlayıcısı döndürür.  
  
 Varsa `filename` veya `oflag` olan bir `NULL` işaretçisi veya `oflag` veya `shflag` olan değer geçerli bir aralık içinde geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve `errno` aşağıdaki değerlerden birine.  
  
 `EACCES`  
 Belirtilen yol bir dizin olduğundan veya dosya salt okunur durumdadır, ancak yazma için açık işlem yapılmaya çalışıldı.  
  
 `EEXIST`  
 `_O_CREAT`ve `_O_EXCL` bayrakları belirtildi, ancak `filename` zaten mevcut.  
  
 `EINVAL`  
 Geçersiz `oflag` veya `shflag` bağımsız değişkeni.  
  
 `EMFILE`  
 Daha fazla hiçbir dosya tanımlayıcıları kullanılabilir.  
  
 `ENOENT`  
 Dosya veya yol bulunamadı.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_sopen` İşlev tarafından belirtilen dosyayı açar `filename` tarafından tanımlanan dosya paylaşılan okuma veya yazma için hazırlar `oflag` ve `shflag`. `_wsopen`bir joker karakter sürümü `_sopen`; `filename` bağımsız değişkeni `_wsopen` bir joker karakter dizesidir. `_wsopen`ve `_sopen` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsopen`|`_sopen`|`_sopen`|`_wsopen`|  
  
 Tamsayı ifade `oflag` bir veya daha fazla tanımlanan aşağıdaki bildirim sabitleri birleştirerek biçimlendirilmiş \<fcntl.h >. Ne zaman iki veya daha fazla sabitleri form bağımsız değişkeni `oflag`, bit düzeyinde OR işleci ile birleştirilir ( `|` ).  
  
 `_O_APPEND`  
 Dosya işaretçisini sonuna kadar her yazma işlemi önce dosyayı yeniden konumlandırır.  
  
 `_O_BINARY`  
 Bir dosya ikili (untranslated) modunda açılır. (Bkz [fopen](../../c-runtime-library/reference/fopen-wfopen.md) ikili mod açıklaması.)  
  
 `_O_CREAT`  
 Bir dosya oluşturur ve yazma için açar. Dosyanın belirtilen etkisizdir `filename` bulunmaktadır. `pmode` Bağımsız değişkeni gereklidir `_O_CREAT` belirtilir.  
  
 `_O_CREAT | _O_SHORT_LIVED`  
 Dosya geçici olarak oluşturur ve mümkünse diske temizleme değil. `pmode` Bağımsız değişkeni gereklidir `_O_CREAT` belirtilir.  
  
 `_O_CREAT | _O_TEMPORARY`  
 Geçici olarak bir dosya oluşturur; son dosya tanımlayıcısı kapatıldığında dosya silinir. `pmode` Bağımsız değişkeni gereklidir `_O_CREAT` belirtilir.  
  
 `_O_CREAT | _O_EXCL`  
 Bir hata değeri tarafından belirtilen bir dosya varsa döndürür `filename` bulunmaktadır. Yalnızca ile kullanıldığında geçerlidir `_O_CREAT`.  
  
 `_O_NOINHERIT`  
 Paylaşılan dosya tanımlayıcısı oluşturulmasını engeller.  
  
 `_O_RANDOM`  
 Öncelikle rasgele erişim diskten belirtir.  
  
 `_O_RDONLY`  
 Yalnızca okumak için bir dosyayı açar. İle belirtilemez `_O_RDWR` veya `_O_WRONLY`.  
  
 `_O_RDWR`  
 Hem okumak ve yazmak için bir dosyayı açar. İle belirtilemez `_O_RDONLY` veya `_O_WRONLY`.  
  
 `_O_SEQUENTIAL`  
 Öncelikle sıralı erişim diskten belirtir.  
  
 `_O_TEXT`  
 Bir dosya (çevrilmiş) metin modunda açılır. (Daha fazla bilgi için bkz: [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_TRUNC`  
 Bir dosyayı açar ve onu uzunluğu sıfır olarak keser; Dosya yazma iznine sahip olmalıdır. İle belirtilemez `_O_RDONLY`. `_O_TRUNC`ile kullanılan `_O_CREAT` varolan bir dosyayı açar veya bir dosya oluşturur.  
  
> [!NOTE]
>  `_O_TRUNC` Bayrağı belirtilen dosyanın içeriğini yok eder.  
  
 `_O_WRONLY`  
 Yalnızca yazmak için bir dosyayı açar. İle belirtilemez `_O_RDONLY` veya `_O_RDWR`.  
  
 `_O_U16TEXT`  
 Bir dosya Unicode UTF-16 modunda açılır.  
  
 `_O_U8TEXT`  
 Bir dosya Unicode UTF-8 modunda açılır.  
  
 `_O_WTEXT`  
 Bir dosya Unicode modunda açılır.  
  
 Dosya erişim modu belirtmek için ya da belirtmelisiniz `_O_RDONLY`, `_O_RDWR`, veya `_O_WRONLY`. Erişim modu için varsayılan değer yoktur.  
  
 Ne zaman bir dosya açıldığında Unicode modunda kullanarak `_O_WTEXT`, `_O_U8TEXT`, veya `_O_U16TEXT`, giriş işlevleri Çevir UTF-16 veri türü olarak depolanan dosyadan okunan veriler `wchar_t`. Unicode modunda açılmış bir dosyaya yazma işlevleri beklediğiniz UTF-16 veri türü olarak depolanan içeren arabellekleri `wchar_t`. Dosyanın UTF-8 olarak kodlanmıştır, sonra UTF-16 verileri UTF-8 yazılması ve onu okunduğunda dosyanın içeriğini UTF-8 kodlu UTF-16 çevrilir çevrilir. Okuma veya tek sayıda bayt Unicode modda yazma girişiminde bir parametre doğrulama hatasına neden olur. Okumak veya programınız UTF-8 olarak depolanan veri yazmak için bir metin veya ikili dosya modu yerine Unicode modunu kullanın. Tüm gerekli kodlama çeviri sorumlu.  
  
 Varsa `_sopen` çağrılır `_O_WRONLY | _O_APPEND` (ekleme modu) ve `_O_WTEXT`, `_O_U16TEXT`, veya `_O_U8TEXT`, ilk kez çalıştığında okuma ve yazma, dosyayı açmak ürün reçetesi okuyun ve sonra da yalnızca yazmak için kapatıp yeniden açın. Okuma ve yazma başarısız için dosyayı açmayı, yalnızca yazmak için dosyayı açar ve Unicode modu ayarı için varsayılan değeri kullanır.  
  
 Bağımsız değişken `shflag` tanımlanan aşağıdaki bildirim sabitlerden biri oluşan sabit bir ifade \<share.h >.  
  
 `_SH_DENYRW`  
 Bir dosya için okuma ve yazma reddeder.  
  
 `_SH_DENYWR`  
 Dosyaya yazma erişimini engeller.  
  
 `_SH_DENYRD`  
 Dosyaya okuma erişimini engeller.  
  
 `_SH_DENYNO`  
 İzinleri okuma ve yazma erişimi.  
  
 `pmode` Bağımsız değişkeni gereklidir yalnızca `_O_CREAT` belirtilir. Dosya mevcut değilse `pmode` yeni dosya ilk kez kapatıldığında ayarlanan dosyanın izin ayarları, belirtir. Aksi takdirde `pmode` göz ardı edilir. `pmode`birini veya her ikisini bildirim sabitleri içeren bir tamsayı ifade `_S_IWRITE` ve `_S_IREAD`, içinde tanımlanan \<sys\stat.h >. Her iki sabitleri verildiğinde, bunlar bit düzeyinde OR işleci ile birleştirilir. Anlamını `pmode` aşağıdaki gibidir.  
  
 `_S_IWRITE`  
 Yazma izin verilir.  
  
 `_S_IREAD`  
 Okuma izin verilir.  
  
 `_S_IREAD | _S_IWRITE`  
 Okuma ve yazma izin verilir.  
  
 Yazma izni verilmedi, dosya salt okunurdur. Windows işletim sisteminde, tüm dosyaları okunabilir; salt yazılır izin vermek mümkün değildir. Bu nedenle, modları `_S_IWRITE` ve `_S_IREAD | _S_IWRITE` eşdeğerdir.  
  
 `_sopen`Geçerli dosya izni maskesi uygular `pmode` önce izinleri ayarlayın. (Bkz [_umask](../../c-runtime-library/reference/umask.md).)  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_sopen`|\<io.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >, \<share.h >|  
|`_wsopen`|\<io.h > veya \<wchar.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >, \<share.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_locking](../../c-runtime-library/reference/locking.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_fsopen, _wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)