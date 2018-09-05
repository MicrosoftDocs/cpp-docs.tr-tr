---
title: Kapsanan bir Windows kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1d338851a6480014e1f7a48f848f95439d9311a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762118"
---
# <a name="using-contained-windows"></a>Kapsanan bir Windows kullanma

ATL ile kapsanan pencereler uygulayan [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Bir kapsanan pencere iletilerini bunları kendi sınıfında işleme yerine bir kapsayıcı nesnesi için temsilci bir pencereyi temsil eder.

> [!NOTE]
>  Öğesinden bir sınıf türetin gerekmez `CContainedWindowT` kapsanan pencereler kullanmak için.

Kapsanan pencereler ile ya da sınıfın, bir var olan Windows sınıfı ya da alt varolan pencereye gerçekleştirebilirsiniz. Bu var olan bir Windows aktarılabileceği bir pencere oluşturmak için sınıf, önce varolan sınıf adı için oluşturucu belirtin `CContainedWindowT` nesne. Ardından çağırın `CContainedWindowT::Create`. Varolan pencereye alt sınıfı için bir Windows sınıf adı (pass NULL oluşturucuya) belirtmeniz gerekmez. Yalnızca çağrı `CContainedWindowT::SubclassWindow` sınıflandırma penceresine tanıtıcısıyla yöntemi.

Kapsanan pencereler genellikle veri üyesi olarak bir kapsayıcı sınıfı kullanın. Kapsayıcı bir pencere olması gerekmez; Ancak, öğesinden türetilmelidir [CMessageMap](../atl/reference/cmessagemap-class.md).

Bir kapsanan pencere iletilerini işlemek için diğer ileti eşlemeleri kullanabilirsiniz. Birden fazla kapsanan pencere varsa, birçok ayrı bir kapsanan pencere karşılık gelen her ileti eşlemeleri, alternatif bildirmelidir.

## <a name="example"></a>Örnek

İki bağımsız windows ile kapsayıcı sınıfının bir örneği verilmiştir:

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

Kapsanan pencereler hakkında daha fazla bilgi için bkz: [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) örnek.

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)

