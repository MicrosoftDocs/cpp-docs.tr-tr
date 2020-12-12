---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1301'
title: Bağlayıcı Araçları Hatası LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: ac282aea62836591c6e30abb3030ef2143a78003
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335958"
---
# <a name="linker-tools-error-lnk1301"></a>Bağlayıcı Araçları Hatası LNK1301

LTCG clr modülleri bulundu,/LTCG ile uyumsuz: parametre

/Clr ve/GL ile derlenen bir modül,/LTCG'NIN profil temelli iyileştirme (PGO) parametrelerinden biri ile birlikte bağlayıcıya geçildi.

Profil temelli iyileştirmeler/clr modülleri için desteklenmez.

Daha fazla bilgi için bkz:

- [/GL (bütün program Iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Profil temelli Iyileştirmeler](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. /Clr ile derlememeyin veya PGO parametrelerinden biriyle/LTCG'E bağlamayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1301 oluşturur:

```cpp
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```
