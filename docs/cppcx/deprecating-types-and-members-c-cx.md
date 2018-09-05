---
title: Türleri ve üyeleri geçersiz kılma (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b2f8ab1c52297a95c89f8ee00053d24baebe39d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764416"
---
# <a name="deprecating-types-and-members-ccx"></a>Türleri ve üyeleri geçersiz kılma (C + +/ CX)
C + +/ CX, Windows çalışma zamanı türleri ve üyeleri kullanımdan kaldırma için üreticilerin ve tüketicilerin kullanarak [kullanım dışı](/uwp/api/windows.foundation.metadata.deprecatedattribute) özniteliği desteklenir. Bu öznitelik uygulanmış bir API tükettiğiniz, API kullanım dışıdır ve kullanmak için alternatif bir API de önerir gösteren bir derleme zamanı uyarı iletisi alırsınız. Kendi genel türleri ve yöntemleri bu özniteliğini uygulayın ve kendi özel ileti sağlayın.  
  
> [!CAUTION]
>  [Kullanım dışı](/uwp/api/windows.foundation.metadata.deprecatedattribute) özniteliği, yalnızca Windows çalışma zamanı türleri ile kullanmak içindir. Standart C++ sınıfları ve üyeleri için [__declspec(deprecated)](../cpp/deprecated-cpp.md).  
  
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
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)