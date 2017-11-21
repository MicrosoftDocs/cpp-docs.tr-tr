---
title: _commit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _commit
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
- _commit
- commit
dev_langs: C++
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4df750e90ccd36545348f765ecd00e02728481e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="commit"></a>_commit
Bir dosyayı doğrudan diske aktarır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Açık olan dosyaya başvuran dosya tanımlayıcısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_commit`Dosya başarılı olduysa 0 döndürür diske temizlendi. Dönüş değeri-1 hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 `_commit` İşlevi ile ilişkili dosya yazmak için işletim sistemi zorlar `fd` diske. Bu çağrı, belirtilen dosya hemen değil işletim sisteminin istediğiniz kadar Temizlenen sağlar.  
  
 Varsa `fd` geçersiz dosya tanımlayıcısı açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevi -1 döndürür ve `errno` ayarlanır `EBADF`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|----------------------|  
|`_commit`|\<io.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_microsoft](../../c-runtime-library/reference/read.md)   
 [_Write](../../c-runtime-library/reference/write.md)