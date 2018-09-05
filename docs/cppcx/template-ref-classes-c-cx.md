---
title: Şablon başvuru sınıfları (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb322ae641a1821ed8434e0ea197acf752698e6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760155"
---
# <a name="template-ref-classes-ccx"></a>Şablon başvuru sınıfları (C + +/ CX)
C++ şablonları meta verileri yayımlanmaz ve bu nedenle, ortak veya korumalı erişilebilirlik programınızda sahip olamaz. Doğal olarak, standart C++ şablonları dahili olarak programınızda kullanabilirsiniz. Ayrıca, özel bir başvuru sınıfı bir şablon olarak tanımlayabilir ve bir açıkça özelleşmiş şablon başvuru sınıfının ortak başvuru sınıfı özel üye olarak bildirebilirsiniz.  
  
## <a name="authoring-ref-class-templates"></a>Başvuru sınıfı şablonları yazma  
 Aşağıdaki örnek bir özel başvuru sınıfı bir şablon olarak bildirmeyi ve standart C++ şablonunu bildirmek ve nasıl bunları hem ortak başvuru sınıfı üye olarak bildirmek nasıl gösterir. Standart C++ şablon bu bir Windows çalışma zamanı türü tarafından özelleştirilebilir Not durumda bir Platform::String ^.  
  
 [!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)