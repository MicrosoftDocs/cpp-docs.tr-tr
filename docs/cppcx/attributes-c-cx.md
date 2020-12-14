---
description: 'Daha fazla bilgi edinin: öznitelikler (C++/CX)'
title: Öznitelikler (C++/CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: 82299db6b5c11521584b8dd400b401ec0df78c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302783"
---
# <a name="attributes-ccx"></a>Öznitelikler (C++/CX)

Öznitelik, meta veri oluşturmada belirli davranışları belirtmek üzere Windows Çalışma Zamanı türleri ve yöntemleri için köşeli ayraç içine eklenebilir özel bir başvuru sınıfı türüdür. Birkaç önceden tanımlı öznitelik — Örneğin,  [Windows:: Foundation:: Metadata:: WebHostHidden](/uwp/api/windows.foundation.metadata.webhosthiddenattribute)— C++/CX kodunda yaygın olarak kullanılır. Bu örnekte, özniteliğin bir sınıfa nasıl uygulandığı gösterilmektedir:

[!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]

## <a name="custom-attributes"></a>Özel öznitelikler

Özel öznitelikler de tanımlayabilirsiniz. Özel özniteliklerin bu Windows Çalışma Zamanı kurallara uyması gerekir:

- Özel öznitelikler yalnızca ortak alanlar içerebilir.

- Öznitelik bir sınıfa uygulandığında özel öznitelik alanları başlatılabilir.

- Bir alan şu türlerden biri olabilir:

  - Int32 (int)

  - uint32 (işaretsiz int)

  - bool

  - Platform:: String ^

  - Windows:: Foundation:: HResult

  - Platform:: Type ^

  - ortak sabit listesi sınıfı (Kullanıcı tanımlı numaralandırmalar dahil)

Sonraki örnekte, özel bir özniteliği nasıl tanımlayacağınızı ve bunu kullandığınızda nasıl başlatacağınızı gösterir.

[!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
