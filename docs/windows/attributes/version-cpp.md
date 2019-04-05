---
title: Sürüm (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: fe1df9e12b9adbf9ce55978fd3479f7e740ddc96
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025758"
---
# <a name="version-c"></a>sürüm (C++)

Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parametreler

*sürüm*<br/>
Sürüm numarasını `coclass`. Belirtilmezse, 1.0 .idl dosyasında yer alır.

## <a name="remarks"></a>Açıklamalar

**Sürüm** C++ özniteliği ile aynı işlevlere sahip [sürüm](/windows/desktop/Midl/version) MIDL özniteliği ve oluşturulan .idl dosyasına üzerinden geçirilir.

## <a name="example"></a>Örnek

Bkz: [bağlanabilir](bindable.md) örnek kullanımını örneğin **sürüm**.

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

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)