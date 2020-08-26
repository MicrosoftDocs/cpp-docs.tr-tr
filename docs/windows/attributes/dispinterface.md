---
title: dispınterface (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: dd2a0883418ff79af53285d3cf51dba7601a363c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845399"
---
# <a name="dispinterface"></a>dispinterface

Bir arabirimi. IDL dosyasına bir dağıtım arabirimi olarak koyar.

## <a name="syntax"></a>Syntax

```cpp
[dispinterface]
```

## <a name="remarks"></a>Açıklamalar

**Dispınterface** C++ özniteliği bir arabirimden önce olduğunda, arabirimin oluşturulan. IDL dosyasındaki kitaplık bloğunun içine yerleştirilmesine neden olur.

Bir temel sınıf belirtmediğiniz takdirde, bir dağıtım arabirimi öğesinden türetilir `IDispatch` . Dağıtım arabiriminin üyeleri için bir [kimlik](id.md) belirtmeniz gerekir.

MıDL belgelerindeki [dispınterface](/windows/win32/Midl/dispinterface) için kullanım örneği:

```cpp
dispinterface helloPro
   { interface hello; };
```

, **dispınterface** özniteliği için geçerli değil.

## <a name="example"></a>Örnek

**Dispınterface**'in nasıl [kullanılacağına ilişkin örnek için bkz](bindable.md) ..

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arayüz**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Kullanıma göre öznitelikler](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[çift](dual.md)<br/>
[özel](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)
