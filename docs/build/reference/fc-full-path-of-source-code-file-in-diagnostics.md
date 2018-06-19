---
title: -FC (kaynak kodu dosyasının tanılamadaki tam yolu) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
dev_langs:
- C++
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a721b6887b6c5c07d96a79b06f05e6d7855250b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373211"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (Kaynak Kodu Dosyasının Tanılamadaki Tam Yolu)

Kaynak kodu dosyaları derleyici tanılama geçirilen tam yolunu görüntülenecek derleyici neden olur.

## <a name="syntax"></a>Sözdizimi

> /FC

## <a name="remarks"></a>Açıklamalar

Aşağıdaki kod örneği göz önünde bulundurun:

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

Olmadan **/FC**, tanılama metnini Bu tanılama metne benzer görünür:

- compiler_option_FC.cpp(5): hata C2143: sözdizimi hatası: eksik ';' önce '}'

İle **/FC**, tanılama metnini Bu tanılama metne benzer görünür:

- c:\test\compiler_option_fc.cpp(5): hata C2143: sözdizimi hatası: eksik ';' önce '}'

 **/FC** kullanırken bir dosya adı tam yolunu görmek istiyorsanız aynı zamanda gereken &#95; &#95;dosya&#95; &#95; makrosu. Bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md) hakkında daha fazla bilgi için &#95; &#95;dosya&#95;&#95;.

**/FC** seçeneği kapsanan olarak **/zı**. Hakkında daha fazla bilgi için **/zı**, bkz: [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md).

**/FC** küçük tam yollarında çıkarır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Gelişmiş** özellik sayfası.

1. Değiştirme **kullanım tam yollarını** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
