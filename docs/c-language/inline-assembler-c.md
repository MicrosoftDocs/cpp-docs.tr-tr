---
title: Inline assembler (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __asm keyword [C]
- inline assembler [C]
ms.assetid: 821acc77-60b1-434c-ba54-2ba930a25ab4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22d27d5ad63bd92558569bfa211e3c58d5677a27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inline-assembler-c"></a>Satır İçi Derleyicisi (C)
**Microsoft özel**  
  
 Satır içi derleyici, fazladan derleme ve bağlantı adımları olmaksızın, doğrudan C kaynak programlarınıza derleme dili yönergeleri eklemenize olanak verir. Satır içi derleyici, derleyici içine eklenmiştir içinde yerleşik olarak bulunur, böylece Microsoft Macro Assembler (MASM) gibi ayrı bir derleyici gerekmez.  
  
 Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. Ve derleme kodu C ifadeleri ile birleştirilebildiğinden, tek başına C'de zor ya da olanaksız olan görevleri yapabilir.  
  
 `__asm` anahtar sözcüğü satır içi derleyiciyi çağırır ve bir C deyiminin geçerli olduğu her durumda görünebilir. Tek başına bulunamaz. Derleme yönerge, küme ayraçları veya, çok az içine yönergeleri grubu tarafından gelmelidir küme ayraçları boş bir çifti. Terim "`__asm` blok" Buraya herhangi bir yönerge veya desteklemediğini köşeli parantez içindeki yönergeleri grubu başvuruyor.  
  
 Aşağıdaki kod ayraç içine alınmış basit bir `__asm` bloğudur. (Kod, bir özel işlev giriş sırasıdır.)  
  
```  
__asm  
{  
   push ebp  
   mov  ebp, esp  
   sub  esp, __LOCAL_SIZE  
}  
```  
  
 Alternatif olarak, koyabilirsiniz `__asm` her derleme yönergesi önünde:  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 `__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE   
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev Öznitelikleri](../c-language/function-attributes.md)