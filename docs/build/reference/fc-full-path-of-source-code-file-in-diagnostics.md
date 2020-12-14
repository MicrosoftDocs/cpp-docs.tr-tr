---
description: Daha fazla bilgi edinin:/FC (kaynak kodu dosyasının Tanılamadaki Tam yolu)
title: /FC (Kaynak Kodu Dosyasının Tanılamadaki Tam Yolu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 01d1148a32179a7c605a19dc7f2856b7697ae6fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200682"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (Kaynak Kodu Dosyasının Tanılamadaki Tam Yolu)

Derleyicinin, tanılamada derleyiciye geçirilen kaynak kodu dosyalarının tam yolunu görüntülemesine neden olur.

## <a name="syntax"></a>Syntax

> /FC

## <a name="remarks"></a>Açıklamalar

Aşağıdaki kod örneğini göz önünde bulundurun:

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

**/FC** olmadan, tanılama metni bu tanılama metnine benzer şekilde görünür:

- compiler_option_FC. cpp (5): hata C2143: sözdizimi hatası: '} ' öncesinde '; ' eksik

**/FC** ile, tanılama metni bu tanılama metnine benzer şekilde görünür:

- c:\test\ compiler_option_fc. cpp (5): hata C2143: sözdizimi hatası: '} ' öncesinde '; ' eksik

**/FC** , &#95;&#95;File&#95;&#95; makrosunu kullanırken bir dosya adının tam yolunu görmek isterseniz de gereklidir.  &#95;&#95;dosya&#95;&#95; hakkında daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md) .

**/FC** seçeneği **/Zi** tarafından kapsanıyor. **/Zi** hakkında daha fazla bilgi için bkz. [/Z7,/ZI,/ZI (hata ayıklama bilgileri biçimi)](z7-zi-zi-debug-information-format.md).

**/FC** küçük harfli tam yolları verir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **Gelişmiş** özellik sayfasını seçin.

1. **Tam yolları kullan** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
