---
title: /WL (Tek Satır Tanılamayı Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- /wl
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
ms.openlocfilehash: b1ded1cd18eb75ed47b76c1353ad82a7fa497ba9
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988572"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (Tek Satır Tanılamayı Etkinleştir)

Bir hata veya uyarı iletisine ek bilgi ekler.

## <a name="syntax"></a>Sözdizimi

```
/WL
```

## <a name="remarks"></a>Açıklamalar

C++ Derleyiciye ait hata ve uyarı iletilerinin ardından, varsayılan olarak yeni bir satırda görüntülenen ek bilgiler gelebilir. Komut satırından derlerken, ek bilgi satırı hata veya uyarı iletisine eklenebilir. Bu işlem, derleme çıktılarınızı bir günlük dosyasına yakalayıp, ardından tüm hataları ve uyarıları bulmak için bu günlüğü işlemek için istenebilir. Noktalı virgül, hata veya uyarı iletisini ek satırdan ayırır.

Tüm hata ve uyarı iletilerinin ek bir bilgi satırı yoktur. Aşağıdaki kod, ek bir bilgi satırı içeren bir hata oluşturur; **/WL**kullandığınızda etkiyi test etmenize olanak tanır.

```cpp
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  klasörüne tıklayın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
