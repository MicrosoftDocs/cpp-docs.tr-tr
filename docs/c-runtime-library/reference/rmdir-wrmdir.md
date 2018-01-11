---
title: _rmdir, _wrmdir | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wrmdir
- _rmdir
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
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
dev_langs: C++
helpviewer_keywords:
- _rmdir function
- directories [C++], deleting
- rmdir function
- directories [C++], removing
- trmdir function
- _trmdir function
- _wrmdir function
- wrmdir function
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d926158275e56c6d845d73fe2d8b4092a84c096c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rmdir-wrmdir"></a>_rmdir, _wrmdir
Bir dizini siler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dirname`  
 Kaldırılacak dizinin yolu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dizin başarıyla silinirse bu işlevlerin her biri 0 döndürür. Dönüş değeri -1, bir hata gösterir ve `errno` aşağıdaki değerlerden birine ayarlayın:  
  
 **ENOTEMPTY**  
 Yol bir dizin değil, dizini boş değil veya geçerli çalışma dizini veya kök dizini dizindir.  
  
 `ENOENT`  
 Yolu geçersiz.  
  
 **EACCES**  
 Bir programı dizinine açık bir tanıtıcı vardır.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_rmdir` İşlevi tarafından belirtilen dizin siler `dirname`. Dizinin boş olması gerekir ve geçerli çalışma dizini veya kök dizini olmamalıdır.  
  
 `_wrmdir`bir joker karakter sürümü `_rmdir`; `dirname` bağımsız değişkeni `_wrmdir` bir joker karakter dizesidir. `_wrmdir`ve `_rmdir` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_rmdir`|\<Direct.h >|  
|`_wrmdir`|\<Direct.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_mkdir](../../c-runtime-library/reference/mkdir-wmkdir.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)