---
title: "Microsoft'a özgü değiştiriciler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f9533ffc2d21c3e8ee006fc97f7c61f4cb41115
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="microsoft-specific-modifiers"></a>Microsoft'a Özgü Değiştiriciler
Bu bölümde aşağıdaki alanlarda C++ için Microsoft özgü uzantılar açıklanmaktadır:  
  
-   [Tabanlı adresleme](../cpp/based-addressing.md), bir işaretçi içinden diğer işaretçileri uzaklığı temel olarak kullanarak uygulama  
  
-   [Çağırma kurallarını işlevi](../cpp/calling-conventions.md)  
  
-   Genişletilmiş depolama sınıfı öznitelikleri ile bildirilen [__declspec](../cpp/declspec.md) anahtar sözcüğü  
  
-   [__W64](../cpp/w64.md) anahtar sözcüğü  
  
 Microsoft'a özgü anahtar sözcükler çoğunu türetilmiş form türleri için Bildirimciler değiştirmek için kullanılabilir. Bildirimciler hakkında daha fazla bilgi için bkz: [Bildirimciler](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
### <a name="microsoft-specific-keywords"></a>Microsoft'a özgü anahtar sözcükler  
  
|Anahtar sözcüğü|Açıklama|Türetilmiş türler oluşturmak için kullanılan?|  
|-------------|-------------|---------------------------------|  
|[__based](../cpp/based-grammar.md)|İzleyen ad bildirimde bulunan 32-bit tabanı bir 32 bit uzaklık bildirir.|Evet|  
|[__cdecl](../cpp/cdecl.md)|İzleyen ad C adlandırma ve çağırma kuralları kullanır.|Evet|  
|[__declspec](../cpp/declspec.md)|Microsoft'a özgü depolama sınıfı öznitelik izleyen ad belirtir.|Hayır|  
|[__fastcall](../cpp/fastcall.md)|İzleyen ad bağımsız değişken geçirme yığını yerine kaydeder, kullanılabilir olduğunda kullanan bir işlev bildirir.|Evet|  
|[__restrict](../cpp/extension-restrict.md)|__Declspec benzer ([kısıtlamak](../cpp/restrict.md)), ancak değişkenlerini kullanın.|Hayır|  
|[__stdcall](../cpp/stdcall.md)|İzleyen ad standart çağırma uyan bir işlev belirtir.|Evet|  
|[__w64](../cpp/w64.md)|Bir veri türü bir 64 bit derleyici daha büyük olarak işaretler.|Hayır|  
|[__unaligned](../cpp/unaligned.md)|Bir işaretçi bir türü veya diğer veri Hizalanmadığını belirtir...|Hayır|  
|[__vectorcall](../cpp/vectorcall.md)|İzleyen ad SSE kaydeder, kullanılabilir olduğunda, bağımsız değişken geçirme yığını yerine dahil olmak üzere kaydeder kullanan bir işlev bildirir.|Evet|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)