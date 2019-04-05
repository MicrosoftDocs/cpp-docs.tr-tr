---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: d6a320089d5954b2cf1d0d96ae1f37656f2ddd58
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032394"
---
# <a name="exclude-import"></a>hariç tutmak (\#içeri aktarma)

**C++ özgü**

Öğeleri, oluşturulan tür kitaplığı üstbilgi dosyalarından çıkarır.

## <a name="syntax"></a>Sözdizimi

```
exclude("Name1"[, "Name2",...])
```

### <a name="parameters"></a>Parametreler

*Name1*<br/>
Çıkarılacak ilk öğe.

*Name2*<br/>
Çıkarılacak ikinci öğe (gerekirse).

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. Bu öznitelik, her biri çıkarılacak üst düzey tür kitaplığı öğesi olan herhangi bir sayıda bağımsız değişken alabilir.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import Öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Yönergesi](../preprocessor/hash-import-directive-cpp.md)