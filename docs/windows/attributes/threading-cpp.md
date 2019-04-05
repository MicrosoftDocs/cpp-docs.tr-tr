---
title: iş parçacığı oluşturma (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: cdebf06a62ebbd1d8648b9777fe200bc7a373261
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038284"
---
# <a name="threading-c"></a>iş parçacığı oluşturma (C++)

Bir COM nesnesi için iş parçacığı modelini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Parametreler

*model*<br/>
(İsteğe bağlı) Aşağıdaki iş parçacığı oluşturma modelleri biri:

- `apartment` (Grup iş parçacığı)

- `neutral` (.NET framework bileşenlerini kullanıcı arabirimi olmadan)

- `single` (basit iş parçacığı)

- `free` (iş parçacığı ücretsiz)

- `both` (Grup ve serbest iş parçacığı oluşturma)

Varsayılan değer `apartment` şeklindedir.

## <a name="remarks"></a>Açıklamalar

**İş parçacığı** C++ özniteliği oluşturulmuş bir .idl dosyasında görünmez ancak, COM nesnesinin uygulamasında kullanılır.

ATL projelerinde, [coclass'ı](coclass.md) özniteliği varsa, ayrıca tarafından belirtilen iş parçacığı modeli *modeli* şablon parametresi olarak geçirilir [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sınıfı , tarafından eklenen `coclass` özniteliği.

**İş parçacığı** özniteliği erişimi de korur bir [event_source](event-source.md).

## <a name="example"></a>Örnek

Bkz: [lisanslı](licensed.md) örnek kullanımını örneğin **iş parçacığı**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Nötr apartmanlar](/windows/desktop/cossdk/neutral-apartments)