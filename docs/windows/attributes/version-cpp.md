---
title: sürüm (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: e5fcf80ef753a869b8798d6ab9c8e9f8ecff16fd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165996"
---
# <a name="version-c"></a>sürüm (C++)

Bir sınıfın birden çok sürümü arasında belirli bir sürümü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parametreler

*version*<br/>
`coclass`sürüm numarası. Belirtilmemişse, 1,0. IDL dosyasına yerleştirilir.

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
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
