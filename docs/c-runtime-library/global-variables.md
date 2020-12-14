---
description: 'Daha fazla bilgi edinin: genel değişkenler'
title: Global Değişkenler
ms.date: 11/04/2016
f1_keywords:
- c.variables
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
ms.openlocfilehash: 8029f058b39cb2e069c83279b361b79f3c8f5515
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229892"
---
# <a name="global-variables"></a>Global Değişkenler

Microsoft C çalışma zamanı kitaplığı, aşağıdaki genel değişkenleri veya makroları sağlar. Bu genel değişkenlerin veya makroların birkaçı, genel değişkenler yerine kullanmanızı önerdiğimiz daha güvenli işlevsel sürümlere göre kullanım dışı bırakılmıştır.

|Değişken|Açıklama|
|--------------|-----------------|
|[__argc, \_ _argv, \_ _wargv](../c-runtime-library/argc-argv-wargv.md)|Komut satırı bağımsız değişkenlerini içerir.|
|[_daylight, _dstbias, _timezone ve _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Kullanım dışı. Bunun yerine,,, `_get_daylight` `_get_dstbias` ve kullanın `_get_timezone` `_get_tzname` .<br /><br /> Yerel saat için ayarlar; Bazı tarih ve Saat işlevlerinde kullanılır.|
|[errno, _doserrno, _sys_errlist, and _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Kullanım dışı. Bunun yerine,,,, `_get_errno` `_set_errno` ve kullanın `_get_doserrno` `_set_doserrno` `perror` `strerror` .<br /><br /> Hata kodlarını ve ilgili bilgileri depolar.|
|[_environ, _wenviron](../c-runtime-library/environ-wenviron.md)|Kullanım dışı. Bunun yerine,,,,, `getenv_s` `_wgetenv_s` ve kullanın `_dupenv_s` `_wdupenv_s` `_putenv_s` `_wputenv_s` .<br /><br /> İşlem ortamı dizelerine işaretçiler dizileri için işaretçiler; Başlangıçta başlatıldı.|
|[_fmode](../c-runtime-library/fmode.md)|Kullanım dışı. Bunun yerine, `_get_fmode` veya kullanın `_set_fmode` .<br /><br /> Varsayılan dosya çevirisi modunu ayarlar.|
|[_iob](../c-runtime-library/iob.md)|Konsol, dosyalar ve cihazlar için g/ç denetim yapılarından oluşan dizi.|
|[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Karakter sınıflandırma işlevleri tarafından kullanılan bilgileri içerir.|
|[_pgmptr, _wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Kullanım dışı. Bunun yerine, `_get_pgmptr` veya kullanın `_get_wpgmptr` .<br /><br /> Programın nasıl çağrıldığına bağlı olarak programın tam veya göreli yolu, tam program adı veya dosya adı uzantısı olmayan program adı ile program başlangıcında başlatılır.|

## <a name="see-also"></a>Ayrıca bkz.

[C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)<br/>
[__argc, \_ _argv, \_ _wargv](../c-runtime-library/argc-argv-wargv.md)<br/>
[_get_daylight](../c-runtime-library/reference/get-daylight.md)<br/>
[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)<br/>
[_get_timezone](../c-runtime-library/reference/get-timezone.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)<br/>
[perror](../c-runtime-library/reference/perror-wperror.md)<br/>
[strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)<br/>
[_get_doserrno](../c-runtime-library/reference/get-doserrno.md)<br/>
[_set_doserrno](../c-runtime-library/reference/set-doserrno.md)<br/>
[_get_errno](../c-runtime-library/reference/get-errno.md)<br/>
[_set_errno](../c-runtime-library/reference/set-errno.md)<br/>
[_dupenv_s, _wdupenv_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)<br/>
[getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)
