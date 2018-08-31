---
title: iş parçacığı oluşturma (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 19f49951cad65d3dbf15c406af9ac78a28408d4b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221820"
---
# <a name="threading-c"></a>iş parçacığı oluşturma (C++)

Bir COM nesnesi için iş parçacığı modelini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ threading(
   model=enumeration
) ]
```

### <a name="parameters"></a>Parametreler

*Model* (isteğe bağlı)  
Aşağıdaki iş parçacığı oluşturma modelleri biri:

- `apartment` (Grup iş parçacığı)

- `neutral` (.NET framework bileşenlerini kullanıcı arabirimi olmadan)

- `single` (basit iş parçacığı)

- `free` (iş parçacığı ücretsiz)

- `both` (Grup ve serbest iş parçacığı oluşturma)

Varsayılan değer `apartment` şeklindedir.

## <a name="remarks"></a>Açıklamalar

**İş parçacığı** C++ özniteliği oluşturulmuş bir .idl dosyasında görünmez ancak, COM nesnesinin uygulamasında kullanılır.

ATL projelerinde, [coclass'ı](../windows/coclass.md) özniteliği varsa, ayrıca tarafından belirtilen iş parçacığı modeli *modeli* şablon parametresi olarak geçirilir [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) sınıfı , tarafından eklenen `coclass` özniteliği.

**İş parçacığı** özniteliği erişimi de korur bir [event_source](../windows/event-source.md).

## <a name="example"></a>Örnek

Bkz: [lisanslı](../windows/licensed.md) örnek kullanımını örneğin **iş parçacığı**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](../windows/com-attributes.md)  
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  
[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)  
[Nötr apartmanlar](/windows/desktop/cossdk/neutral-apartments)  