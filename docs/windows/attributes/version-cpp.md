---
title: sürüm (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: b537f56c39c33abc52897cf53ea2cc0fb24ee458
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213807"
---
# <a name="version-c"></a>sürüm (C++)

Bir sınıfın birden çok sürümü arasında belirli bir sürümü tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parametreler

*Sürüm*<br/>
Öğesinin sürüm numarası `coclass` . Belirtilmemişse, 1,0. IDL dosyasına yerleştirilir.

## <a name="remarks"></a>Açıklamalar

**Sürüm** C++ özniteliği, [Version](/windows/win32/Midl/version) MIDL özniteliğiyle aynı işlevselliğe sahiptir ve oluşturulan. IDL dosyasına geçirilir.

## <a name="example"></a>Örnek

**Sürümün**örnek kullanımı için [bağlanabilir](bindable.md) örneğe bakın.

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

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
