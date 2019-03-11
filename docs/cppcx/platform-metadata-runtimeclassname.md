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
ms.openlocfilehash: d3de753c3a8897058333e02ce4294a0780d5b818
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738563"
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

## <a name="see-also"></a>Ayrıca bkz.

[Platform::Metadata Ad Alanı](../cppcx/platform-metadata-namespace.md)
