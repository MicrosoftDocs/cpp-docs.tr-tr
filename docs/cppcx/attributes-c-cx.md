---
title: Öznitelikler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82d779448afdb931b24d2c4d08645d448f295198
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105126"
---
# <a name="attributes-ccx"></a>Öznitelikler (C + +/ CX)

Köşeli ayraç içinde meta verileri oluşturma belirli davranışları belirtmek için Windows çalışma zamanı türleri ve yöntemleri için $a başvuru sınıfının özel bir özniteliktir. Önceden tanımlanmış birkaç öznitelikleri — Örneğin, [Windows::Foundation::Metadata::WebHostHidden](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)— C +'da yaygın olarak kullanılan +/ CX kod. Bu örnek, öznitelik bir sınıfa nasıl uygulanacağını gösterir:

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

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)