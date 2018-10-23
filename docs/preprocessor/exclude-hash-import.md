---
title: (#import) hariç | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c345d9268f63a714eeae4beff78a7ac39ce545a1
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807906"
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