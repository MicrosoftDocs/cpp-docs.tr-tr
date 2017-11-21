---
title: "Kayan nokta değerlerinin yetersiz kalması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f74624f935c9a1384c1c4992004b12c7847e9fd2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="underflow-of-floating-point-values"></a>Kayan Nokta Değerlerinin Yetersiz Kalması
**ANSI 4.5.1** olup matematik işlevleri set tamsayı ifadesi `errno` makrosu değerine `ERANGE` underflow aralığı hatalar hakkında  
  
 Bir kayan nokta yetersizliği `errno` ifadesini `ERANGE` olarak ayarlamaz. Bir değer sıfıra yaklaştığında ve en sonunda yetersiz kaldığında, değer sıfır olarak ayarlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık işlevleri](../c-language/library-functions.md)