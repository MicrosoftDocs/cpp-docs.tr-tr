---
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
ms.openlocfilehash: 4a01e04582ac81d678aa0702945c62ee974a4428
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222380"
---
# <a name="region-endregion-pragmas"></a>region, endregion pragması

`#pragma region`Visual Studio Code düzenleyicisinin ana [hat özelliğini](/visualstudio/ide/outlining) kullanırken genişletebileceğiniz veya daraltabileceğiniz bir kod bloğu belirtmenize olanak tanır.

## <a name="syntax"></a>Sözdizimi

> **#pragma bölgesi** *ad*\
> **#pragma endregion** *Açıklama*

### <a name="parameters"></a>Parametreler

*açıklamanın*\
Seçim Kod düzenleyicisinde görüntülenecek bir açıklama.

*ada*\
Seçim Bölgenin adı. Bu ad, kod düzenleyicisinde görüntülenir.

## <a name="remarks"></a>Açıklamalar

`#pragma endregion`bir `#pragma region` bloğun sonunu işaretler.

Bir `#region` bloğun bir `#pragma endregion` yönerge tarafından sonlandırılması gerekir.

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
