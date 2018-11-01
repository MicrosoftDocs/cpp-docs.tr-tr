---
title: Platform::Metadata::RuntimeClassName
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
ms.openlocfilehash: 09641f55e27ab00fc941d85d4d09d6a7784e2d8a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668279"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName

Bir sınıf tanımına uygulandığında, özel bir sınıf GetRuntimeClassName işlevinden geçerli bir ad verir sağlar...

## <a name="syntax"></a>Sözdizimi

```cpp
[Platform::Metadata::RuntimeClassName] name
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
Windows çalışma zamanı'nda görülebilir mevcut bir ortak tür adı.

### <a name="remarks"></a>Açıklamalar

Bu öznitelik, bir özel çalışma zamanı tür adı ve/veya ne zaman var olan ad gereksinimlerini karşılamıyor belirtmek için özel başvuru sınıfları üzerinde kullanın. Sınıf uygulayan bir ortak arabirim bir ad belirtin.

### <a name="example"></a>Örnek

Aşağıdaki örnek, öznitelik kullanma işlemini gösterir. Bu örnekte, çalışma zamanı türü HellowWorldImpl Test::Native::MyComponent::IHelloWorld adıdır

```cpp
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