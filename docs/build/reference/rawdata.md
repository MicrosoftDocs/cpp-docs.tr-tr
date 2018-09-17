---
title: -RAWDATA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rawdata
dev_langs:
- C++
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38677b0e67ddaec5b6ef0e3fcffed1bed27826b6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707180"
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