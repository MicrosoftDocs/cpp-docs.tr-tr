---
title: Dosya öznitelik sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- A_HIDDEN
- _A_NORMAL
- _A_SUBDIR
- _A_RDONLY
- A_NORMAL
- A_SUBDIR
- _A_SYSTEM
- c.constants.file
- _A_HIDDEN
- A_RDONLY
- _A_ARCH
- A_ARCH
dev_langs:
- C++
helpviewer_keywords:
- constants [C++], file attributes
- file attribute constants [C++]
- _A_SYSTEM constant
- files [C++], file attribute constants
- _A_SUBDIR constant
- _A_ARCH constant
- _A_NORMAL constant
- _A_HIDDEN constant
- _A_RDONLY constant
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42745d25c0f743fa1a11226d5cfe433327c8ff2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077054"
---
# <a name="file-attribute-constants"></a>Dosya Öznitelik Sabitleri

## <a name="syntax"></a>Sözdizimi

```

#include <io.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler geçerli işlev tarafından belirtilen dizin ve dosya özniteliklerini belirtin.

Öznitelik, aşağıdaki bildirim sabitleriyle gösterilir:

|Sabit|Açıklama|
|-|-|
|`_A_ARCH`| Arşiv. Dosya değiştirildi ve yedekleme komutu tarafından işaretli olduğunda ayarlayın. Değer: 0x20|
|`_A_HIDDEN`| Gizli bir dosya. Normalde /AH seçeneği kullanılmadığı sürece DIR komutu ile görülür. Bu öznitelik dosyalarıyla yanı sıra normal dosya hakkındaki bilgileri döndürür. Değer: 0x02|
|`_A_NORMAL`| Normal. Dosya okuma veya yazma kısıtlama. Değer: 0x00|
|`_A_RDONLY`| Salt okunur. Dosya yazma için açılamıyor ve aynı ada sahip bir dosya oluşturulamıyor. Değer: 0x01|
|`_A_SUBDIR`| Alt. Değer: 0x10|
|`_A_SYSTEM`| Sistem dosyası. Normalde /AS seçeneği kullanılmadığı sürece DIR komutu ile görülür. Değer: 0x04|

Birden fazla sabit veya işleci ile birleştirilebilir (&#124;).

## <a name="see-also"></a>Ayrıca Bkz.

[fileName İşlevleri Ara](../c-runtime-library/filename-search-functions.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)