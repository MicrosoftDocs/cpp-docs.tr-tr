---
description: 'Daha fazla bilgi edinin: yerel ayar kategorileri'
title: Yerel Ayar Kategorileri
ms.date: 11/04/2016
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
ms.openlocfilehash: 2c6bfa4b2d1d0b76520043ee5568d51cf28a23c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246389"
---
# <a name="locale-categories"></a>Yerel Ayar Kategorileri

## <a name="syntax"></a>Syntax

```
#include <locale.h>
```

## <a name="remarks"></a>Açıklamalar

Yerel ayar kategorileri, bir programın yerel ayar bilgilerinin hangi kısmının kullanılacağını belirtmek için yerelleştirme yordamları tarafından kullanılan bildirim sabitleridir. Yerel ayar, programınızın belirli yönlerinin özelleştirilebilecek olduğu yere (veya ülkeye/bölgeye) başvurur. Yerel ayara bağımlı alanları, örneğin tarih biçimlendirmesini veya parasal değerler için görüntüleme biçimini içerir.

|Yerel ayar kategorisi|Programın etkilenen bölümleri|
|---------------------|-------------------------------|
|`LC_ALL`|Yerel ayara özgü tüm davranışlar (tüm kategoriler)|
|`LC_COLLATE`|`strcoll`Ve işlevlerinin davranışı `strxfrm`|
|`LC_CTYPE`|Karakter işleme işlevlerinin davranışı ( `isdigit` etkilenmeden,, `isxdigit` `mbstowcs` ve hariç `mbtowc` )|
|`LC_MAX`|Aynı `LC_TIME`|
|`LC_MIN`|Aynı `LC_ALL`|
|`LC_MONETARY`|İşlev tarafından döndürülen parasal biçimlendirme bilgileri `localeconv`|
|`LC_NUMERIC`|İşlev tarafından döndürülen biçimlendirilmiş çıkış yordamları (örneğin, `printf` ), veri dönüştürme yordamları ve parasal olmayan biçimlendirme bilgileri için ondalık nokta karakteri `localeconv`|
|`LC_TIME`|İşlevin davranışı `strftime`|

Bir örnek için bkz. [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) .

## <a name="see-also"></a>Ayrıca bkz.

[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcoll Işlevleri](../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
