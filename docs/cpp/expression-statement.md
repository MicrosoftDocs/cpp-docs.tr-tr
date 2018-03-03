---
title: "İfade deyimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e627e107df850f31a9cf04981795edd1185c0ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)