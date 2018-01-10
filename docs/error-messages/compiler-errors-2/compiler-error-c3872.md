---
title: "Derleyici Hatası C3872 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3872
dev_langs: C++
helpviewer_keywords: C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 327a0300e8df9cbc225e130d69bfe359359a0d6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3872"></a>Derleyici Hatası C3872
'char': bu karakterin bir tanımlayıcı izin verilmiyor  
  
 C++ derleyicisi C ++ 11 standart bir tanımlayıcı izin verilen karakter üzerinde izler. Yalnızca belirli aralıkları karakterden ve evrensel karakter adları tanımlayıcıda izin verilir. Bir tanımlayıcıda başlangıç karakteri ek kısıtlamalar. Daha fazla bilgi ve izin verilen karakterler ve evrensel karakter ad aralıkları listesi için bkz: [tanımlayıcıları](../../cpp/identifiers-cpp.md).  
  
 Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kod. / CLR kullanarak derlenmiş kod tanımlayıcılarının izlemelidir [standart ECMA-335: ortak dil altyapısı (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Aşağıdaki örnek C3872 oluşturur:  
  
```  
// C3872.cpp  
int main() {  
   int abc_\u0040;   // C3872, U+0040 is in base char set  
   int abc_\u3001;   // C3872, U+3001 is not in allowed range  
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range  
}  
```