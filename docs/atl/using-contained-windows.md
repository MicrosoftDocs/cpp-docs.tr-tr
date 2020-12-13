---
description: 'Hakkında daha fazla bilgi edinin: kapsanan pencereleri kullanma'
title: Kapsanan pencereleri kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 11beb998365a10a8126e37ecbf7388ec6177e659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138222"
---
# <a name="using-contained-windows"></a>Kapsanan pencereleri kullanma

ATL, [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)ile içerilen pencereleri uygular. İçerilen bir pencere, iletilerini kendi sınıfında işlemek yerine bir kapsayıcı nesnesine temsilcerek bir pencereyi temsil eder.

> [!NOTE]
> Kapsanan pencereleri kullanmak için ' den bir sınıf türetmeniz gerekmez `CContainedWindowT` .

İçerilen pencereler ile var olan bir Windows sınıfının üst sınıfını ya da varolan bir pencerenin alt sınıfını kullanabilirsiniz. Var olan bir Windows sınıfını üst sınıflara uygulayan bir pencere oluşturmak için, önce nesne oluşturucusunda var olan sınıf adını belirtin `CContainedWindowT` . Ardından öğesini çağırın `CContainedWindowT::Create` . Varolan bir pencerenin alt sınıfını almak için, bir Windows sınıf adı belirtmeniz gerekmez (oluşturucuya NULL değeri geçirin). Yöntemi, alt `CContainedWindowT::SubclassWindow` sınıflandırılmakta olan pencereye yönelik tanıtıcıyla birlikte çağırmak yeterlidir.

Genellikle kapsayıcı sınıfının veri üyeleri olarak içerilen pencereleri kullanırsınız. Kapsayıcının bir pencere olması gerekmez; Ancak, [CMessageMap](../atl/reference/cmessagemap-class.md)öğesinden türemelidir.

İçerilen bir pencere, iletilerini işlemek için alternatif ileti eşlemeleri kullanabilir. İçerilen birden fazla pencere varsa, her biri ayrı içerilen pencereye karşılık gelen birkaç alternatif ileti eşlemesi bildirmeniz gerekir.

## <a name="example"></a>Örnek

Aşağıda, iki içerilen pencere içeren bir kapsayıcı sınıfına örnek verilmiştir:

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

İçerilen pencereler hakkında daha fazla bilgi için bkz. alt [DIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)
