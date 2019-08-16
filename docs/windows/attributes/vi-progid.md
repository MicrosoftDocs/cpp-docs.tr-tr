---
title: vi_progid (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: fbf5ab2bc4263356a1cfcf789865a3f7e286ccd7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514859"
---
# <a name="vi_progid"></a>vi_progid

ProgID 'nin sürümden bağımsız bir biçimini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Parametreler

*name*<br/>
Nesneyi temsil eden sürümden bağımsız ProgID.

ProgID 'ler, COM/ActiveX nesnelerini tanımlamak için kullanılan sınıf tanımlayıcısının (CLSID) okunabilir bir sürümünü sunar.

## <a name="remarks"></a>Açıklamalar

**Vi_progid** C++ özniteliği bir com nesnesi için sürümden bağımsız bir ProgID belirlemenizi sağlar. Bir ProgID *name1. AD2. Version*biçiminde bulunur. Sürümden bağımsız bir ProgID 'nin *sürümü*yok. Bir `progid` üzerinde`coclass`hem hem de **vi_progid** özniteliklerini belirtmek mümkündür. **Vi_progid**belirtmezseniz, Version-Dependent ProgID, [ProgID](progid.md) özniteliği tarafından belirtilen değerdir.

`coclass` vi_progid özniteliği, yani vi_progid belirtirseniz, ve vi_progid özniteliklerini belirten şeydir `coclass` .

**Vi_progid** özniteliği, bir sınıfın belirtilen ad altında otomatik olarak kaydedilmesine neden olur. Oluşturulan. IDL dosyası ProgID değerini görüntülemez.

ATL projelerinde, [coclass](coclass.md) özniteliği de varsa, belirtilen ProgID `GetVersionIndependentProgID` işlevi `coclass` (özniteliği tarafından eklenir) tarafından kullanılır.

## <a name="example"></a>Örnek

Örnek bir **vi_progid**kullanımı için [coclass](coclass.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[ProgID anahtarı](/windows/win32/com/-progid--key)
