---
title: /RAWDATA
ms.date: 11/04/2016
f1_keywords:
- /rawdata
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
ms.openlocfilehash: 02af8df04d80c20c5d7629b51abab6295a21f5e5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816470"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, dosyada her bölümün ham içeriği görüntüler. Bağımsız değişkenler, aşağıda gösterildiği gibi görüntüleme biçimini denetler:

|Bağımsız Değişken|Sonuç|
|--------------|------------|
|1.|Varsayılan. İçeriği yazdırılan gösterimine sahip oldukları onaltılık baytlar ve ayrıca ASCII karakter olarak görüntülenir.|
|2|İçeriği onaltılık 2 baytlık değer olarak görüntülenir.|
|4|İçeriği onaltılık 4 baytlık değer olarak görüntülenir.|
|8|İçeriği onaltılık 8 baytlık değer olarak görüntülenir.|
|YOK|Ham verileri bastırılır. Bu bağımsız değişken çıktısını denetlemek yararlıdır/ALL.|
|*Sayı*|Görüntülenen satır tutan bir genişliğe ayarlanır `number` satır başına değeri.|

Yalnızca [OPTIONAL](headers.md) DUMPBIN seçeneği ile üretilen dosyalar kullanıma [/GL](gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
