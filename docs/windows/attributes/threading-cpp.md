---
title: Threading (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: db2940ec3536ae8ea29ba40db84ea869ecb3d0ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513925"
---
# <a name="threading-c"></a>iş parçacığı oluşturma (C++)

COM nesnesi için iş parçacığı modelini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Parametreler

*modelinizi*<br/>
Seçim Aşağıdaki iş parçacığı modellerden biri:

- `apartment`(Apartman iş parçacığı)

- `neutral`(Kullanıcı arabirimi olmayan .NET Framework bileşenleri)

- `single`(basit iş parçacığı)

- `free`(serbest iş parçacığı)

- `both`(Apartman ve serbest iş parçacığı)

Varsayılan değer `apartment` şeklindedir.

## <a name="remarks"></a>Açıklamalar

**Threading** C++ özniteliği oluşturulan. IDL dosyasında görünmez, ancak com nesnenizin uygulamasında kullanılacaktır.

ATL projelerinde, [coclass](coclass.md) özniteliği de varsa, *model* tarafından belirtilen iş parçacığı modeli [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) `coclass` sınıfına öznitelik tarafından yerleştirilen şablon parametresi olarak geçirilir.

**İş parçacığı** özniteliği bir [event_source](event-source.md)erişimini de korur.

## <a name="example"></a>Örnek

**İş parçacığı**örneği kullanımı için [lisanslı](licensed.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Bağımsız apartmanlar](/windows/win32/cossdk/neutral-apartments)