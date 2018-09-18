---
title: _fmode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- fmode
- _fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfc89eeda690632979521fa8a4e91c48c8b3c866
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080838"
---
# <a name="fmode"></a>_fmode

`_fmode` Değişkenini metin veya ikili çeviri için varsayılan dosya çevirisi modu ayarlar. Bu genel değişkeni daha güvenli işlevsel sürümleri için kullanım dışı [_get_fmode](../c-runtime-library/reference/get-fmode.md) ve [_set_fmode](../c-runtime-library/reference/set-fmode.md), hangi kullanılmalıdır genel değişken yerine. Stdlıb.h içinde şu şekilde bildirilir.

## <a name="syntax"></a>Sözdizimi

```
extern int _fmode;
```

## <a name="remarks"></a>Açıklamalar

Varsayılan ayar `_fmode` olduğu `_O_TEXT` metin modunda çeviri için. `_O_BINARY` ikili mod ayardır.

Değerini değiştirebilir `_fmode` üç yolla:

- Binmode.obj bağlantıyla. Bu ilk ayarını değiştirir `_fmode` için `_O_BINARY`, hariç tüm dosyalar neden `stdin`, `stdout`, ve `stderr` İkili modda açılacak.

- Çağrı yapmak `_get_fmode` veya `_set_fmode` almak veya ayarlamak için `_fmode` genel değişkeni, sırasıyla.

- Değiştirin `_fmode` programınızda ayarı tarafından doğrudan.

## <a name="see-also"></a>Ayrıca Bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)