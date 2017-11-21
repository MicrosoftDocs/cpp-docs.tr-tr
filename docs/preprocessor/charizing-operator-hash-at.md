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
ms.openlocfilehash: 1920d8183607140ebe38aaf56a447bc9cd3010f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Ön İşlemci işleçleri](../preprocessor/preprocessor-operators.md)