---
title: Atama
ms.date: 11/19/2018
helpviewer_keywords:
- casting [C++]
- coercion [C++]
- virtual functions [C++], in derived classes [C++]
- static cast operator
- dynamic cast operator
- polymorphic classes [C++]
- classes [C++], polymorphism
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
ms.openlocfilehash: bb06db3af6aee031b6cb2d69b38a9404304420fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190150"
---
# <a name="casting"></a>Atama

C++ dili, bir sınıf sanal işlevler içeren bir temel sınıftan türetilmişse, temel sınıf türünün işaretçisinin türetilmiş sınıf nesnesinde yer alan sanal işlevlerin uygulamalarını çağırmak için kullanılabilmesini sağlar. Sanal işlevler içeren bir sınıf, bazen "çok biçimli bir sınıf" olarak adlandırılır.

Türetilmiş bir sınıf türetildiği tüm temel sınıfların tanımlarını içerdiği için bir işaretçi güvenli bir şekilde temel sınıfların herhangi birinin sınıf hiyerarşisine atanabilir. Temel sınıfın işaretçisi göz önünde bulundurulduğunda, işaretçiyi hiyerarşide aşağı doğru atamak güvenli olabilir. İşaret edilen nesne, temel sınıftan türetilen bir türdense güvenlidir. Bu durumda, gerçek nesne "tam nesne" olarak kabul edilir. Temel sınıfın işaretçisinin, tam nesnenin "alt nesnesine" işaret ettiği bildirilir. Örnek olarak aşağıdaki şekilde gösterilen sınıf hiyerarşisini inceleyin.

![Sınıf hiyerarşisi](../cpp/media/vc38zz1.gif "Sınıf hiyerarşisi") <br/>
Sınıf hiyerarşisi

`C` türünden bir nesne, aşağıdaki şekilde gösterildiği gibi sanallaştırılabilir.

![B ve A alt&#45;nesneleriyle C sınıfı](../cpp/media/vc38zz2.gif "B ve A alt&#45;nesneleriyle C sınıfı") <br/>
Alt nesneler B ve A ile C sınıfı

`C` sınıfının bir örneği göz önünde bulundurulduğunda, bir `B` alt nesnesi ve bir `A` alt nesnesi vardır. `C` ve `A` alt nesneleriyle birlikte `B` örneği, "tam nesne"dir.

Çalışma zamanı tür bilgileri kullanılarak, bir işaretçinin tam bir nesneyi gerçekten işaret edip etmediği denetlenebilir ve işaretçi hiyerarşisindeki başka bir nesneyi işaret edecek şekilde güvenli olarak atanabilir. [Dynamic_cast](../cpp/dynamic-cast-operator.md) işleci bu tür atamalar yapmak için kullanılabilir. İşlemi güvenli hale getirmek için gerekli olan çalışma zamanı denetimini de gerçekleştirir.

Polimorfik olmayan türlerin dönüştürülmesi için [static_cast](../cpp/static-cast-operator.md) işlecini kullanabilirsiniz (Bu konu, statik ve dinamik atama dönüştürmeleri arasındaki farkı ve bunların her birini kullanmak için uygun olduğunu açıklamaktadır).

Bu bölümde aşağıdaki konular ele alınmaktadır:

- [Atama işleçleri](../cpp/casting-operators.md)

- [Çalışma zamanı tür bilgileri](../cpp/run-time-type-information.md)

## <a name="see-also"></a>Ayrıca bkz.

[İfadeler](../cpp/expressions-cpp.md)
