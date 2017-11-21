---
title: _getdcwd, _wgetdcwd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd
- _wgetdcwd
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
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs: C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7541bf3135dfcc3734a43fe64277e5b8ea141e9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd
Geçerli çalışma dizininin tam yolu belirtilen sürücü üzerindeki alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `drive`  
 Sürücüyü belirtir negatif olmayan bir tamsayı (0 = varsayılan sürücü, 1 A, 2 = B vb.).  
  
 Belirtilen sürücü kullanılamıyorsa veya sürücü türünü (örneğin, çıkarılabilir, sabit, CD-ROM'dan, RAM disk veya ağ sürücüsü) belirlenemiyor, açıklanan geçersiz parametre işleyicisi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md), olan çağrılır.  
  
 `buffer`  
 Yol için depolama konumu veya **NULL**.  
  
 Varsa **NULL** belirtilirse, bu işlev bir arabellek en az ayırır `maxlen` kullanarak boyut **malloc**ve dönüş değerini `_getdcwd` ayrılmış arabelleğe bir işaretçidir. Arabellek çağırarak serbest bırakılabilirler `free` ve işaretçiyi geçirme.  
  
 `maxlen`  
 Yol uzunluğunun karakter cinsinden belirtir sıfır olmayan pozitif bir tamsayı: `char` için `_getdcwd` ve `wchar_t` için `_wgetdcwd`.  
  
 Varsa `maxlen` açıklanan geçersiz parametre işleyicisi sıfırdan büyük değil [parametre doğrulaması](../../c-runtime-library/parameter-validation.md), çağrılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen sürücüye geçerli çalışma dizininin tam yolu temsil eden bir dize işaretçi veya `NULL`, bir hata gösterir.  
  
 Varsa `buffer` olarak belirtilen `NULL` ve ayırmak için yeterli bellek `maxlen` karakter, bir hata oluşur ve `errno` ayarlanır `ENOMEM`. Sondaki boş karakter içerir, yol uzunluğu aşması durumunda `maxlen`, bir hata oluşur ve `errno` ayarlanır `ERANGE`. Bu hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_getdcwd` İşlevi belirtilen sürücüde geçerli çalışma dizininin tam yolunu alır ve konumunda depolar `buffer`. Geçerli çalışma dizini köküne ayarlarsanız dizesi bir ters eğik (\\). Kök dışında başka bir dizin için geçerli çalışma dizini ayarlarsanız, dizesi bir ters eğik çizgi ile değil dizin adı ile sona erer.  
  
 `_wgetdcwd`bir joker karakter sürümü `_getdcwd`ve kendi `buffer` parametre ve dönüş değeri olan joker karakter dizeleri. Aksi takdirde, `_wgetdcwd` ve `_getdcwd` aynı şekilde davranır.  
  
 Bağımlı olsa da bu işlev iş parçacığı **GetFullPathName**, kendisini değil iş parçacığı güvenli olduğu. Ancak, birden çok iş parçacıklı uygulamanız bu iki işlevini çağırırsa iş parçacığı güvenliği ihlal edebilir ve **GetFullPathName**. Daha fazla bilgi için Git [MSDN Kitaplığı](http://go.microsoft.com/fwlink/?LinkID=150542) arayın ve sonra **GetFullPathName**.  
  
 Sürümü olan bu işlev, `_nolock` soneki aynı şekilde davrandığını bu işleve iş parçacığı açısından güvenli değildir ve girişime diğer iş parçacıkları tarafından korunmuyor. Daha fazla bilgi için bkz: [_getdcwd_nolock, _wgetdcwd_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md).  
  
 Zaman `_DEBUG` ve `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_getdcwd` ve `_wgetdcwd` yapılan çağrılar tarafından değiştirilen `_getdcwd_dbg` ve `_wgetdcwd_dbg` böylece bellek ayırmaları ayıklayabilirsiniz. Daha fazla bilgi için bkz:[_getdcwd_dbg, _wgetdcwd_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_getdcwd`|\<Direct.h >|  
|`_wgetdcwd`|\<Direct.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)