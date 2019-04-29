---
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
ms.openlocfilehash: 89609de3fc5584a960480bff83566f5e38c8be1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342490"
---
# <a name="path-field-limits"></a>Yol Alanı Sınırları

## <a name="syntax"></a>Sözdizimi

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler yolu için ve yolun içinde ayrı alanlar için uzunluk üst sınırını tanımlayın.

|Sabit|Açıklama|
|--------------|-------------|
|`_MAX_DIR`|Dizin bileşeni uzunluğunun üst sınırı|
|`_MAX_DRIVE`|Sürücü bileşen uzunluğunun üst sınırı|
|`_MAX_EXT`|Uzantı bileşeni uzunluğunun üst sınırı|
|`_MAX_FNAME`|Dosya adı bileşeni uzunluğunun üst sınırı|
|`_MAX_PATH`|Tam yolunun maksimum uzunluğu|

> [!NOTE]
> C çalışma zamanı yol uzunluğu 32.768 karakter kadar uzunlukta destekler. ancak bu daha uzun yollar destekleyecek şekilde özellikle dosya sistemi, işletim sistemi kadar olacaktır. Alanların toplamı aşmamalıdır `_MAX_PATH` tam için geriye dönük uyumluluk FAT32 dosya sistemleri. Windows NTFS dosya sistemi yolları 32.768 karakter kadar uzunluğunda, ancak yalnızca Unicode API'leri kullanırken destekler. Yol adı uzun kullanırken karakterler yolu ön eki \\ \\? \ ve C çalışma zamanı işlevleri Unicode sürümlerini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)