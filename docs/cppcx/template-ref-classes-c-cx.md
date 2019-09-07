---
title: Şablon başvuru sınıfları (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: 3e9c233b5227b4ad86eb632db740001bc2a3a8bd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740848"
---
# <a name="template-ref-classes-ccx"></a>Şablon başvuru sınıfları (C++/CX)

C++Şablonlar meta verilerde yayımlanmaz ve bu nedenle programınızda ortak veya korumalı erişilebilirliği olamaz. Elbette, programda dahili olarak standart C++ şablonları kullanabilirsiniz. Ayrıca, özel bir başvuru sınıfını şablon olarak tanımlayabilir ve açık bir özel şablon başvuru sınıfını ortak bir başvuru sınıfında özel üye olarak bildirebilirsiniz.

## <a name="authoring-ref-class-templates"></a>Başvuru sınıfı şablonları yazma

Aşağıdaki örnek, bir özel başvuru sınıfının bir şablon olarak nasıl bildirilemeyeceğini ve ayrıca standart C++ bir şablon bildirmek ve bunları ortak bir başvuru sınıfında üye olarak bildirmek için gösterir. Standart C++ şablonun, bu örnekte Platform:: String ^ olan bir Windows çalışma zamanı türü tarafından özelleştirilebilir olduğunu unutmayın.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
