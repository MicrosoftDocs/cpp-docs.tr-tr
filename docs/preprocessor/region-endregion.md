---
title: region, endregion
ms.date: 10/18/2018
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
ms.openlocfilehash: c73a90aa2be83d643b74dde4645081e89da3ff73
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037940"
---
# <a name="region-endregion"></a>region, endregion

`#pragma region` Genişlet veya daralt kullanarak bir kod bloğunu belirtmenizi sağlar [anahat oluşturma özelliği](/visualstudio/ide/outlining) Visual Studio Kod Düzenleyicisi'nin.

## <a name="syntax"></a>Sözdizimi

```
#pragma region name
#pragma endregion comment
```

### <a name="parameters"></a>Parametreler

*comment*<br/>
(İsteğe bağlı) Kod Düzenleyicisi'nde görüntüleyen bir açıklama.

*name*<br/>
(İsteğe bağlı) Bölge adı.  Bu ad, Kod Düzenleyicisi'nde görüntülenir.

## <a name="remarks"></a>Açıklamalar

`#pragma endregion` sonunu işaretleyen bir `#pragma region` blok.

A `#region` blok sonlandırıldı, ile `#pragma endregion`.

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

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)