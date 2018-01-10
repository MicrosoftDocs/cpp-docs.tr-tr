---
title: "Bit alanları deposu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1be04ba4c68b2629a5e765788af95a203ae06b34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-bit-fields"></a>Bit Alanları Deposu
**ANSI 3.5.2.1** int içinde bit alanları ayırma sırasını  
  
 Bit alanları, bir tamsayı içinde en az önemli olan bitten en önemli bite doğru ayrılır. Aşağıdaki kodda  
  
```  
struct mybitfields  
{  
   unsigned a : 4;  
   unsigned b : 5;  
   unsigned c : 7;  
} test;  
  
int main( void )  
{  
   test.a = 2;  
   test.b = 31;  
   test.c = 0;  
}  
```  
  
 bitler aşağıdaki gibi düzenlenir:  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 80x86 işlemcileri tamsayı değerlerinin düşük baytını yüksek bayttan önce depoladığı için yukarıdaki 0x01F2 tamsayısı, fiziksel bellekte arkasından 0x01 gelen 0xF2 olarak depolanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)