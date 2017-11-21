---
title: "İfade deyimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 80493922076514ce254d01a97dd0c86f51c92ac1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-statement"></a>İfade Deyimi
İfade deyimleri, ifadelerin değerlendirilmesine neden olur. İfade deyiminin sonucunda denetim aktarımı veya yineleme gerçekleşmez.  
  
 İfade deyimine yönelik sözdizimi  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir ifade deyimindeki tüm ifadeler değerlendirilir ve sonraki ifade yürütülmeden önce tüm yan etkiler tamamlanır. En yaygın ifade deyimleri atamalar ve işlev çağrılarıdır.  İfade isteğe bağlı olduğundan, tek başına bir noktalı virgül olarak adlandırılan bir boş ifade deyimi değerlendirilir [null](../cpp/null-statement.md) deyimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ deyimlerine genel bakış](../cpp/overview-of-cpp-statements.md)