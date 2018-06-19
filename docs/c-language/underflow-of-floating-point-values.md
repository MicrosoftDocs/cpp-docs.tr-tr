---
title: Kayan nokta değerlerinin yetersiz kalması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ceaa41dcaca88c7857a03c16ccccabdba086fd0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387830"
---
# <a name="underflow-of-floating-point-values"></a>Kayan Nokta Değerlerinin Yetersiz Kalması
**ANSI 4.5.1** olup matematik işlevleri set tamsayı ifadesi `errno` makrosu değerine `ERANGE` underflow aralığı hatalar hakkında  
  
 Bir kayan nokta yetersizliği `errno` ifadesini `ERANGE` olarak ayarlamaz. Bir değer sıfıra yaklaştığında ve en sonunda yetersiz kaldığında, değer sıfır olarak ayarlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık İşlevleri](../c-language/library-functions.md)