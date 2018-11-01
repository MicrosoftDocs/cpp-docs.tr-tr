---
title: Türleri ve üyeleri geçersiz kılma (C + +/ CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 661445c8a365451d94f938cfe262623866b0fa5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618640"
---
# <a name="deprecating-types-and-members-ccx"></a>Türleri ve üyeleri geçersiz kılma (C + +/ CX)

C + +/ CX, Windows çalışma zamanı türleri ve üyeleri kullanımdan kaldırma için üreticilerin ve tüketicilerin kullanarak [kullanım dışı](/uwp/api/windows.foundation.metadata.deprecatedattribute) özniteliği desteklenir. Bu öznitelik uygulanmış bir API tükettiğiniz, API kullanım dışıdır ve kullanmak için alternatif bir API de önerir gösteren bir derleme zamanı uyarı iletisi alırsınız. Kendi genel türleri ve yöntemleri bu özniteliğini uygulayın ve kendi özel ileti sağlayın.

> [!CAUTION]
> [Kullanım dışı](/uwp/api/windows.foundation.metadata.deprecatedattribute) özniteliği, yalnızca Windows çalışma zamanı türleri ile kullanmak içindir. Standart C++ sınıfları ve üyeleri için [__declspec(deprecated)](../cpp/deprecated-cpp.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, genel Apı'lerinizi kullanımdan kaldırmaya gösterilmektedir; Örneğin, bir Windows çalışma zamanı bileşeni içinde. İkinci parametresinin türü [Windows: Foundation:: Metadata::DeprecationType](/uwp/api/windows.foundation.metadata.deprecationtype) API olup olmadığını belirtir. kaldırılan veya kullanım dışı. Değer desteklenir. şu anda yalnızca DeprecationType::Deprecated. Üçüncü parametre özniteliğinde belirtir [Windows::Foundation::Metadata::Platform](/uwp/api/windows.foundation.metadata.platformattribute) öznitelik uygulandığı için.

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

## <a name="supported-targets"></a>Desteklenen hedefleri

Aşağıdaki tablo, kullanım dışı özniteliğin uygulanabileceği yapıları listeler:

||
|-|
|XAML denetimi|
|temsilci|
|olay|
|Enum alan|
|enum|
|struct |
|yöntemi|
|sınıf|
|arabirim|
|özellik|
|Yapı alanı|
|Parametreli Oluşturucusu|

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)