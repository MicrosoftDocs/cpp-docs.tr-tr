---
title: Öznitelikler (C + +/ CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: 5f74914ab65fdf2c1803b47665e16378991efa3c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743824"
---
# <a name="attributes-ccx"></a>Öznitelikler (C + +/ CX)

Köşeli ayraç içinde meta verileri oluşturma belirli davranışları belirtmek için Windows çalışma zamanı türleri ve yöntemleri için $a başvuru sınıfının özel bir özniteliktir. Önceden tanımlanmış birkaç öznitelikleri — Örneğin, [Windows::Foundation::Metadata::WebHostHidden](/uwp/api/Windows.Foundation.Metadata.WebHostHiddenAttribute)— C +'da yaygın olarak kullanılan +/ CX kod. Bu örnek, öznitelik bir sınıfa nasıl uygulanacağını gösterir:

[!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]

## <a name="custom-attributes"></a>Özel öznitelikler

Ayrıca, özel öznitelikler tanımlayabilirsiniz. Özel öznitelikler, bu Windows çalışma zamanı kurallara uymalıdır:

- Özel öznitelikleri yalnızca ortak alanlar içerebilir.

- Öznitelik bir sınıfa uygulandığında özel öznitelik alanları başlatılabilir.

- Bir alan, şu türlerden birinde olabilir:

   - Int32 (int)

   - uint32 (işaretsiz int)

   - bool

   - Platform::String ^

   - Windows::Foundation::HResult

   - Platform::type ^

   - Genel sabit listesi sınıfı (kullanıcı tanımlı sabit listeleri içerir)

Sonraki örnek, özel bir öznitelik tanımlayın ve bunları kullandığınızda başlatmak gösterilmektedir.

[!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)
