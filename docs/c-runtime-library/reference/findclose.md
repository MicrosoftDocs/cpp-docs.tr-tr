---
title: _findclose | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _findclose
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
- _findclose
- findclose
dev_langs: C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8deae0204a9165ee9ab89036faab3b762c536349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="findclose"></a>_findclose
Belirtilen arama tanıtıcısı kapatır ve ilişkili kaynakları serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `handle`  
 Önceki bir çağrı tarafından döndürülen arama tanıtıcısıyla `_findfirst`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, `_findclose` 0 döndürür. Aksi takdirde, -1 döndürür ve ayarlar `errno` için `ENOENT`, daha fazla ile eşleşen dosyaları belirten bulunamadı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_findclose`|\<io.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sistem çağrıları](../../c-runtime-library/system-calls.md)   
 [Dosya arama işlevleri](../../c-runtime-library/filename-search-functions.md)