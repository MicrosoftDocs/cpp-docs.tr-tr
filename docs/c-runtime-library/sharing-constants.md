---
title: Paylaşım Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
ms.openlocfilehash: ecc7e5fc5afaf1d6d97f3ab46be3b1ed3001d8e5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519548"
---
# <a name="sharing-constants"></a>Paylaşım Sabitleri

Dosya Paylaşımı için sabitler modları.

## <a name="syntax"></a>Sözdizimi

```

#include <share.h>
```

## <a name="remarks"></a>Açıklamalar

*Shflag* bağımsız değişken bir veya daha fazla bildirim sabitleri oluşur Paylaşım modu belirler. Bunlar ile birleştirilebilir *oflag* bağımsız değişkenleri (bkz [dosya sabitleri](../c-runtime-library/file-constants.md)).

Aşağıdaki tabloda, sabitleri ve anlamlarını listeler:

|Sabit|Açıklama|
|--------------|-------------|
|`_SH_DENYRW`|Okuma ve dosyaya yazma erişimi engeller|
|`_SH_DENYWR`|Dosya yazma erişimi engeller|
|`_SH_DENYRD`|Dosya okuma erişimi engeller|
|`_SH_DENYNO`|İzinleri okuma ve yazma erişimi|
|`_SH_SECURE`|Güvenli modu ayarlar (paylaşılan okuma, yazma için açar).|

## <a name="see-also"></a>Ayrıca Bkz.

[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)