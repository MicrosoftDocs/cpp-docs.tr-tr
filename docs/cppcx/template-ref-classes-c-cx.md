---
title: Şablon başvuru sınıfları (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: 4398cc2c545a57277289a6aa41fc4664d9734eed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396043"
---
# <a name="template-ref-classes-ccx"></a>Şablon başvuru sınıfları (C++/CX)

C++ şablonları meta verileri yayımlanmaz ve bu nedenle, ortak veya korumalı erişilebilirlik programınızda sahip olamaz. Doğal olarak, standart C++ şablonları dahili olarak programınızda kullanabilirsiniz. Ayrıca, özel bir başvuru sınıfı bir şablon olarak tanımlayabilir ve bir açıkça özelleşmiş şablon başvuru sınıfının ortak başvuru sınıfı özel üye olarak bildirebilirsiniz.

## <a name="authoring-ref-class-templates"></a>Başvuru sınıfı şablonları yazma

Aşağıdaki örnek bir özel başvuru sınıfı bir şablon olarak bildirmeyi ve standart C++ şablonunu bildirmek ve nasıl bunları hem ortak başvuru sınıfı üye olarak bildirmek nasıl gösterir. Unutmayın standart C++ şablonu özelleştirilmiş bir Windows çalışma zamanı tür, bu durumda Platform::String bir ^.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
