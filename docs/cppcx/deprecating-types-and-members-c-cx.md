---
description: 'Daha fazla bilgi edinin: türleri ve üyeleri kullanımdan kaldırma (C++/CX)'
title: Türleri ve Üyeleri Geçersiz Kılma (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: fddb9ecd81045655f3ca80c41e0fa3103d3ff52d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342003"
---
# <a name="deprecating-types-and-members-ccx"></a>Türleri ve Üyeleri Geçersiz Kılma (C++/CX)

C++/CX ' te, [kullanım dışı bırakılmış](/uwp/api/windows.foundation.metadata.deprecatedattribute) özniteliği kullanarak üreticileri ve tüketiciler için Windows çalışma zamanı türlerini ve üyelerini kullanımdan kaldırma desteklenir. Bu özniteliğin uygulandığı bir API kullanıyorsanız, API 'nin kullanım dışı olduğunu ve ayrıca kullanılacak alternatif bir API 'yi öneren bir derleme zamanı uyarı iletisi alırsınız. Kendi ortak türleriniz ve yöntemlerinde bu özniteliği uygulayabilir ve kendi özel iletinizi sağlayabilirsiniz.

> [!CAUTION]
> [Kullanım dışı bırakılan](/uwp/api/windows.foundation.metadata.deprecatedattribute) öznitelik yalnızca Windows çalışma zamanı türleriyle kullanım içindir. Standart C++ sınıfları ve üyeleri için [__declspec (kullanım dışı)](../cpp/deprecated-cpp.md)öğesini kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, kendi ortak API 'lerinizi kullanımdan kaldırma (örneğin, bir Windows Çalışma Zamanı bileşeninde) gösterilmektedir. [Windows: Foundation:: Metadata::D eprecationType](/uwp/api/windows.foundation.metadata.deprecationtype) türünde ikinci parametre, API 'nin kullanım dışı bırakılıp kaldırılmadığını belirtir. Şu anda yalnızca kullanım dışı Cationtype::D epreta değeri desteklenir. Öznitelikteki üçüncü parametre, özniteliğin uygulandığı [Windows:: Foundation:: Metadata::P latform](/uwp/api/windows.foundation.metadata.platformattribute) öğesini belirtir.

```

namespace wfm = Windows::Foundation::Metadata;

public ref class Bicycle sealed
{

public:
    property double Speed;

    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]
    double ComputeAngularVelocity();
};
```

## <a name="supported-targets"></a>Desteklenen hedefler

Aşağıdaki tabloda, kullanım dışı bırakılan özniteliğin uygulanabileceğini listeleyen yapılar listelenmektedir:

:::row:::
   :::column span="":::
      sınıfı
      ğini
      yardımının
      Enum alanı \
      olay
      arabirim
   :::column-end:::
   :::column span="":::
      yöntemidir
      Parametreli Oluşturucu \
      özelliði
      sýný
      struct alanı \
      XAML denetimi
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
