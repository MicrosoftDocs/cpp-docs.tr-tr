---
title: Platform::Metadata::RuntimeClassName | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9addee7708fe1d0838168dd54f395459f9b71990
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName
Bir sınıf tanımı uygulandığında, özel bir sınıf geçerli bir ad GetRuntimeClassName işlevinden döndürür sağlar...  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### <a name="parameters"></a>Parametreler  
 name  
  
 Windows çalışma zamanı'nda görünür olan mevcut bir ortak türü adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu öznitelik özel ref sınıflarında özel çalışma zamanı tür adı ve/veya ne zaman varolan adı gereksinimlerini karşılamıyor belirtmek için kullanın. Bir ad sınıfını uygulayan ortak bir arabirim belirtin.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, özniteliğin nasıl kullanılacağını gösterir. Bu örnekte, çalışma zamanı tür HellowWorldImpl Test::Native::MyComponent::IHelloWorld adıdır  
  
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