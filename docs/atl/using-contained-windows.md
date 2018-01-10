---
title: Kapsanan Windows kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f812b99131d63b87df8dbfd8c9afd5493d0a0140
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

