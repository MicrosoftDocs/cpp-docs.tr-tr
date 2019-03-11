---
title: Global Değişkenler
ms.date: 11/04/2016
f1_keywords:
- c.variables
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
ms.openlocfilehash: dfa78bd2c7aae7cc6059443066cbef58512755ce
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744372"
---
# <a name="global-variables"></a>Global Değişkenler

Microsoft C çalışma zamanı kitaplığı aşağıdaki genel değişkenleri ve makroları sağlar. Birkaç bu genel değişkenler veya makrolar, genel değişkenler yerine kullanmanızı öneririz, daha güvenli işlevsel sürümleri ile değiştiriliyor bırakılmıştır.

|Değişken|Açıklama|
|--------------|-----------------|
|[__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)|Komut satırı bağımsız değişkenleri içerir.|
|[_daylight, _dstbias, _timezone, and _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Kullanım dışı. Bunun yerine, `_get_daylight`, `_get_dstbias`, `_get_timezone`, ve `_get_tzname`.<br /><br /> Yerel saate ayarlar; Bazı tarih ve saat işlevleri kullanılır.|
|[errno, _doserrno, _sys_errlist, and _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Kullanım dışı. Bunun yerine, `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` ve `strerror`.<br /><br /> Hata kodları ve ilgili bilgileri depolar.|
|[_environ, _wenviron](../c-runtime-library/environ-wenviron.md)|Kullanım dışı. Bunun yerine, `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s`, ve `_wputenv_s`.<br /><br /> İşlem ortamı dizelerine bir dizi işaretçileri; Başlangıçta başlatıldı.|
|[_fmode](../c-runtime-library/fmode.md)|Kullanım dışı. Bunun yerine, `_get_fmode` veya `_set_fmode`.<br /><br /> Varsayılan dosya çevirisi modu ayarlar.|
|[_iob](../c-runtime-library/iob.md)|Konsolu, dosyaları ve cihazlar için g/ç denetim yapıları dizisi.|
|[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Karakter-sınıflandırma işlevleri tarafından kullanılan bilgileri içerir.|
|[_pgmptr, _wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Kullanım dışı. Bunun yerine, `_get_pgmptr` veya `_get_wpgmptr`.<br /><br /> Program, tam adını veya programın nasıl çağrıldığı bağlı olarak, dosya adı uzantısı olmadan program adı tam veya göreli yoluna program başlangıcında başlatıldı.|

## <a name="see-also"></a>Ayrıca bkz.

[C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)<br/>
[__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)<br/>
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
