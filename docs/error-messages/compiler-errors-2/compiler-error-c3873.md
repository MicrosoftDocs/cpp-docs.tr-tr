---
title: Derleyici Hatası C3873 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bec37b8fb00aedd83d91f1d001d77c42679ec038
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269441"
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