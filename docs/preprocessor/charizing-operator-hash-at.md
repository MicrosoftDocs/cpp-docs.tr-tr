---
title: "Karakterleştirme işleci (#@) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6521322e7a71d8e76b657fb8580157c036e881b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="charizing-operator-"></a>Karakterleştirme İşleci (#@)
**Microsoft Specific**  
  
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