---
description: 'Daha fazla bilgi edinin: dosya özniteliği sabitleri'
title: Dosya Öznitelik Sabitleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 8b57549b4a21cc5d699f933009c575b3f3fca81d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306371"
---
# <a name="file-attribute-constants"></a>Dosya Öznitelik Sabitleri

## <a name="syntax"></a>Syntax

```
#include <io.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler, işlev tarafından belirtilen dosyanın veya dizinin geçerli özniteliklerini belirtir.

Öznitelikler aşağıdaki bildirim sabitleriyle temsil edilir:

|Sabit|Açıklama|
|-|-|
|`_A_ARCH`| Arşivliyorsanız. Dosya her değiştirildiğinde ayarlanır ve BACKUP komutu tarafından temizlenir. Değer: 0x20|
|`_A_HIDDEN`| Gizli dosya. /AH seçeneği kullanılmadığı takdirde normalde DIR komutuyla görünmez. Bu özniteliğe sahip dosyaların yanı sıra normal dosyalarla ilgili bilgileri döndürür. Değer: 0x02|
|`_A_NORMAL`| Olağan. Dosya, kısıtlama olmadan okunabilir veya yazılabilir. Değer: 0x00|
|`_A_RDONLY`| Salt okunur. Dosya yazma için açılamıyor ve aynı ada sahip bir dosya oluşturulamıyor. Değer: 0x01|
|`_A_SUBDIR`| Dizin. Değer: 0x10|
|`_A_SYSTEM`| Sistem dosyası. /AS seçeneği kullanılmadığı sürece normalde DIR komutuyla görülmez. Değer: 0x04|

Birden çok sabit veya işleci (&#124;) ile birleştirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Dosya adı arama Işlevleri](../c-runtime-library/filename-search-functions.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
