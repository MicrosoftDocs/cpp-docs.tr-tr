---
title: "Belirteçlerin değerlendirmesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be73ad565b3e240ceb21a9c7e3d185f327524d19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="evaluation-of-tokens"></a>Belirteçlerin Değerlendirmesi
Derleyici belirteçleri yorumlarken, bir sonraki belirtece geçmeden önce tek bir belirtece olabildiğince çok karakteri dahil eder. Bu davranış nedeniyle, belirteçler boşlukla düzgün bir şekilde ayrılmamışsa derleyici bunları istediğiniz gibi yorumlamayabilir. Aşağıdaki ifadeyi göz önünde bulundurun:  
  
```  
i+++j  
```  
  
 Bu örnekte, derleyici önce üç artı işaretinden olası en uzun işleci (`++`) oluşturur, ardından kalan artı işaretini ek işleç (`+`) olarak işler. Bu nedenle, ifade `(i++) + (j)` olarak değil, `(i) + (++j)` olarak yorumlanır. Bu ve benzer durumlarda, belirsizlikten kaçınmak ve uygun ifade değerlendirmesi sağlamak için boşluk ve parantezler kullanın.  
  
 **Microsoft özel**  
  
 C derleyicisi, bir CTRL + Z karakterini dosya sonu göstergesi olarak değerlendirir. CTRL+Z'den sonra gelen metni yoksayar.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Belirteçleri](../c-language/c-tokens.md)