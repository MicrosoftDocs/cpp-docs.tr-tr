---
title: dispınterface (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: 6360c5e97eae19d7b2d74b3b43d4feae07d4b091
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501621"
---
# <a name="dispinterface"></a>dispinterface

Bir arabirimi. IDL dosyasına bir dağıtım arabirimi olarak koyar.

## <a name="syntax"></a>Sözdizimi

```cpp
[dispinterface]
```

## <a name="remarks"></a>Açıklamalar

**Dispınterface** C++ özniteliği bir arabirimden önce olduğunda, arabirimin oluşturulan. IDL dosyasındaki kitaplık bloğunun içine yerleştirilmesine neden olur.

Bir temel sınıf belirtmediğiniz takdirde, bir dağıtım arabirimi öğesinden `IDispatch`türetilir. Dağıtım arabiriminin üyeleri için bir [kimlik](id.md) belirtmeniz gerekir.

MıDL belgelerindeki [dispınterface](/windows/win32/Midl/dispinterface) için kullanım örneği:

```cpp
dispinterface helloPro
   { interface hello; };
```

, **dispınterface** özniteliği için geçerli değil.

## <a name="example"></a>Örnek

**Dispınterface**'in nasıl [](bindable.md) kullanılacağına ilişkin örnek için bkz.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Kullanıma Göre Öznitelikler](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[custom](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)