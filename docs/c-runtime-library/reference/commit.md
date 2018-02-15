---
title: _commit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _commit
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
dev_langs:
- C++
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed5a3f1e8d1f4a122ecf5a66393fa5c1f5c65f1b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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
 `_commit` Dosya başarılı olduysa 0 döndürür diske temizlendi. Dönüş değeri-1 hata gösterir.  
  
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
 [_read](../../c-runtime-library/reference/read.md)   
 [_write](../../c-runtime-library/reference/write.md)