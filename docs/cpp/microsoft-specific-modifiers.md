---
title: Microsoft'a özgü değiştiriciler | Microsoft Docs
ms.custom: ''
ms.date: 08/16/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3dfc57e1d6af11628b37823f2452ee2b65f8a7f
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42465648"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft'a Özgü Değiştiriciler
Bu bölüm, C++ aşağıdaki alanlarda Microsoft'a özel uzantıları açıklar:  
  
-   [Tabanlı adresleme](based-addressing.md), yöntem bir işaretçi, diğer işaretçilerin uzak olabileceği bir temel olarak kullanma  
  
-   [İşlev çağırma kuralları](calling-conventions.md)  
  
-   Genişletilmiş depolama sınıfı öznitelikleri ile bildirilen [__declspec](declspec.md) anahtar sözcüğü  
  
-   [__W64](w64.md) anahtar sözcüğü  

### <a name="microsoft-specific-keywords"></a>Microsoft'a özgü anahtar sözcükler  

Microsoft'a özgü anahtar sözcüklerin çoğu, bildirimcileri türetilmiş türler biçimlendirecek şekilde değiştirmek için kullanılabilir. Bildirimciler hakkında daha fazla bilgi için bkz: [Bildirimciler](overview-of-declarators.md).  

|Anahtar sözcüğü|Açıklama|Türetilmiş türler oluşturmak için kullanılır?|   
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|İzleyen ad bildirimdeki 32-bit tabana bir 32-bit uzaklığı bildirir.|Evet|   
|[__cdecl](cdecl.md)|İzleyen ad, C adlandırma ve çağırma kuralları kullanır.|Evet|      
|[__declspec](declspec.md)|İzleyen ad, Microsoft'a özgü depolama sınıfı özniteliğini belirtir.|Hayır|    
|[__fastcall](fastcall.md)|İzleyen ad, bağımsız değişken geçirme yığını yerine kayıtları kullanılabilir olduğunda, kullanan bir işlev bildirir.|Evet|   
|[__restrict](extension-restrict.md)|Benzer şekilde __declspec ([kısıtlama](restrict.md)), ancak değişkenlerde kullanmak için.|Hayır|      
|[__stdcall](stdcall.md)|İzleyen ad, standart çağırma kuralına uyan bir işlevi belirtir.|Evet|     
|[__w64](w64.md)|Bir veri türü, bir 64 bit derleyicide daha büyük olarak işaretler.|Hayır|    
|[__unaligned](unaligned.md)|Bir işaretçi türü veya diğer verilere Hizalanmadığını belirtir...|Hayır|      
|[__vectorcall](vectorcall.md)|İzleyen ad, kullanılabilir olduğunda, bağımsız değişken geçirme yığını yerine SSE kayıtları da dahil olmak üzere kayıtları kullanan bir işlev bildirir.|Evet|      
    
## <a name="see-also"></a>Ayrıca Bkz.     
 [C++ Dil Başvurusu](cpp-language-reference.md)