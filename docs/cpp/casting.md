---
title: Atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- casting [C++]
- coercion [C++]
- virtual functions [C++], in derived classes [C++]
- static cast operator
- dynamic cast operator
- polymorphic classes [C++]
- classes [C++], polymorphism
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07abd7c6a6a5c646dade15299fe6cfe78d9ff1d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411734"
---
# <a name="casting"></a>Atama
C++ dili, bir sınıf sanal işlevler içeren bir temel sınıftan türetilmişse, temel sınıf türünün işaretçisinin türetilmiş sınıf nesnesinde yer alan sanal işlevlerin uygulamalarını çağırmak için kullanılabilmesini sağlar. Sanal işlevler içeren bir sınıf, bazen "çok biçimli bir sınıf" olarak adlandırılır.  
  
 Türetilmiş bir sınıf türetildiği tüm temel sınıfların tanımlarını içerdiği için bir işaretçi güvenli bir şekilde temel sınıfların herhangi birinin sınıf hiyerarşisine atanabilir. Temel sınıfın işaretçisi göz önünde bulundurulduğunda, işaretçiyi hiyerarşide aşağı doğru atamak güvenli olabilir. İşaret edilen nesne, temel sınıftan türetilen bir türdense güvenlidir. Bu durumda, gerçek nesne "tam nesne" olarak kabul edilir. Temel sınıfın işaretçisinin, tam nesnenin "alt nesnesine" işaret ettiği bildirilir. Örnek olarak aşağıdaki şekilde gösterilen sınıf hiyerarşisini inceleyin.  
  
 ![Sınıf hiyerarşisi](../cpp/media/vc38zz1.gif "vc38ZZ1")  
Sınıf Hiyerarşisi  
  
 `C` türünden bir nesne, aşağıdaki şekilde gösterildiği gibi sanallaştırılabilir.  
  
 ![Sub C sınıfıyla&#45;B ve A nesneleri](../cpp/media/vc38zz2.gif "vc38ZZ2")  
B Alt Nesnesine ve A Alt Nesnesine sahip C Sınıfı  
  
 `C` sınıfının bir örneği göz önünde bulundurulduğunda, bir `B` alt nesnesi ve bir `A` alt nesnesi vardır. `C` ve `A` alt nesneleriyle birlikte `B` örneği, "tam nesne"dir.  
  
 Çalışma zamanı tür bilgileri kullanılarak, bir işaretçinin tam bir nesneyi gerçekten işaret edip etmediği denetlenebilir ve işaretçi hiyerarşisindeki başka bir nesneyi işaret edecek şekilde güvenli olarak atanabilir. [Dynamic_cast](../cpp/dynamic-cast-operator.md) işleci, bu tür atamaları yapmak için kullanılabilir. İşlemi güvenli hale getirmek için gerekli olan çalışma zamanı denetimini de gerçekleştirir.  
  
 Nonpolymorphic türleri dönüştürme için kullandığınız [static_cast](../cpp/static-cast-operator.md) işleci (Bu konuda, statik ve dinamik atama dönüşümleri arasında ve her kullanmak, uygun olduğunda fark açıklanmıştır).  
  
 Bu bölüm aşağıdaki konuları içerir:  
  
-   [Atama İşleçleri](../cpp/casting-operators.md)  
  
-   [Çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfadeler](../cpp/expressions-cpp.md)