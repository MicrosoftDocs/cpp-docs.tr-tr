---
title: Kapsanan Windows kullanma | Microsoft Docs
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
ms.openlocfilehash: f6c3b439baf05c4e4287613e9b6b5a9b1c2546b6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="using-contained-windows"></a>Kapsanan Windows kullanma
ATL uygulayan kapsanan windows ile [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Kapsanan bir pencere iletileri kendi sınıfında işleme yerine bir kapsayıcı nesne için temsilci bir pencereyi temsil eder.  
  
> [!NOTE]
>  Öğesinden bir sınıf türetin gerekmez `CContainedWindowT` kapsanan windows kullanmak için.  
  
 Kapsanan windows ile bir mevcut Windows sınıfı veya varolan bir pencereyi alt sınıf ya da üst sınıf kullanabilirsiniz. Bu aktarılabileceği bir mevcut Windows bir pencere oluşturmak için sınıfı, oluşturucuda varolan sınıf adı belirtmeniz `CContainedWindowT` nesnesi. ' I çağırın `CContainedWindowT::Create`. Varolan bir pencereyi alt sınıf için bir Windows sınıf adı belirtmeniz gerekmez (geçirmek **NULL** oluşturucuya). Basit Arama `CContainedWindowT::SubclassWindow` sınıflandırma penceresine tanıtıcısıyla yöntemi.  
  
 Kapsanan windows genellikle bir kapsayıcı sınıfı veri üyesi olarak kullanın. Kapsayıcı bir pencere olması gerekmez; Ancak, öğesinden türetilmelidir [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 Kapsanan bir pencere iletileri işlemek için alternatif ileti eşlemeleri kullanabilirsiniz. Birden fazla içerdiği pencere varsa, birkaç her ayrı bir kapsanan penceresine karşılık gelen ileti eşlemeleri alternatif bildirmeniz gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki iki kapsanan windows ile bir kapsayıcı sınıfını örneğidir:  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 Kapsanan pencereleri hakkında daha fazla bilgi için bkz: [SUBEDIT](../visual-cpp-samples.md) örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere sınıfları](../atl/atl-window-classes.md)

