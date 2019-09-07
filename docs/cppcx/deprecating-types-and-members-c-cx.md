---
title: Türleri ve üyeleri kullanımdan kaldırma (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 6cd880af7e206b4c7338e53615594ec2c65c59fc
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740495"
---
# <a name="deprecating-types-and-members-ccx"></a>Türleri ve üyeleri kullanımdan kaldırma (C++/CX)

/CX C++'de, [kullanım dışı bırakılmış](/uwp/api/windows.foundation.metadata.deprecatedattribute) özniteliği kullanarak üreticileri ve tüketiciler için Windows çalışma zamanı türlerini ve üyelerini kullanımdan kaldırma desteklenir. Bu özniteliğin uygulandığı bir API kullanıyorsanız, API 'nin kullanım dışı olduğunu ve ayrıca kullanılacak alternatif bir API 'yi öneren bir derleme zamanı uyarı iletisi alırsınız. Kendi ortak türleriniz ve yöntemlerinde bu özniteliği uygulayabilir ve kendi özel iletinizi sağlayabilirsiniz.

> [!CAUTION]
> [Kullanım dışı bırakılan](/uwp/api/windows.foundation.metadata.deprecatedattribute) öznitelik yalnızca Windows çalışma zamanı türleriyle kullanım içindir. Standart C++ sınıflar ve Üyeler için [__declspec (kullanım dışı)](../cpp/deprecated-cpp.md)kullanın.

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

| |
|-|
|XAML denetimi|
|temsilci|
|olay|
|sabit listesi alanı|
|enum|
|struct|
|yöntemi|
|sınıf|
|arabirim|
|özellik|
|struct alanı|
|Parametreli Oluşturucu|

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
