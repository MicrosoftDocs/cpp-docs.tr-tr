---
title: Genel değişkenler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.variables
dev_langs:
- C++
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2da3dd07c7088bee4be750b764b4a467bfebeae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392045"
---
# <a name="global-variables"></a>Global Değişkenler
Microsoft C çalışma zamanı kitaplığı aşağıdaki genel değişkenleri veya makroları sağlar. Bu genel değişkenler veya makroları çeşitli hangi yerine genel değişkenler kullanmanızı öneririz, daha güvenli işlevsel sürümleri lehinde kullanım dışı bırakıldı.  
  
|Değişken|Açıklama|  
|--------------|-----------------|  
|[__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)|Komut satırı bağımsız değişkenleri içeriyor.|  
|[_daylight, _dstbias, _timezone, and _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Kullanım dışı. Bunun yerine, kullanın `_get_daylight`, `_get_dstbias`, `_get_timezone`, ve `_get_tzname`.<br /><br /> Yerel saatine göre ayarlanır; Bazı tarih ve saat işlevleri kullanılır.|  
|[errno, _doserrno, _sys_errlist, and _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Kullanım dışı. Bunun yerine, kullanın `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` ve `strerror`.<br /><br /> Hata kodları ve ilgili bilgileri depolar.|  
|[_environ, _wenviron](../c-runtime-library/environ-wenviron.md)|Kullanım dışı. Bunun yerine, kullanın `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s`, ve `_wputenv_s`.<br /><br /> İşlem ortamı dizeleri işaretçiler dizileri işaretçileri; Başlangıçta başlatıldı.|  
|[_fmode](../c-runtime-library/fmode.md)|Kullanım dışı. Bunun yerine, kullanın `_get_fmode` veya `_set_fmode`.<br /><br /> Varsayılan dosya çevirisi modu ayarlar.|  
|[_iob](../c-runtime-library/iob.md)|Konsolu, dosyaları ve aygıtlar için g/ç denetim yapıları dizisi.|  
|[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Karakter Sınıflaması işlevler tarafından kullanılan bilgileri içerir.|  
|[_pgmptr, _wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Kullanım dışı. Bunun yerine, kullanın `_get_pgmptr` veya `_get_wpgmptr`.<br /><br /> Program, tam program adı veya programın nasıl başlatıldığına bağlı olarak, dosya adı uzantısı olmadan program adı tam veya göreli yola program başlangıçta başlatıldı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)   
 [__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [_get_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [_get_errno](../c-runtime-library/reference/get-errno.md)   
 [_set_errno](../c-runtime-library/reference/set-errno.md)   
 [_dupenv_s, _wdupenv_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [GETENV, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)