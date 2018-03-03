---
title: "İfadelerdeki diziler | Microsoft Docs"
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
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29f6e16e665d8076ed5a1fe593e1bb9437f1406a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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