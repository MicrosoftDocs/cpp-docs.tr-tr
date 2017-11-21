---
title: "Derleyici Hatası C3551 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3551
dev_langs: C++
helpviewer_keywords: C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 450bd97efc9cfbf07eac84a3e6a693af698fc64f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3551"></a>Derleyici Hatası C3551
"geç bir dönüş türü belirtilen beklenen"  
  
 Kullanırsanız `auto` anahtar sözcüğü bir işlevin dönüş türü için bir yer tutucu olarak belirtilen geç dönüş türü sağlamanız gerekir. Aşağıdaki örnekte, dönüş türü işlevinin geç belirtilen `myFunction` işaretçi türü dört öğelerinin bir dizi `int`.  
  
```  
auto myFunction()->int(*)[4];   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomatik](../../cpp/auto-cpp.md)