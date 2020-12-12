---
description: 'Hakkında daha fazla bilgi edinin: vi_progid'
title: vi_progid (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: 766ebcee636b3fb0bcdb1aeabd53ee0e977ca790
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327193"
---
# <a name="vi_progid"></a>vi_progid

ProgID 'nin sürümden bağımsız bir biçimini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Parametreler

*ada*<br/>
Nesneyi temsil eden sürümden bağımsız ProgID.

ProgID 'ler, COM/ActiveX nesnelerini tanımlamak için kullanılan sınıf tanımlayıcısının (CLSID) okunabilir bir sürümünü sunar.

## <a name="remarks"></a>Açıklamalar

**Vi_progid** C++ özniteliği, bir com nesnesi için sürümden bağımsız bir ProgID belirlemenizi sağlar. Bir ProgID *name1. AD2. Version* biçiminde bulunur. Sürümden bağımsız bir ProgID 'nin *sürümü* yok. Hem hem de `progid` **vi_progid** özniteliklerini belirtmek mümkündür `coclass` . **Vi_progid** belirtmezseniz, sürümden bağımsız ProgID, [ProgID](progid.md) özniteliği tarafından belirtilen değerdir.

**vi_progid** `coclass` özniteliği, yani **vi_progid** belirtirseniz, `coclass` ve **vi_progid** özniteliklerini belirterek aynı şey olur.

**Vi_progid** özniteliği, bir sınıfın belirtilen ad altında otomatik olarak kaydedilmesine neden olur. Oluşturulan. IDL dosyası ProgID değerini görüntülemez.

ATL projelerinde, [coclass](coclass.md) özniteliği de varsa, belirtilen ProgID `GetVersionIndependentProgID` işlevi (özniteliği tarafından eklenir) tarafından kullanılır `coclass` .

## <a name="example"></a>Örnek

**Vi_progid** örnek bir kullanımı için bkz. [coclass](coclass.md) örneği.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[ProgID anahtarı](/windows/win32/com/-progid--key)
