---
title: "İmzalı bit düzeyinde işlemler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92750e2e309fd0ceaf06e81cc9483c0785795019
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="signed-bitwise-operations"></a>İmzalı Bit Düzeyinde İşlemler
**ANSI 3.3** imzalı tamsayılar Bitsel işlemlerinin sonuçları  
  
 İşaretli tamsayılarda bit düzeyinde işlemler, işaretsiz tamsayılarda bit düzeyinde işlemlerle aynı şekilde çalışır. Örneğin, `-16 & 99` binary olarak ifade edilebilir  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Bit düzeyinde AND'in sonucu 96'dır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tam Sayılar](../c-language/integers.md)