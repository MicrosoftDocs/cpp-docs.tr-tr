---
title: dispinterface (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 3b02244e0576f99cc0a6940f2ee4a13511cfbe6f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789571"
---
# <a name="dispinterface"></a>dispinterface

Bir arabirim gönderme arabirimi olarak .idl dosyasına yerleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[dispinterface]
```

## <a name="remarks"></a>Açıklamalar

Zaman **dispinterface** C++ özniteliği önündeki bir arabirim, oluşturulan .idl dosyasındaki kitaplığı bloğunun yerleştirilecek arabirimi neden olur.

Dağıtım arabirimi türetilir bir temel sınıf belirtmediğiniz sürece `IDispatch`. Belirtmelisiniz bir [kimliği](id.md) gönderme arabirimin üyeleri için.

Kullanım örneği için [dispinterface](/windows/desktop/Midl/dispinterface) MIDL belgelerinde:

```cpp
dispinterface helloPro
   { interface hello; };
```

için geçerli değil **dispinterface** özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](bindable.md) nasıl kullanılacağına ilişkin bir örnek **dispinterface**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Kullanıma Göre Öznitelikler](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[Özel](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)  