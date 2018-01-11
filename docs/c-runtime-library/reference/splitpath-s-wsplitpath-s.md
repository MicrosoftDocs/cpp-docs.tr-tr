---
title: _splitpath_s, _wsplitpath_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath_s
- _splitpath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs: C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6cfb2d72b728b64aeb00c3b8437f9c47e02fb813
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s
Bir yol adı bileşenlerine keser. Sürümleri bunlar [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`path`  
 Tam yolu.  
  
 [out]`drive`  
 Sürücü harfini izleyen iki nokta ile (`:`). Geçirebilirsiniz `NULL` sürücü harfi gerekmiyorsa, bu parametre için.  
  
 [in]`driveNumberOfElements`  
 Boyutunu `drive` tek baytlı veya uluslararası karakter arabellek. Varsa `drive` olan `NULL`, bu değerin 0 olması gerekir.  
  
 [out]`dir`  
 Sondaki eğik çizgi dahil olmak üzere dizin yolu. Eğik ( `/` ), ters eğik çizgi ( `\` ), ya da her ikisini de kullanılabilir. Geçirebilirsiniz `NULL` dizin yolu gerekmiyorsa, bu parametre için.  
  
 [in]`dirNumberOfElements`  
 Boyutunu `dir` tek baytlı veya uluslararası karakter arabellek. Varsa `dir` olan `NULL`, bu değerin 0 olması gerekir.  
  
 [out]`fname`  
 Temel dosya adı (uzantısı olmadan). Geçirebilirsiniz `NULL` filename gerekmiyorsa, bu parametre için.  
  
 [in]`nameNumberOfElements`  
 Boyutunu `fname` tek baytlı veya uluslararası karakter arabellek. Varsa `fname` olan `NULL`, bu değerin 0 olması gerekir.  
  
 [out]`ext`  
 Dosya adı uzantısı, dönem baştaki dahil olmak üzere (**.**). Geçirebilirsiniz `NULL` dosya adı uzantısı gerekmez, bu parametre için.  
  
 [in]`extNumberOfElements`  
 Boyutunu `ext` tek baytlı veya uluslararası karakter arabellek. Varsa `ext` olan `NULL`, bu değerin 0 olması gerekir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır; hatasında bir hata kodu.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|Koşul|Dönüş Değeri|  
|---------------|------------------|  
|`path`değil`NULL`|`EINVAL`|  
|`drive`olan `NULL`, `driveNumberOfElements` sıfır değil|`EINVAL`|  
|`drive`olmayan olan`NULL`, `driveNumberOfElements` sıfır|`EINVAL`|  
|`dir`olan `NULL`, `dirNumberOfElements` sıfır değil|`EINVAL`|  
|`dir`olmayan olan`NULL`, `dirNumberOfElements` sıfır|`EINVAL`|  
|`fname`olan `NULL`, `nameNumberOfElements` sıfır değil|`EINVAL`|  
|`fname`olmayan olan`NULL`, `nameNumberOfElements` sıfır|`EINVAL`|  
|`ext`olan `NULL`, `extNumberOfElements` sıfır değil|`EINVAL`|  
|`ext`olmayan olan`NULL`, `extNumberOfElements` sıfır|`EINVAL`|  
  
 Yukarıdaki koşullardan herhangi biri meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve geri dönüp `EINVAL`.  
  
 Herhangi bir arabellek ise sonucu tutmak için çok kısa, bu işlevler dizeleri boş, ayarlamak için tüm arabellekler temizleyin `errno` için `ERANGE`ve geri dönüp `ERANGE`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_splitpath_s` İşlevi dört bileşenlerine yolunu keser. `_splitpath_s`çok baytlı karakter sıralarının şu anda kullanımda birden çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. `_wsplitpath_s`bir joker karakter sürümü `_splitpath_s`; bağımsız değişkenleri `_wsplitpath_s` joker karakter dizelerdir. Aksi takdirde bu işlevler aynı şekilde davranır  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 Her bileşenin tam yolunun ayrı bir arabellek depolanır; bildirim sabitleri `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME`, ve `_MAX_EXT` (STDLIB içinde tanımlanmıştır. H) her dosya bileşeni için izin verilen en büyük boyutu belirtin. Bileşenleri karşılık gelen bildirim sabitleri yığın bozulması neden daha büyük dosya.  
  
 Aşağıdaki tabloda bildirim sabitleri değerleri listelenmektedir.  
  
|Ad|Değer|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Tam yolu (örneğin, bir dosya adı), bileşen içermiyorsa `_splitpath_s` karşılık gelen arabellek boş bir dize atar.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
 Bu işlevler hata ayıklama sürümleri ilk 0xFD arabellekle doldurun. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_splitpath_s`|\<stdlib.h >|  
|`_wsplitpath_s`|\<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)