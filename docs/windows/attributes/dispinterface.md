---
title: dispınterface (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: 66567b0a1b043136e0a754e3a52bbdd7c463e178
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168245"
---
# <a name="dispinterface"></a>dispinterface

Bir arabirimi. IDL dosyasına bir dağıtım arabirimi olarak koyar.

## <a name="syntax"></a>Sözdizimi

```cpp
[dispinterface]
```

## <a name="remarks"></a>Açıklamalar

**Dispınterface** C++ özniteliği bir arabirimden önce olduğunda, arabirimin oluşturulan. IDL dosyasındaki kitaplık bloğunun içine yerleştirilmesine neden olur.

Bir temel sınıf belirtmediğiniz takdirde, bir dağıtım arabirimi `IDispatch`türetilir. Dağıtım arabiriminin üyeleri için bir [kimlik](id.md) belirtmeniz gerekir.

MıDL belgelerindeki [dispınterface](/windows/win32/Midl/dispinterface) için kullanım örneği:

```cpp
dispinterface helloPro
   { interface hello; };
```

, **dispınterface** özniteliği için geçerli değil.

## <a name="example"></a>Örnek

**Dispınterface**'in nasıl [kullanılacağına ilişkin örnek için bkz](bindable.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
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
