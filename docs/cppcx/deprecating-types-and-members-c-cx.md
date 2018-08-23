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
ms.openlocfilehash: 8aecb47db6e9d620ff49fac337454242a1bdb72a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605707"
---
# <a name="deprecating-types-and-members-ccx"></a>Türleri ve üyeleri geçersiz kılma (C + +/ CX)
C + +/ CX, Windows çalışma zamanı türleri ve üyeleri kullanımdan kaldırma için üreticilerin ve tüketicilerin kullanarak [kullanım dışı](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) özniteliği desteklenir. Bu öznitelik uygulanmış bir API tükettiğiniz, API kullanım dışıdır ve kullanmak için alternatif bir API de önerir gösteren bir derleme zamanı uyarı iletisi alırsınız. Kendi genel türleri ve yöntemleri bu özniteliğini uygulayın ve kendi özel ileti sağlayın.  
  
> [!CAUTION]
>  [Kullanım dışı](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) özniteliği, yalnızca Windows çalışma zamanı türleri ile kullanmak içindir. Standart C++ sınıfları ve üyeleri için [__declspec(deprecated)](http://msdn.microsoft.com/library/044swk7y.aspx).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, genel Apı'lerinizi kullanımdan kaldırmaya gösterilmektedir; Örneğin, bir Windows çalışma zamanı bileşeni içinde. İkinci parametresinin türü [Windows: Foundation:: Metadata::DeprecationType](http://msdn.microsoft.com/en-us/ee01e63d-37d0-4273-accc-fca174f88bfa) API olup olmadığını belirtir. kaldırılan veya kullanım dışı. Değer desteklenir. şu anda yalnızca DeprecationType::Deprecated. Üçüncü parametre özniteliğinde belirtir [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/en-us/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) öznitelik uygulandığı için.  
  
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