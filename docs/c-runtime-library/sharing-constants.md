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
ms.openlocfilehash: e1dc7879403072113c8b81658165c377a1bf4527
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532827"
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