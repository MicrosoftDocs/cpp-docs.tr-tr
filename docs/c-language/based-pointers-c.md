---
title: Pointers (C) tabanlı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b414110b0f3367c2b589f82915f417ea7389d738
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="based-pointers-c"></a>Tabanlı İşaretçiler (C)
**Microsoft özel**  
  
 [__based (C++ Başvurusu)](../cpp/based-pointers-cpp.md)  
  
 Microsoft 32-bit ve 64-bit C Derleyicileri için bir temel bir 32 bit veya 64-bit işaretçi temel 32 bit veya 64-bit uzaklığı işaretçidir. Tabanlı adresleme, burada ayrılmış nesneleri bölümleri üzerinde denetim kullanan, böylelikle yürütülebilir dosyasının boyutunu azaltmak ve yürütme hızını artırmak için yararlıdır. Genel olarak, formdur tabanlı bir işaretçi belirtmek için  
  
```  
  
type  
__based(  
base  
)  
declarator  
  
```  
  
 Tabanlı adresleme "işaretçi göre" değişken bir işaretçi belirtimi temel olarak sağlar. Göre daha sonra temel aldığı işaretçi başında başlangıç bellek bölüme bir uzaklık işaretçidir. İşaretçi adreslere dayanarak, yalnızca form işaretçileridir `__based` 32-bit ve 64-bit derlemeleri geçerli anahtar sözcüğü. Bu tür derlemeleri, 32 bit veya 64-bit yer bir 32 bit veya 64-bit tabanı gelen oldukları.  
  
 İşaretçilere göre işaretçilerin bir kullanımı da, işaretçiler içeren kalıcı tanımlayıcılara yöneliktir. İşaretçiye göre işaretçilerden oluşan bağlantılı bir liste diske kaydedilebilir ve daha sonra işaretçiler geçerli kalacak şekilde bellekte başka bir yere yeniden yüklenebilir.  
  
 Aşağıdaki örnek üzerindeki işaretçi dayalı bir işaretçi gösterir.  
  
```  
void *vpBuffer;  
  
struct llist_t  
{  
    void __based( vpBuffer ) *vpData;  
    struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 `vpBuffer` işaretçisine, programda daha sonra ayrılan belleğin adresi atanır. Bağlantılı liste, `vpBuffer` değerine göre yeniden konumlandırılır.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)