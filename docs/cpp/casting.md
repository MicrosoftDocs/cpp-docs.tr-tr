---
title: Atama
ms.date: 11/04/2016
helpviewer_keywords:
- casting [C++]
- coercion [C++]
- virtual functions [C++], in derived classes [C++]
- static cast operator
- dynamic cast operator
- polymorphic classes [C++]
- classes [C++], polymorphism
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
ms.openlocfilehash: eb309319a4af6d604d8558552ce313ba1d0fb629
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560803"
---
# <a name="casting"></a>Atama

C++ dili, bir sınıf sanal işlevler içeren bir temel sınıftan türetilmişse, temel sınıf türünün işaretçisinin türetilmiş sınıf nesnesinde yer alan sanal işlevlerin uygulamalarını çağırmak için kullanılabilmesini sağlar. Sanal işlevler içeren bir sınıf, bazen "çok biçimli bir sınıf" olarak adlandırılır.

Türetilmiş bir sınıf türetildiği tüm temel sınıfların tanımlarını içerdiği için bir işaretçi güvenli bir şekilde temel sınıfların herhangi birinin sınıf hiyerarşisine atanabilir. Temel sınıfın işaretçisi göz önünde bulundurulduğunda, işaretçiyi hiyerarşide aşağı doğru atamak güvenli olabilir. İşaret edilen nesne, temel sınıftan türetilen bir türdense güvenlidir. Bu durumda, gerçek nesne "tam nesne" olarak kabul edilir. Temel sınıfın işaretçisinin, tam nesnenin "alt nesnesine" işaret ettiği bildirilir. Örnek olarak aşağıdaki şekilde gösterilen sınıf hiyerarşisini inceleyin.

![Sınıf hiyerarşisi](../cpp/media/vc38zz1.gif "vc38ZZ1") sınıf hiyerarşisi

`C` türünden bir nesne, aşağıdaki şekilde gösterildiği gibi sanallaştırılabilir.

![Sub sahip C sınıfı&#45;nesneleri B ve A](../cpp/media/vc38zz2.gif "vc38ZZ2") B alt nesnesine ve A alt nesnesine sahip C sınıfı

`C` sınıfının bir örneği göz önünde bulundurulduğunda, bir `B` alt nesnesi ve bir `A` alt nesnesi vardır. `C` ve `A` alt nesneleriyle birlikte `B` örneği, "tam nesne"dir.

Çalışma zamanı tür bilgileri kullanılarak, bir işaretçinin tam bir nesneyi gerçekten işaret edip etmediği denetlenebilir ve işaretçi hiyerarşisindeki başka bir nesneyi işaret edecek şekilde güvenli olarak atanabilir. [Dynamic_cast](../cpp/dynamic-cast-operator.md) işleci bu türden atamalar gerçekleştirmek için kullanılabilir. İşlemi güvenli hale getirmek için gerekli olan çalışma zamanı denetimini de gerçekleştirir.

Türlerin dönüştürülmesi dönüştürme için kullanabileceğiniz [static_cast](../cpp/static-cast-operator.md) işleci (Bu konuda, statik ve dinamik atama dönüştürmelerinin arasındaki ve her kullanmak, uygun olduğunda fark açıklanmaktadır).

Bu bölümde aşağıdaki konuları içerir:

- [Atama İşleçleri](../cpp/casting-operators.md)

- [Çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md)

## <a name="see-also"></a>Ayrıca bkz.

[İfadeler](../cpp/expressions-cpp.md)