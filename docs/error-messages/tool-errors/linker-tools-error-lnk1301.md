---
title: Bağlayıcı Araçları Hatası LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: fe64eecfbc9fed57c3748afd5804b76d6e4284a4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990930"
---
# <a name="linker-tools-error-lnk1301"></a>Bağlayıcı Araçları Hatası LNK1301

LTCG clr modülleri bulundu,/LTCG ile uyumsuz: parametre

/Clr ve/GL ile derlenen bir modül,/LTCG'NIN profil temelli iyileştirme (PGO) parametrelerinden biri ile birlikte bağlayıcıya geçildi.

Profil temelli iyileştirmeler/clr modülleri için desteklenmez.

Daha fazla bilgi için bkz.

- [/GL (Bütün Program İyileştirmesi)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (Bağlama Zamanı Kodu Oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Profil Temelli İyileştirmeler](../../build/profile-guided-optimizations.md)

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
