---
title: sürüm (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 9a432267632b1f2a716a833a485b182cd93a27e2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514880"
---
# <a name="version-c"></a>sürüm (C++)

Bir sınıfın birden çok sürümü arasında belirli bir sürümü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parametreler

*version*<br/>
Öğesinin sürüm numarası `coclass`. Belirtilmemişse, 1,0. IDL dosyasına yerleştirilir.

## <a name="remarks"></a>Açıklamalar

**Version** C++ özniteliği [Version](/windows/win32/Midl/version) MIDL özniteliğiyle aynı işlevselliğe sahiptir ve oluşturulan. IDL dosyasına geçirilir.

## <a name="example"></a>Örnek

**Sürümün**örnek kullanımı için [bağlanabilir](bindable.md) örneğe bakın.

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

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)