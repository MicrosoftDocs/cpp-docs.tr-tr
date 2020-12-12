---
description: 'Daha fazla bilgi edinin: Platform:: Metadata:: RuntimeClassName'
title: Platform::Metadata::RuntimeClassName
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
ms.openlocfilehash: 25d6f3ae6b7509029b08f809fa20d5bd0ca5e735
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308386"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName

Bir sınıf tanımına uygulandığında, özel bir sınıfın GetRuntimeClassName işlevinden geçerli bir ad döndürdüğünden emin olur.

## <a name="syntax"></a>Sözdizimi

```cpp
[Platform::Metadata::RuntimeClassName] name
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
Windows Çalışma Zamanı görünür olan var olan bir genel türün adı.

### <a name="remarks"></a>Açıklamalar

Özel bir çalışma zamanı türü adı ve/veya mevcut adın gereksinimleri karşılamadığında, özel başvuru sınıflarında bu özniteliği kullanın. Ad olarak, sınıfın uyguladığı ortak bir arabirim belirtin.

### <a name="example"></a>Örnek

Aşağıdaki örnek, özniteliğini nasıl kullanacağınızı gösterir. Bu örnekte, Hellowworldımpl çalışma zamanı türü adı test:: Native:: MyComponent:: ıhelloworld

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

[Platform:: Metadata ad alanı](../cppcx/platform-metadata-namespace.md)
