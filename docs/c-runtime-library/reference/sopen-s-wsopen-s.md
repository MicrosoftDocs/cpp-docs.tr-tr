---
title: _sopen_s, _wsopen_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _sopen_s
- _wsopen_s
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
- _sopen_s
- wsopen_s
- _wsopen_s
- sopen_s
dev_langs: C++
helpviewer_keywords:
- sopen_s function
- _wsopen_s function
- wsopen_s function
- opening files, for sharing
- files [C++], opening
- _sopen_s function
- files [C++], sharing
ms.assetid: 059a0084-d08c-4973-9174-55e391b72aa2
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 403fc7f285aeebf5fc7b6d4ebb39d1e922d8edc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sopens-wsopens"></a>_sopen_s, _wsopen_s
Bir dosya paylaşımı için açılır. Bu sürümleri [_sopen ve _wsopen](../../c-runtime-library/reference/sopen-wsopen.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _sopen_s(  
   int* pfh,  
   const char *filename,  
   int oflag,  
   int shflag,  
   int pmode  
);  
errno_t _wsopen_s(  
   int* pfh,  
   const wchar_t *filename,  
   int oflag,  
   int shflag,  
   int pmode,  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pfh`  
 Dosya tanıtıcısı veya -1 hata durumunda.  
  
 [in]`filename`  
 Dosya adı.  
  
 [in]`oflag`  
 İzin verilen işlem türü.  
  
 [in]`shflag`  
 İzin verilen paylaşım türü.  
  
 [in]`pmode`  
 İzni ayarı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan bir dönüş değeri bir hata olduğunu gösterir; Bu durumda `errno` aşağıdaki değerlerden birine ayarlayın.  
  
 `EACCES`  
 Belirtilen yol bir dizin olduğundan veya dosya salt okunur durumdadır, ancak yazma için açık işlem yapılmaya çalışıldı.  
  
 `EEXIST`  
 `_O_CREAT`ve `_O_EXCL` bayrakları belirtildi, ancak `filename` zaten mevcut.  
  
 `EINVAL`  
 Geçersiz `oflag`, `shflag`, veya `pmode` bağımsız değişken veya `pfh` veya `filename` null işaretçi oluştu.  
  
 `EMFILE`  
 Daha fazla dosya tanımlayıcıları kullanılabilir.  
  
 `ENOENT`  
 Dosya veya yol bulunamadı.  
  
 İşleve geçersiz bir bağımsız değişken aktarılırsa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve `EINVAL` döndürülür.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Bir hata olması durumunda, aracılığıyla -1 döndürülür `pfh` (sürece `pfh` null işaretçi).  
  
## <a name="remarks"></a>Açıklamalar  
 `_sopen_s` İşlev tarafından belirtilen dosyayı açar `filename` tarafından tanımlanan dosya paylaşılan okuma veya yazma için hazırlar `oflag` ve `shflag`. `_wsopen_s`bir joker karakter sürümü `_sopen_s`; `filename` bağımsız değişkeni `_wsopen_s` bir joker karakter dizesidir. `_wsopen_s`ve `_sopen_s` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsopen_s`|`_sopen_s`|`_sopen_s`|`_wsopen_s`|  
  
 Tamsayı ifade `oflag` içinde tanımlanan bir veya daha fazla bildirim sabitleri birleştirerek biçimlendirilmiş \<fcntl.h >. Ne zaman iki veya daha fazla sabitleri form bağımsız değişkeni `oflag`, bit düzeyinde OR işleci ile birleştirilir ( `|` ).  
  
 `_O_APPEND`  
 Dosya işaretçisini sonuna kadar her yazma işlemi önce dosyayı yeniden konumlandırır.  
  
 `_O_BINARY`  
 Bir dosya ikili (untranslated) modunda açılır. (Bkz [fopen](../../c-runtime-library/reference/fopen-wfopen.md) ikili mod açıklaması.)  
  
 `_O_CREAT`  
 Bir dosya oluşturur ve yazma için açar. Dosyanın belirtilen etkisizdir `filename` bulunmaktadır.  
  
 `_O_CREAT | _O_SHORT_LIVED`  
 Dosya geçici olarak oluşturur ve mümkünse diske temizleme değil.  
  
 `_O_CREAT | _O_TEMPORARY`  
 Geçici olarak bir dosya oluşturur; son dosya tanımlayıcısı kapatıldığında dosya silinir.  
  
 `_O_CREAT | _O_EXCL`  
 Belirtilen dosya bir hata değeri döndürür `filename` bulunmaktadır. Yalnızca ile kullanıldığında geçerlidir `_O_CREAT`.  
  
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
  
 Varsa `_sopen_s` çağrılır `_O_WRONLY | _O_APPEND` (ekleme modu) ve `_O_WTEXT`, `_O_U16TEXT`, veya `_O_U8TEXT`, ilk kez çalıştığında okuma ve yazma, dosyayı açmak ürün reçetesi okuyun ve sonra da yalnızca yazmak için kapatıp yeniden açın. Okuma ve yazma başarısız için dosyayı açmayı, yalnızca yazmak için dosyayı açar ve Unicode modu ayarı için varsayılan değeri kullanır.  
  
 Bağımsız değişken `shflag` tanımlanan aşağıdaki bildirim sabitlerden biri oluşan sabit bir ifade \<share.h >.  
  
 `_SH_DENYRW`  
 Bir dosya için okuma ve yazma reddeder.  
  
 `_SH_DENYWR`  
 Dosyaya yazma erişimini engeller.  
  
 `_SH_DENYRD`  
 Dosyaya okuma erişimini engeller.  
  
 `_SH_DENYNO`  
 İzinleri okuma ve yazma erişimi.  
  
 `pmode` Bağımsız değişkeni gereklidir her zaman, aksine, `_sopen`. Belirttiğinizde `_O_CREAT`, dosyanın mevcut değilse `pmode` yeni dosya ilk kez kapatıldığında ayarlanan dosyanın izin ayarları, belirtir. Aksi takdirde `pmode` göz ardı edilir. `pmode`birini veya her ikisini bildirim sabitleri içeren bir tamsayı ifade `_S_IWRITE` ve `_S_IREAD`, içinde tanımlanan \<sys\stat.h >. Her iki sabitleri verildiğinde, bunlar bit düzeyinde OR işleci ile birleştirilir. Anlamını `pmode` aşağıdaki gibidir.  
  
 `_S_IWRITE`  
 Yazma izin verilir.  
  
 `_S_IREAD`  
 Okuma izin verilir.  
  
 `_S_IREAD | _S_IWRITE`  
 Okuma ve yazma izin verilir.  
  
 Yazma izni verilmedi, dosya salt okunurdur. Windows işletim sisteminde, tüm dosyaları okunabilir; salt yazılır izin vermek mümkün değildir. Bu nedenle, modları `_S_IWRITE` ve `_S_IREAD | _S_IWRITE` eşdeğerdir.  
  
 `_sopen_s`Geçerli dosya izni maskesi uygular `pmode` önce izinleri ayarlayın. (Bkz [_umask](../../c-runtime-library/reference/umask.md).)  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_sopen_s`|\<io.h >|\<fcntl.h >, \<sys\types.h >, \<sys\stat.h >, \<share.h >|  
|`_wsopen_s`|\<io.h > veya \<wchar.h >|\<fcntl.h >, \<sys/types.h >, \<sys/stat.h >, \<share.h >|  
  
 `_sopen_s`ve `_wsopen_s` Microsoft uzantıları. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_locking](../../c-runtime-library/reference/locking.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_fsopen, _wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)