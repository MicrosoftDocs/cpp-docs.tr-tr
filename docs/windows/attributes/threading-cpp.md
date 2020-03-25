---
title: Threading (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: b249eaf61266ed9964e44f6f0ad1c2f12a1b1067
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214506"
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

- `apartment` (Apartman iş parçacığı)

- `neutral` (Kullanıcı arabirimi olmayan bileşenleri .NET Framework)

- `single` (basit iş parçacığı)

- `free` (serbest iş parçacığı)

- `both` (Apartman ve serbest iş parçacığı)

Varsayılan değer: `apartment`.

## <a name="remarks"></a>Açıklamalar

**Threading** C++ özniteliği oluşturulan. IDL dosyasında görünmez, ancak com nesnenizin uygulamasında kullanılacaktır.

ATL projelerinde, [coclass](coclass.md) özniteliği de varsa *model* tarafından belirtilen Iş parçacığı modeli [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sınıfına, `coclass` özniteliği tarafından eklenir.

**İş parçacığı** özniteliği bir [event_source](event-source.md)erişimi de korur.

## <a name="example"></a>Örnek

**İş parçacığı**örneği kullanımı için [lisanslı](licensed.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Bağımsız apartmanlar](/windows/win32/cossdk/neutral-apartments)
