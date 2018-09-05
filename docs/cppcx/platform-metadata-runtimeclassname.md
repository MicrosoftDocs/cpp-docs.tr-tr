---
title: Platform::metadata::RuntimeClassName | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 024d9d7dce234b07620a108b1f11c240bd842ac6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765497"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName
Bir sınıf tanımına uygulandığında, özel bir sınıf GetRuntimeClassName işlevinden geçerli bir ad verir sağlar...  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### <a name="parameters"></a>Parametreler  
 name  
  
 Windows çalışma zamanı'nda görülebilir mevcut bir ortak tür adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu öznitelik, bir özel çalışma zamanı tür adı ve/veya ne zaman var olan ad gereksinimlerini karşılamıyor belirtmek için özel başvuru sınıfları üzerinde kullanın. Sınıf uygulayan bir ortak arabirim bir ad belirtin.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, öznitelik kullanma işlemini gösterir. Bu örnekte, çalışma zamanı türü HellowWorldImpl Test::Native::MyComponent::IHelloWorld adıdır  
  
```  
  
namespace Test  
{  
    namespace Native  
    {  
        namespace MyComponent  
        {  
            public interface class IHelloWorld  
            {  
                Platform::String^ SayHello();  
            };  
  
            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld  
            {  
            public:  
                HelloWorldImpl();  
                virtual Platform::String^ SayHello();  
            };  
  
            Platform::String^ HelloWorldImpl::SayHello()  
            {  
                return L"Hello World!";  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::Metadata Ad Alanı](../cppcx/platform-metadata-namespace.md)