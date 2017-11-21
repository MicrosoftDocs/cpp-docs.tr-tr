---
title: "İfadelerdeki diziler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6f4bceac05f72c609c7aef8702c6313572ed6db5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="arrays-in-expressions"></a>İfadelerdeki Diziler
Bir dizi türü bir tanımlayıcı görüntülendiğinde bir ifadede dışında `sizeof`, adresi, (**&**), veya başlatma bir başvuru, ilk dizi öğesi için bir işaretçi dönüştürülür. Örneğin:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 `psz` işaretçisi `szError1` dizisinin ilk öğesine işaret eder. İşaretçilerin aksine, dizilerin değiştirilebilir I-değerleri olmadığına dikkat edin. Bu nedenle aşağıdaki atama geçersizdir:  
  
```  
szError1 = psz;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diziler](../cpp/arrays-cpp.md)