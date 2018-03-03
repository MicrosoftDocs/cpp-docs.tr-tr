---
title: "Bileşik deyimler (bloklar) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36dc3c25d5f8bbd37ebfaa3458c07f6948492817
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compound-statements-blocks"></a>Bileşik Deyimler (Bloklar)
Bileşik deyim süslü ayraçlar içindeki sıfır veya daha fazla deyimleri oluşur (**{}**). Bileşik deyim, deyim beklenen herhangi bir yerde kullanılabilir. Bileşik deyimlere genellikle "blok" adı verilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki örnek, bileşik deyim olarak kullanır. *deyimi* parçası **varsa** deyimi (bkz [if deyimi](../cpp/if-else-statement-cpp.md) söz dizimi hakkında ayrıntılar için):  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
{
    Balance -= Amount;  
}
```  
  
> [!NOTE]
>  Bir bildirim bir deyim olduğundan, bir bildirimi deyimlerinde biri olabilir *deyimi listesi*. Sonuç olarak, bileşik deyim içinde bildirilen, ancak açıkça statik olarak bildirilmeyen adların yerel kapsamı ve (nesneler için) ömrü vardır. Bkz: [kapsam](../cpp/scope-visual-cpp.md) adları yerel kapsamlı işlenmesi hakkındaki ayrıntılar için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)