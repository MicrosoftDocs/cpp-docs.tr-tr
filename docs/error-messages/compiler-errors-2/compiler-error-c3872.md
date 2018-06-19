---
title: Derleyici Hatası C3872 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3872
dev_langs:
- C++
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3259e87eb8939129ebc84c0a08acab2c7d7c509
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270168"
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