---
title: İçerdeki Pencereleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 5da765eae28d411c98e79af5b9173f48ea66ef8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329300"
---
# <a name="using-contained-windows"></a>İçerdeki Pencereleri Kullanma

ATL [ccontainedwindowT](../atl/reference/ccontainedwindowt-class.md)içeren pencereler ilerler. İçe sahip pencere, iletilerini kendi sınıfında işlemek yerine kapsayıcı nesneye devreden bir pencereyi temsil eder.

> [!NOTE]
> İçerdeki pencereleri kullanmak için `CContainedWindowT` bir sınıf türetmeniz gerekmez.

İçerdiği pencerelerle, varolan bir Windows sınıfını üst sınıfa alabilir veya varolan bir pencereyi alt sınıfa göre sınıflandırabilirsiniz. Varolan bir Windows sınıfının üst sınıflarını oluşturan bir pencere oluşturmak için, önce nesnenin oluşturucusundaki varolan sınıf adını belirtin. `CContainedWindowT` O `CContainedWindowT::Create`zaman ara. Varolan bir pencereyi alt sınıfa aktarmak için bir Windows sınıf adı belirtmeniz gerekmez (NULL'u oluşturucuya geçirin). Alt sınıflı olan pencereye tutamacı olan `CContainedWindowT::SubclassWindow` yöntemi aramanız yeterlidir.

İçerdiği pencereleri genellikle kapsayıcı sınıfının veri üyeleri olarak kullanırsınız. Kapsayıcı bir pencere olması gerekmez; ancak, [CMessageMap](../atl/reference/cmessagemap-class.md)türetmek gerekir.

İçe yer alan bir pencere, iletilerini işlemek için alternatif ileti eşlemlerini kullanabilir. Birden fazla bulunan pencereniz varsa, her biri ayrı bir pencereye karşılık gelen birkaç alternatif ileti eşlemesi bildirmeniz gerekir.

## <a name="example"></a>Örnek

Aşağıda, iki pencereiçeren bir kapsayıcı sınıfı örneği verilmiştir:

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

İçerdiği pencereler hakkında daha fazla bilgi için [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Sınıfları](../atl/atl-window-classes.md)
