---
title: "Numaralandırmalar (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3a95af557dd416d99368dbd1ab51495e0bd1d85
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="enums-ccx"></a>Numaralandırmalar (C + +/ CX)
C + +/ CX destekleyen `public enum class` standart C++ işlevdedir olan anahtar sözcük `scoped  enum`. Kullanarak bildirilmiş bir numaralandırıcı kullandığınızda `public enum class` anahtar sözcüğü, her bir numaralandırıcı değeri kapsam için numaralandırma tanıtıcısı kullanmalısınız.  
  
### <a name="remarks"></a>Açıklamalar  
 A `public enum class` , bir erişim belirteci gibi yok `public`, standart bir C++ kabul edilir [enum kapsamlı](../cpp/enumerations-cpp.md).  
  
 A `public enum class` veya `public enum struct` Windows Runtime türü Int32 veya bayrakları enum uint32 olmasını gerektirse de, bildirimi herhangi bir tam sayı türde bir temel alınan tür sahip olabilir. Aşağıdaki söz dizimini bölümünü açıklar bir `public enum class` veya `public enum struct`.  
  
 Bu örnek, bir ortak enum sınıf tanımlama gösterilmektedir:  
  
 [!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]  
  
 Sonraki Bu örnek, kullanma gösterir:  
  
 [!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]  
  
### <a name="examples"></a>Örnekler  
 Sonraki örnekler enum bildirmeyi Göster  
  
 [!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]  
  
 Aşağıdaki örnek, karşılaştırmaları gerçekleştirir ve sayısal eşdeğerleri atama gösterilmektedir. Dikkat Numaralandırıcı kullanımını `One` tarafından kapsamlı `Enum1` numaralandırma tanıtıcısı ve Numaralandırıcı `First` tarafından kapsamlı `Enum2`.  
  
 [!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)