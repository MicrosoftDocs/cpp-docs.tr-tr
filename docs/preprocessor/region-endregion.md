---
description: 'Şu konuda daha fazla bilgi edinin: bölge, endregion pragmaları'
title: region, endregion pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
ms.openlocfilehash: a12305240f0c05913d16c5f26fb64661fc08e736
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167428"
---
# <a name="region-endregion-pragmas"></a>region, endregion pragması

`#pragma region` Visual Studio Code düzenleyicisinin ana [hat özelliğini](/visualstudio/ide/outlining) kullanırken genişletebileceğiniz veya daraltabileceğiniz bir kod bloğu belirtmenize olanak tanır.

## <a name="syntax"></a>Syntax

> **#pragma bölge** *adı*\
> **#pragma endregion** *açıklaması*

### <a name="parameters"></a>Parametreler

*açıklamanın*\
Seçim Kod düzenleyicisinde görüntülenecek bir açıklama.

*ada*\
Seçim Bölgenin adı. Bu ad, kod düzenleyicisinde görüntülenir.

## <a name="remarks"></a>Açıklamalar

`#pragma endregion` bir bloğun sonunu işaretler `#pragma region` .

Bir `#region` bloğun bir yönerge tarafından sonlandırılması gerekir `#pragma endregion` .

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
