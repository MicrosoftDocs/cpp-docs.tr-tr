---
description: 'Daha fazla bilgi edinin: şablon başvuru sınıfları (C++/CX)'
title: Şablon Başvuru Sınıfları (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: c8f3e668dddd80a2ce05f10f9a5d2ada30096c3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307632"
---
# <a name="template-ref-classes-ccx"></a>Şablon Başvuru Sınıfları (C++/CX)

C++ şablonları meta verilerde yayımlanmaz ve bu nedenle programınızda ortak veya korumalı erişilebilirliği olamaz. Kuşkusuz, programda dahili olarak standart C++ şablonlarını kullanabilirsiniz. Ayrıca, özel bir başvuru sınıfını şablon olarak tanımlayabilir ve açık bir özel şablon başvuru sınıfını ortak bir başvuru sınıfında özel üye olarak bildirebilirsiniz.

## <a name="authoring-ref-class-templates"></a>Başvuru sınıfı şablonları yazma

Aşağıdaki örnek, bir özel başvuru sınıfının bir şablon olarak nasıl bildirilemeyeceğini ve ayrıca standart bir C++ şablonunun nasıl bildirilemeyeceğini ve bunları ortak bir başvuru sınıfında üye olarak nasıl bildirecekleri gösterilmektedir. Standart C++ şablonunun, bu örnekte Platform:: String ^ olan bir Windows Çalışma Zamanı türü tarafından özelleştirilebilir olduğunu unutmayın.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
