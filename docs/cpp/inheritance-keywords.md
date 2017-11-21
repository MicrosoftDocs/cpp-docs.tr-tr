---
title: "Devralınan anahtar sözcükler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs: C++
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes [C++]
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes [C++], declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 65d338f642d705fec6f1a45b5e88f05c1ee55cc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="inheritance-keywords"></a>Devralınan Anahtar Sözcükler
**Microsoft özel**  
  
```  
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;  
```  
  
 burada:  
  
 *sınıf adı*  
 Bildirilen sınıfın adı.  
  
 C++ sınıfının tanımını önce bir sınıf üyesi için bir işaretçi bildirin olanak tanır. Örneğin:  
  
```  
class S;  
int S::*p;  
```  
  
 Yukarıdaki kod `p` sınıfı S. tamsayı üyesi için bir işaretçi olarak bildirilir Ancak, `class S` sahip bu kodda; tanımlanan değil ancak yalnızca bildirildi. Derleyici böyle bir işaretçi karşılaştığında, işaretçi genelleştirilmiş bir gösterimini yapmanız gerekir. Belirtilen devralma model bağımlı gösteriminin boyutudur. Bir devralma modeli derleyici belirtmek için dört yolu vardır:  
  
-   Altında IDE'de **işaretçi-üye gösterimi**  
  
-   Komut satırını kullanarak [/vmg](../build/reference/vmb-vmg-representation-method.md) geçiş  
  
-   Kullanarak [pointers_to_members](../preprocessor/pointers-to-members.md) pragması  
  
-   Devralma anahtar sözcükleri kullanarak `__single_inheritance`, `__multiple_inheritance`, ve `__virtual_inheritance`. Bu teknik sınıfı başına temelinde devralma modeli denetler.  
  
    > [!NOTE]
    >  Her zaman bir işaretçi bir sınıf üyesi için sınıf tanımladıktan sonra bildirirseniz, bu seçeneklerden birini kullanmanız gerekmez.  
  
 Sınıf tanımı önce bir sınıf üyesi için bir işaretçi bildirme boyutunu ve sonuçta elde edilen yürütülebilir dosyasının hızını etkiler. Devralma bir sınıf tarafından daha büyük bir işaretçi sınıfı ve daha geniş bir üyesi için işaretçiyi yorumlamak için gereken kod göstermek için gereken bayt sayısını kullanılan daha karmaşık. Tek devralma az karmaşıktır ve sanal devralma en karmaşık.  
  
 Yukarıdaki örnekte değiştirilirse:  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 komut satırı seçenekleri veya pragmaları, üyeleri işaretçileri bakılmaksızın `class S` en küçük olası gösterimi kullanır.  
  
> [!NOTE]
>  Bir sınıf işaretçi-üye gösterimi aynı iletme bildirimi o sınıf üyelerine işaretçileri bildirir her bir çeviri birim gerçekleşeceğini ve üye işaretçileri bildirilen önce bildirimi olmamalıdır.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)