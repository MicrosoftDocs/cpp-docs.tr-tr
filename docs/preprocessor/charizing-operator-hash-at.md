---
title: "Karakterleştirme işleci (#@) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#@'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 933e97732462b61919d9e5a1e73f2a72d26ea01b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="charizing-operator-"></a>Karakterleştirme İşleci (#@)
**Microsoft özel**  
  
 Charizing işleci yalnızca makroları bağımsız değişkenlerle kullanılabilir. Varsa  **#@**  biçimsel parametresi önündeki makrosu tanımında gerçek bağımsız değişkeni tek tırnak işaretleri içine ve makrosu genişletildiğinde karakteri olarak işlem görür. Örneğin:  
  
```  
#define makechar(x)  #@x  
```  
  
 deyim neden olur.  
  
```  
a = makechar(b);  
```  
  
 için genişletilecek  
  
```  
a = 'b';  
```  
  
 Tek tırnak karakteri ile charizing işleci kullanılamaz.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)