---
description: Microsoft C/C++ içindeki Region ve endregion yönergeleri hakkında daha fazla bilgi edinin pragma
title: Bölge ve endregion pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragma, region
- pragma, endregion
- endregion pragma
- region pragma
no-loc:
- pragma
ms.openlocfilehash: 68964cd2cab4ff344a8319f970f7ee94be4d378d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713291"
---
# <a name="region-and-endregion-no-locpragma"></a>`region`ve `endregion`pragma

`#pragma region` Visual Studio düzenleyicisinin ana [hat özelliğini](/visualstudio/ide/outlining) kullanırken genişletebileceğiniz veya daraltabileceğiniz bir kod bloğu belirtmenize olanak tanır.

## <a name="syntax"></a>Syntax

> **`#pragma region`***ad*\
> **`#pragma endregion`***Açıklama*

### <a name="parameters"></a>Parametreler

*açıklamanın*\
Seçim Kod düzenleyicisinde görüntülenecek bir açıklama.

*ada*\
Seçim Bölgenin adı. Bu ad, kod düzenleyicisinde görüntülenir.

## <a name="remarks"></a>Açıklamalar

`#pragma endregion` bir bloğun sonunu işaretler `#pragma region` .

Bir `#pragma region` bloğun bir yönerge tarafından sonlandırılması gerekir `#pragma endregion` .

## <a name="example"></a>Örnek

```cpp
// pragma_directives_region.cpp
#pragma region Region_1
void Test() {}
void Test2() {}
void Test3() {}
#pragma endregion Region_1

int main() {}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
