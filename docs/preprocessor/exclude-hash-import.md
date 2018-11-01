---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: 1de1376fbe80147bc9fe01ea83bad81912431310
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498260"
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

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)