---
title: Öznitelikler (C++/CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: 77962dc2d4b7f6bda90a5376e5154782365a4106
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740390"
---
# <a name="attributes-ccx"></a>Öznitelikler (C++/CX)

Öznitelik, meta veri oluşturmada belirli davranışları belirtmek üzere Windows Çalışma Zamanı türleri ve yöntemleri için köşeli ayraç içine eklenebilir özel bir başvuru sınıfı türüdür. Daha önceden tanımlanmış birkaç öznitelik — Örneğin, [Windows:: Foundation:: Metadata:: WebHostHidden](/uwp/api/Windows.Foundation.Metadata.WebHostHiddenAttribute)—, genellikle C++/CX kodunda kullanılır. Bu örnekte, özniteliğin bir sınıfa nasıl uygulandığı gösterilmektedir:

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
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
