---
title: Şablon başvuru sınıfları (C + +/ CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: a128b9fcc7b37ad2cf7c7a17abb24c8074952501
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642217"
---
# <a name="template-ref-classes-ccx"></a>Şablon başvuru sınıfları (C + +/ CX)

C++ şablonları meta verileri yayımlanmaz ve bu nedenle, ortak veya korumalı erişilebilirlik programınızda sahip olamaz. Doğal olarak, standart C++ şablonları dahili olarak programınızda kullanabilirsiniz. Ayrıca, özel bir başvuru sınıfı bir şablon olarak tanımlayabilir ve bir açıkça özelleşmiş şablon başvuru sınıfının ortak başvuru sınıfı özel üye olarak bildirebilirsiniz.

## <a name="authoring-ref-class-templates"></a>Başvuru sınıfı şablonları yazma

Aşağıdaki örnek bir özel başvuru sınıfı bir şablon olarak bildirmeyi ve standart C++ şablonunu bildirmek ve nasıl bunları hem ortak başvuru sınıfı üye olarak bildirmek nasıl gösterir. Standart C++ şablon bu bir Windows çalışma zamanı türü tarafından özelleştirilebilir Not durumda bir Platform::String ^.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)