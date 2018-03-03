---
title: "Derleyici Hatası C3873 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adbc98bd40b6dcfa4640c416b5ec38640b0ee822
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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