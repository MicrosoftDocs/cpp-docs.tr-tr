---
title: _fmode
ms.date: 11/04/2016
f1_keywords:
- fmode
- _fmode
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
ms.openlocfilehash: a41d665eab50203fc3bb176f8bb1bbc30737e844
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741940"
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

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)
