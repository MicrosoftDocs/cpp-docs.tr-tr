---
title: Türleri ve üyeleri onaysız kılınmadan (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b82f22f996b0f52889bd76227647ab367118898
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="deprecating-types-and-members-ccx"></a>Türleri ve üyeleri onaysız kılınmadan (C + +/ CX)
C + +/ CX, üreticileri ve tüketicileri kullanarak Windows çalışma zamanı tür ve üyelerinin kullanımdan [kullanım dışı](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) özniteliği desteklenir. Bu öznitelik uygulanmış bir API kullanmak, API kullanım dışıdır ve ayrıca kullanmak için alternatif bir API önerir belirten bir derleme zamanı uyarı iletisi alırsınız. Kendi ortak türleri ve yöntemleri bu özniteliğini uygulayın ve kendi özel ileti sağlayın.  
  
> [!CAUTION]
>  [Kullanım dışı](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) özniteliktir yalnızca Windows çalışma zamanı türleri ile kullanım için. Standart C++ sınıflar ve üyeleri için kullanmak [__declspec(deprecated)](http://msdn.microsoft.com/library/044swk7y.aspx).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, kendi ortak API'ler alanı onaylanamadı gösterilmiştir — Örneğin, bir Windows çalışma zamanı bileşeni içinde. İkinci parametre türü [Windows: Foundation:: Metadata::DeprecationType](http://msdn.microsoft.com/en-us/ee01e63d-37d0-4273-accc-fca174f88bfa) API yüklenmekte olan olup olmadığını belirtir kullanım dışı veya kaldırılmış. Değer desteklenir şu anda yalnızca DeprecationType::Deprecated. Öznitelik üçüncü parametre belirtir [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/en-us/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) öznitelik geçerli olduğu için.  
  
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
 Aşağıdaki tabloda, kullanım dışı özniteliği uygulanabilir yapıları listelenmektedir:  
  
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
|Yapı alan|  
|Parametreli Oluşturucusu|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)