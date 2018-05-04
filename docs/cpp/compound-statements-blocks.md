---
title: Bileşik deyimler (bloklar) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a8823935ee2f871cdc033aec23f05fc108244e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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