---
title: Karakterleştirme işleci (#@) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9e0c0d140d937b7359ff3abf9c0eae145a89210
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912738"
---
# <a name="charizing-operator-"></a>Karakterleştirme İşleci (#@)
**Microsoft özel**  
  
 Charizing işleci yalnızca makroları bağımsız değişkenlerle kullanılabilir. Varsa **#@** biçimsel parametresi önündeki makrosu tanımında gerçek bağımsız değişkeni tek tırnak işaretleri içine ve makrosu genişletildiğinde karakteri olarak işlem görür. Örneğin:  
  
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