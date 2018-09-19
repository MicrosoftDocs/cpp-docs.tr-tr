---
title: Yerel ayar kategorileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12162e7d6eabfc60b3b4c028b990b720a502f516
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077886"
---
# <a name="locale-categories"></a>Yerel Ayar Kategorileri

## <a name="syntax"></a>Sözdizimi

```

#include <locale.h>

```

## <a name="remarks"></a>Açıklamalar

Yerel ayar kategorileri yerelleştirme yordamları tarafından kullanılacak olan bir programın yerel ayar bilgilerinin hangi kısmının belirtmek için kullanılan bildirim sabitleri ' dir. Yerel ayar, programınızın bazı yönlerini özelleştirilebilir konumu (veya ülke/bölge) ifade eder. Yerel ayara bağımlı alanları, örneğin, parasal değerlerin görüntülenme biçimini ve tarihleri biçimlendirme içerir.

|Yerel ayar kategorisi|Etkilenen programın bölümlerini|
|---------------------|-------------------------------|
|`LC_ALL`|Tüm yerel ayara özgü davranışın (tüm kategoriler)|
|`LC_COLLATE`|Davranışını `strcoll` ve `strxfrm` işlevleri|
|`LC_CTYPE`|Karakter işleme işlevleri davranışını (dışında **isdigit**, `isxdigit`, `mbstowcs`, ve `mbtowc`, Etkilenmeyen)|
|`LC_MAX`|Aynı `LC_TIME`|
|`LC_MIN`|Aynı `LC_ALL`|
|`LC_MONETARY`|Biçimlendirme bilgileri tarafından döndürülen para `localeconv` işlevi|
|`LC_NUMERIC`|Ondalık nokta karakteri biçimlendirilen çıkış rutinleri (örneğin, `printf`), veri dönüştürme rutinleri ve tarafından döndürülen parasal biçimlendirme bilgileri `localeconv` işlevi|
|`LC_TIME`|Davranışını `strftime` işlevi|

Bkz: [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) örneği.

## <a name="see-also"></a>Ayrıca Bkz.

[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcoll İşlevleri](../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)