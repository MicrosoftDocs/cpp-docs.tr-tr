---
title: Bağlayıcı Araçları Hatası LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: b112c4498913c18d82ce8fbc4f6c6d211b906263
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431245"
---
# <a name="linker-tools-error-lnk1301"></a>Bağlayıcı Araçları Hatası LNK1301

LTCG clr modülleri bulundu, /LTCG:parameter ile uyumsuz

/ CLR ve /GL ile derlenmiş bir modül için profil temelli en iyileştirmeler biriyle birlikte Bağlayıcısı/LTCG (PGO) parametrelerinin geçirildi.

Profil temelli en iyileştirmeler, / CLR modülleri için desteklenmez.

Daha fazla bilgi için bkz.:

- [/GL (Bütün Program İyileştirmesi)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (Bağlama Zamanı Kodu Oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. / CLR ile derlenmiyor veya PGO parametrelerden biri için/LTCG ile bağlamayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK1301 oluşturur:

```
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```