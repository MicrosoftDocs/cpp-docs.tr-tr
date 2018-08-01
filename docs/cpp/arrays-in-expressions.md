---
title: İfadelerdeki diziler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b792bc02cf620cbd961830a99e35ae0c61898fed
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408694"
---
# <a name="arrays-in-expressions"></a>İfadelerdeki Diziler
Bir dizi türünde bir tanımlayıcısı göründüğünde bir ifadede dışında `sizeof`, adres (**&**), veya başlatma, bir başvurunun ilk dizi öğesinin işaretçisine dönüştürülür. Örneğin:  
  
```cpp 
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 `psz` işaretçisi `szError1` dizisinin ilk öğesine işaret eder. İşaretçilerin aksine, dizilerin değiştirilebilir I-değerleri olmadığına dikkat edin. Bu nedenle aşağıdaki atama geçersizdir:  
  
```cpp 
szError1 = psz;  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Diziler](../cpp/arrays-cpp.md)