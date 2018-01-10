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
ms.workload: cplusplus
ms.openlocfilehash: 475ec5a827a1453a6f9474762d5be41299fc87e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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