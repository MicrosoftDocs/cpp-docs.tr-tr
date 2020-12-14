---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1313'
title: Bağlayıcı Araçları Hatası LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 1c10038def9a448645e80ae10fc47d4372769b58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310738"
---
# <a name="linker-tools-error-lnk1313"></a>Bağlayıcı Araçları Hatası LNK1313

> IJW/yerel modül algılandı; saf modüllerle bağlanamaz

## <a name="remarks"></a>Açıklamalar

Geçerli Visual C++ sürümü, yerel veya karma yönetilen/yerel. obj dosyalarını **/clr: Pure** ile derlenen. obj dosyalarıyla bağlamayı desteklemez.

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
