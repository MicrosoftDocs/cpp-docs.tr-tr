---
title: Bağlayıcı Araçları Hatası LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 03ff61a1f3501b3ea106138e957a657ed064e645
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90683448"
---
# <a name="linker-tools-error-lnk1313"></a>Bağlayıcı Araçları Hatası LNK1313

> IJW/yerel modül algılandı; saf modüllerle bağlanamaz

## <a name="remarks"></a>Açıklamalar

Geçerli Visual C++ sürümü, yerel veya karma yönetilen/yerel. obj dosyalarını **/clr: Pure**ile derlenen. obj dosyalarıyla bağlamayı desteklemez.

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

## <a name="examples"></a>Örnekler

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

Aşağıdaki örnek LNK1313 oluşturacaktır.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```
