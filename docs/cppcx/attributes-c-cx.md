---
title: Öznitelikler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 627e89c844b97637897c9b5eb6c1cc7e32081fd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="attributes-ccx"></a>Öznitelikler (C + +/ CX)
Windows çalışma zamanı türleri ve yöntemleri meta veri oluşturma, belirli davranışlarını belirtmek için köşeli ayraçlar içinde $a ref sınıfı özel bir tür özniteliğidir. Önceden tanımlanmış birkaç öznitelikleri — Örneğin, [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)— C + yaygın olarak kullanılan +/ CX kodu. Bu örnek, bir sınıfa öznitelik nasıl uygulandığını gösterir:  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>Özel öznitelikler  
 Özel öznitelikler de tanımlayabilirsiniz. Özel öznitelikler bu Windows çalışma zamanı kurallarına uyması gerekir:  
  
-   Özel öznitelikler yalnızca genel alanlar içerebilir.  
  
-   Öznitelik bir sınıfa uygulandığında özel öznitelik alanları başlatılabilir.  
  
-   Bir alan şu türlerden biri olabilir:  
  
    -   Int32 (int)  
  
    -   uint32 (imzasız int)  
  
    -   bool  
  
    -   Platform::String ^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::type ^  
  
    -   Ortak enum sınıfı (kullanıcı tanımlı numaralandırmaları içerir)  
  
 Aşağıdaki örnek, özel bir öznitelik tanımlamak ve kullandığınız zaman başlatma gösterilmektedir.  
  
 [!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sistem türü (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)