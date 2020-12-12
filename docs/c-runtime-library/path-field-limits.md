---
description: 'Daha fazla bilgi edinin: yol alanı sınırları'
title: Yol Alanı Sınırları
ms.date: 11/04/2016
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
ms.openlocfilehash: 41698d946e45a78f9b89f40fdd3c7c58af5d4354
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213487"
---
# <a name="path-field-limits"></a>Yol Alanı Sınırları

## <a name="syntax"></a>Syntax

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler yol için en fazla uzunluğu ve yol içindeki tek alanları tanımlar.

|Sabit|Anlamı|
|--------------|-------------|
|`_MAX_DIR`|En fazla dizin bileşeni uzunluğu|
|`_MAX_DRIVE`|En fazla sürücü bileşeni uzunluğu|
|`_MAX_EXT`|En fazla uzantı bileşeni uzunluğu|
|`_MAX_FNAME`|Dosya adı bileşen uzunluğu üst sınırı|
|`_MAX_PATH`|Tam yol uzunluğu üst sınırı|

> [!NOTE]
> C çalışma zamanı, en fazla 32768 karakter uzunluğunda olan yol uzunluklarını destekler, ancak bu daha uzun yolları desteklemek için işletim sistemine, özellikle de dosya sistemine kadar sahiptir. Alanların toplamı, `_MAX_PATH` FAT32 dosya sistemleriyle tam geriye dönük uyumluluk için aşmamalıdır. Windows NTFS dosya sistemi, en fazla 32768 karakter uzunluğunda olan yolları yalnızca Unicode API 'Leri kullanılırken destekler. Uzun yol adları kullanırken, yolu? \ ile önek olarak adlandırır \\ \\ ve C çalışma zamanı işlevlerinin Unicode sürümlerini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Global sabitler](../c-runtime-library/global-constants.md)
