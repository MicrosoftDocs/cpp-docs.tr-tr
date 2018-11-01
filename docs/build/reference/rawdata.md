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
ms.openlocfilehash: 91fa1e26ca159f23c848efc6bf46afdea2a8bc52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621487"
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

Yalnızca [OPTIONAL](../../build/reference/headers.md) DUMPBIN seçeneği ile üretilen dosyalar kullanıma [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)