---
title: dispinterface (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: 6fd5010dc20d03c518206d81919e3beafbcaa9a9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038466"
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
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Kullanıma Göre Öznitelikler](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[custom](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)