---
title: "Öznitelikler (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6dcd3818d21b644211891ae4779a6b9bf5074e6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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