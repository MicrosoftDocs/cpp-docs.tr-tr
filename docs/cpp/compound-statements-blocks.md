---
title: "Bileşik deyimler (bloklar) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs: C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c9fc47721ba5cecc8ca9f61f89ecedebaed18ae4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [C++ deyimlerine genel bakış](../cpp/overview-of-cpp-statements.md)