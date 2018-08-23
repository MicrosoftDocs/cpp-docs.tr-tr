---
title: Öznitelikler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7db8d6c527842cd3784623002fba001a4174c1fc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601144"
---
# <a name="attributes-ccx"></a>Öznitelikler (C + +/ CX)
Köşeli ayraç içinde meta verileri oluşturma belirli davranışları belirtmek için Windows çalışma zamanı türleri ve yöntemleri için $a başvuru sınıfının özel bir özniteliktir. Önceden tanımlanmış birkaç öznitelikleri — Örneğin, [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)— C +'da yaygın olarak kullanılan +/ CX kod. Bu örnek, öznitelik bir sınıfa nasıl uygulanacağını gösterir:  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>Özel öznitelikler  
 Ayrıca, özel öznitelikler tanımlayabilirsiniz. Özel öznitelikler, bu Windows çalışma zamanı kurallara uymalıdır:  
  
-   Özel öznitelikleri yalnızca ortak alanlar içerebilir.  
  
-   Öznitelik bir sınıfa uygulandığında özel öznitelik alanları başlatılabilir.  
  
-   Bir alan, şu türlerden birinde olabilir:  
  
    -   Int32 (int)  
  
    -   uint32 (işaretsiz int)  
  
    -   bool  
  
    -   Platform::String ^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::type ^  
  
    -   Genel sabit listesi sınıfı (kullanıcı tanımlı sabit listeleri içerir)  
  
 Sonraki örnek, özel bir öznitelik tanımlayın ve bunları kullandığınızda başlatmak gösterilmektedir.  
  
 [!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)