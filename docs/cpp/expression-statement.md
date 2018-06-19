---
title: İfade deyimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60879ca8792e3259a69b7a9a3de6cd83dce0d6d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411594"
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