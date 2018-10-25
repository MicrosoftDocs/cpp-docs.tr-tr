---
title: Sürüm (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 95b30d65fe67f2647cb8ca50619f3ab13f167053
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059005"
---
# <a name="version-c"></a>sürüm (C++)

Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Parametreler

*version*<br/>
Sürüm numarasını `coclass`. Belirtilmezse, 1.0 .idl dosyasında yer alır.

## <a name="remarks"></a>Açıklamalar

**Sürüm** C++ özniteliği ile aynı işlevlere sahip [sürüm](/windows/desktop/Midl/version) MIDL özniteliği ve oluşturulan .idl dosyasına üzerinden geçirilir.

## <a name="example"></a>Örnek

Bkz: [bağlanabilir](bindable.md) örnek kullanımını örneğin **sürüm**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)