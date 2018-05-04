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
ms.openlocfilehash: 28691e636f01174ecfe2a9d48b016523fce67f14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="rawdata"></a>/RAWDATA
```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek dosyasında her bölümün ham içeriğini görüntüler. Bağımsız değişkenler aşağıda gösterildiği gibi görünen biçimini kontrol edin:  
  
|Bağımsız Değişken|Sonuç|  
|--------------|------------|  
|1.|Varsayılan. Yazdırılan gösterimi varsa içeriği onaltılık bayt ve ayrıca ASCII karakterleri olarak görüntülenir.|  
|2|İçeriği onaltılık 2-bayt değerleri olarak görüntülenir.|  
|4|İçeriği onaltılık 4-bayt değerleri olarak görüntülenir.|  
|8|İçeriği onaltılık 8-bayt değerleri olarak görüntülenir.|  
|YOK|Ham verileri engellenir. Bu bağımsız değişken çıktısını denetlemek kullanışlıdır/ALL.|  
|*Sayı*|Görüntülenen satırları tutan bir genişliğini ayarlamak `number` satır başına değeri.|  
  
 Yalnızca [/HEADERS](../../build/reference/headers.md) DUMPBIN seçeneği ile üretilen dosyalarda kullanıma [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)