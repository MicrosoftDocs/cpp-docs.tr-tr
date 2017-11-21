---
title: "Derleyici Hatası C3873 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3873
helpviewer_keywords: C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2e95250fd2bf789425585b704f50bd4d1c51b2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3873"></a>Derleyici Hatası C3873
'char': bu karakterin bir tanımlayıcı ilk karakteri olarak izin verilmiyor  
  
 C++ derleyicisi C ++ 11 standart bir tanımlayıcı izin verilen karakter üzerinde izler. Yalnızca belirli aralıkları karakterden ve evrensel karakter adları tanımlayıcıda izin verilir. Bir tanımlayıcıda başlangıç karakteri ek kısıtlamalar. Daha fazla bilgi ve izin verilen karakterler ve evrensel karakter ad aralıkları listesi için bkz: [tanımlayıcıları](../../cpp/identifiers-cpp.md).  
  
 Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kod. / CLR kullanarak derlenmiş kod tanımlayıcılarının izlemelidir [standart ECMA-335: ortak dil altyapısı (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Aşağıdaki örnek C3873 oluşturur:  
  
```  
// C3873.cpp  
int main() {  
   int \u036F_abc;   // C3873, not in allowed range for initial character  
   int abc_\u036F;   // OK, in allowed range for non-initial character  
}  
```