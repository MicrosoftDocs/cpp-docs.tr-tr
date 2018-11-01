---
title: (out C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: 15b82ddca42f9b70ac16538cea19f8aedd799c05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574453"
---
# <a name="out-c"></a>out (C++)

Çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülen işaretçi parametrelerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[out]
```

## <a name="remarks"></a>Açıklamalar

**Kullanıma** C++ özniteliği ile aynı işlevlere sahip [kullanıma](/windows/desktop/Midl/out-idl) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](bindable.md) örnek kullanımı için **kullanıma**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Parametre arabirimi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)