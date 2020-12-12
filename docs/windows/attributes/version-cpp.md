---
description: 'Daha fazla bilgi edinin: sürüm (C++)'
title: sürüm (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 5b6d13e59b36fe37d71c9e2cca6fe7d75587f77b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118309"
---
# <a name="version-c"></a>sürüm (C++)

Bir sınıfın birden çok sürümü arasında belirli bir sürümü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parametreler

*Sürüm*<br/>
Öğesinin sürüm numarası `coclass` . Belirtilmemişse, 1,0. IDL dosyasına yerleştirilir.

## <a name="remarks"></a>Açıklamalar

**Sürüm** C++ özniteliği, [Version](/windows/win32/Midl/version) MIDL özniteliğiyle aynı işlevselliğe sahiptir ve oluşturulan. IDL dosyasına geçirilir.

## <a name="example"></a>Örnek

**Sürümün** örnek kullanımı için [bağlanabilir](bindable.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
