---
title: "Şablon ref sınıfları (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f135907a4aba473db62734f9370ee82b7113c66d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="template-ref-classes-ccx"></a>Şablon ref sınıfları (C + +/ CX)
C++ şablonları meta verileri yayımlanmayan ve bu nedenle ortak veya korumalı erişilebilirlik programınıza sahip olamaz. Doğal olarak, standart C++ şablonları dahili programınıza kullanabilirsiniz. Ayrıca, bir şablon olarak özel ref sınıfı tanımlayabilirsiniz ve ortak ref sınıfı özel üye olarak açıkça özelleşmiş şablon ref sınıfı bildirebilirsiniz.  
  
## <a name="authoring-ref-class-templates"></a>Ref sınıf şablonları yazma  
 Aşağıdaki örnek, şablon olarak özel ref sınıfı bildirmek nasıl ve ayrıca standart bir C++ şablon bildirme ve bunları ortak ref sınıftaki üyeleri olarak her ikisi de nasıl bildirmek üzere nasıl gösterir. Standart C++ şablon bu bir Windows çalışma zamanı türüne göre özelleştirilmiş olduğunu not durumda bir Platform::String ^.  
  
 [!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sistem türü (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)