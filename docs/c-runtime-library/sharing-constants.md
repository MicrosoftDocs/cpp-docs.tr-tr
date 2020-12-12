---
description: 'Daha fazla bilgi edinin: sabitleri paylaşma'
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
ms.openlocfilehash: 7cda55d16a9b59c30e9fdbce47c565552839e792
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176177"
---
# <a name="sharing-constants"></a>Paylaşım Sabitleri

Dosya paylaşım modları için sabitler.

## <a name="syntax"></a>Syntax

```
#include <share.h>
```

## <a name="remarks"></a>Açıklamalar

*Shflag* bağımsız değişkeni, bir veya daha fazla bildirim sabitinden oluşan paylaşım modunu belirler. Bunlar, *oflag* bağımsız değişkenleriyle birleştirilebilir (bkz. [Dosya sabitleri](../c-runtime-library/file-constants.md)).

Aşağıdaki tabloda sabitler ve anlamları listelenmektedir:

|Sabit|Anlamı|
|--------------|-------------|
|`_SH_DENYRW`|Dosyaya okuma ve yazma erişimini reddeder|
|`_SH_DENYWR`|Dosyaya yazma erişimini reddeder|
|`_SH_DENYRD`|Dosyaya okuma erişimini reddeder|
|`_SH_DENYNO`|Okuma ve yazma erişimine izin verir|
|`_SH_SECURE`|Güvenli modu (paylaşılan okuma, dışlamalı yazma erişimi) ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
