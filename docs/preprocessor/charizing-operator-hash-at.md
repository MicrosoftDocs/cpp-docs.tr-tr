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
ms.openlocfilehash: c6aa18936497f0415da331697aceb26f26345500
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42466338"
---
# <a name="charizing-operator-"></a>Karakterleştirme İşleci (#@)
**Microsoft'a özgü**  
  
Karakter haline getirme işleci yalnızca makrolar bağımsız değişkenlerle kullanılabilir. Varsa `#@` biçimsel parametre önündeki Makro tanımında gerçek bağımsız değişkeni tek tırnak işareti içine alınmış ve makro genişletildiğinde bir karakter olarak kabul edilir. Örneğin:  
  
```  
#define makechar(x)  #@x  
```  
  
deyim neden olur  
  
```  
a = makechar(b);  
```  
  
değerine genişletilmesi  
  
```  
a = 'b';  
```  
  
Tek tırnak karakteri karakter haline getirme işleci ile kullanılamaz.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)