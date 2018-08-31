---
title: dispinterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a98c9016281a67211a41d1c63fcb9886a0b3c35
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222516"
---
# <a name="dispinterface"></a>dispinterface

Bir arabirim gönderme arabirimi olarak .idl dosyasına yerleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[dispinterface]
```

## <a name="remarks"></a>Açıklamalar

Zaman **dispinterface** C++ özniteliği önündeki bir arabirim, oluşturulan .idl dosyasındaki kitaplığı bloğunun yerleştirilecek arabirimi neden olur.

Dağıtım arabirimi türetilir bir temel sınıf belirtmediğiniz sürece `IDispatch`. Belirtmelisiniz bir [kimliği](../windows/id.md) gönderme arabirimin üyeleri için.

Kullanım örneği için [dispinterface](/windows/desktop/Midl/dispinterface) MIDL belgelerinde:

```cpp
dispinterface helloPro
   { interface hello; };
```

için geçerli değil **dispinterface** özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](../windows/bindable.md) nasıl kullanılacağına ilişkin bir örnek **dispinterface**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)  
[uuid](../windows/uuid-cpp-attributes.md)  
[dual](../windows/dual.md)  
[Özel](../windows/custom-cpp.md)  
[object](../windows/object-cpp.md)  
[__interface](../cpp/interface.md)  