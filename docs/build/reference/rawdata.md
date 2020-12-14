---
description: Bu konuda daha fazla bilgi edinin:/RAWDATA
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
ms.openlocfilehash: efe2001c0170b8539b98902591849dedaf0fb819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225381"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek dosyadaki her bölümün ham içeriğini görüntüler. Bağımsız değişkenler aşağıda gösterildiği gibi, ekran biçimini denetler:

|Bağımsız Değişken|Sonuç|
|--------------|------------|
|1|Varsayılan. İçerikler, yazdırılmış bir gösterimler varsa ASCII karakterleri olarak onaltılık baytlara ve ayrıca görüntülenir.|
|2|İçerik, onaltılı 2 baytlık değerler olarak görüntülenir.|
|4|İçerik, onaltılı 4 baytlık değerler olarak görüntülenir.|
|8|İçerik onaltılık 8 baytlık değerler olarak görüntülenir.|
|SEÇIM|Ham veriler bastırılır. Bu bağımsız değişken,/ALL. çıktısını denetlemek için yararlıdır|
|*Sayı*|Görüntülenen çizgiler, satır başına değerleri tutan bir genişliğe ayarlanır `number` .|

[/GL](gl-whole-program-optimization.md) derleyici seçeneği ile oluşturulan dosyalarda yalnızca [/Headers](headers.md) dumpbin seçeneği kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
