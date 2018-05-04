---
title: İmzalı bit düzeyinde işlemler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3ddd1c32beb5660fd1fa3c0160756734b4c1923
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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