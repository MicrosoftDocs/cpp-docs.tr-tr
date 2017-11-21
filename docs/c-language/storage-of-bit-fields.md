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
ms.openlocfilehash: b984448e55380dd3f2223b098a048fec57cb0ba6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Yapılar, birleşimler, numaralandırmalar ve Bit alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)