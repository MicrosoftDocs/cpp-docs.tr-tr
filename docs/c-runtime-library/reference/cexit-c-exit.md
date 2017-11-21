---
title: _cexit, _c_exit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _c_exit
- _cexit
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cexit
- c_exit
- _c_exit
- cexit
dev_langs: C++
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edd16f6ac3d37bfc1ccd13d4e70a8868a4ac23cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cexit-cexit"></a>_cexit, _c_exit
Temizleme işlemleri gerçekleştirir ve işlem sonlandırılıyor olmadan döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `_cexit` İşlev çağrısı, son giren ilk çıkar (LIFO) sırası, tarafından kaydedilen işlevleri `atexit` ve `_onexit`. Ardından `_cexit` tüm g/ç arabelleklerini alır ve döndürmeden önce tüm açık akışları kapatır. `_c_exit`aynı `_exit` ancak arama işlemi işleme olmadan döndürür `atexit` veya `_onexit` veya akış arabellekleri temizleme. Davranışını `exit`,`_exit`, `_cexit`, ve `_c_exit` aşağıdaki tabloda gösterilmiştir.  
  
|İşlev|Davranış|  
|--------------|--------------|  
|`exit`|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|  
|`_exit`|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|  
|`_cexit`|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür, ancak işlemi sonlandırmamız değil.|  
|`_c_exit`|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana verir, ancak işlemi sonlandırmamız değil.|  
  
 Çağırdığınızda `_cexit` veya `_c_exit` İşlevler, çağrı sırada mevcut geçici veya otomatik nesneleri için Yıkıcılar çağrılmaz. Bir otomatik bir işlevin tanımlı olduğu bir nesne nereye nesne statik olarak bildirilmedi nesnesidir. Geçici bir nesne derleyici tarafından oluşturulan nesnedir. Otomatik nesneyi çağırmadan önce yok etmek için `_cexit` veya `_c_exit`, açıkça yıkıcı nesne için şu şekilde çağırın:  
  
```  
myObject.myClass::~myClass( );  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_cexit`|\<Process.h >|  
|`_c_exit`|\<Process.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [Sistem, _wsystem](../../c-runtime-library/reference/system-wsystem.md)