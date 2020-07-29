---
title: Threading (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: e08d25df07ad881c8843953d01d9074c815ddb85
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193074"
---
# <a name="threading-c"></a>iş parçacığı oluşturma (C++)

COM nesnesi için iş parçacığı modelini belirtir.

## <a name="syntax"></a>Söz dizimi

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

Varsayılan değer: `apartment`.

## <a name="remarks"></a>Açıklamalar

**İş parçacığı** C++ özniteliği oluşturulan. IDL dosyasında görünmez, ancak com nesnenizin uygulamasında kullanılacaktır.

ATL projelerinde, [coclass](coclass.md) özniteliği de varsa, *model* tarafından belirtilen Iş parçacığı modeli [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sınıfına öznitelik tarafından yerleştirilen şablon parametresi olarak geçirilir `coclass` .

**İş parçacığı** özniteliği bir [event_source](event-source.md)erişimi de korur.

## <a name="example"></a>Örnek

**İş parçacığı**örneği kullanımı için [lisanslı](licensed.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM öznitelikleri](com-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Bağımsız apartmanlar](/windows/win32/cossdk/neutral-apartments)
