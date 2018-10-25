---
title: iş parçacığı oluşturma (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85ffa775fd18b6979fccf4354ce243f017634d02
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059681"
---
# <a name="threading-c"></a>iş parçacığı oluşturma (C++)

Bir COM nesnesi için iş parçacığı modelini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Parametreler

*Model*<br/>
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
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Nötr apartmanlar](/windows/desktop/cossdk/neutral-apartments)