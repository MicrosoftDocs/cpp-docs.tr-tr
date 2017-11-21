---
title: _chdrive | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _chdrive
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
- chdrive
- _chdrive
dev_langs: C++
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 214083f511067c102fcb3ab7d3e6637cfeb548ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chdrive"></a>_chdrive
Geçerli çalışma sürücüyü değiştirir.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `drive`  
 Geçerli çalışma belirten 1-26 arasında bir tamsayı sürücü (1 = A, 2 = B ve benzeri).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır (geçerli çalışma sürücüsünü başarıyla; değiştirilmişse, 0) Aksi durumda, -1.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `drive` olan aralığı içinde 1 ila 26, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **_chdrive** işlev döndürür -1, `errno` ayarlanır `EACCES`, ve `_doserrno` ayarlanır `ERROR_INVALID_DRIVE`.  
  
 **_Chdrive** işlevi değil iş parçacığı bağımlı olduğundan dolayı **SetCurrentDirectory** kendisi iş parçacığı açısından güvenli işlevi. Kullanılacak **_chdrive** güvenli bir çok iş parçacıklı uygulamada kendi iş parçacığı eşitleme sağlamanız gerekir. Daha fazla bilgi için Git [MSDN Kitaplığı](http://go.microsoft.com/fwlink/?LinkID=150542) arayın ve sonra **SetCurrentDirectory**.  
  
 **_Chdrive** işlevi değişiklikler yalnızca geçerli çalışma sürücü;  **_chdir** geçerli çalışma dizini değiştirir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|**_chdrive**|\<Direct.h >|  
  
 Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [Sistem, _wsystem](../../c-runtime-library/reference/system-wsystem.md)