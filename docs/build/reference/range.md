---
description: Daha fazla bilgi için:/RANGE
title: /RANGE
ms.date: 11/04/2016
f1_keywords:
- /RANGE
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
ms.openlocfilehash: 9af54bddde977e92b5256f0835c31afbff1405d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225407"
---
# <a name="range"></a>/RANGE

/RAWDATA veya/DISASMGIBI diğer dumpbin seçenekleriyle birlikte kullanıldığında dumpbin çıkışını değiştirir.

## <a name="syntax"></a>Sözdizimi

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>Parametreler

*Vadk*<br/>
Dumpbin işleminin başlamasını istediğiniz sanal adres.

*vaMax*<br/>
Seçim Dumpbin işleminin bitmesini istediğiniz sanal adres. Belirtilmemişse, dumpbin dosyanın sonuna gider.

## <a name="remarks"></a>Açıklamalar

Bir görüntünün sanal adreslerini görmek için görüntü için eşleme dosyasını (RVA + taban), dumpbin için **/disasm** veya **/Headers** seçeneğini veya Visual Studio hata ayıklayıcısındaki ayrıştırma penceresini kullanın.

## <a name="example"></a>Örnek

Bu örnekte, **/deasm** seçeneğinin görüntüsünü değiştirmek için **/Range** kullanılır. Bu örnekte, başlangıç değeri ondalık sayı olarak ifade edilir ve bitiş değeri onaltılık sayı olarak belirtilir.

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
