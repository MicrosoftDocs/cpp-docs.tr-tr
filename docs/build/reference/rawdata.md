---
title: -RAWDATA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /rawdata
dev_langs: C++
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0a0d9517bae5bdd1eed6cfafda496643aee666d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [DUMPBIN seçenekleri](../../build/reference/dumpbin-options.md)