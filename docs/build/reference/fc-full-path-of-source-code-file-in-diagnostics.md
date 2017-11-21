---
title: "-FC (kaynak kodu dosyasının tanılamadaki tam yolu) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
dev_langs: C++
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c9c612dfa300ff42d90988edb77601619fdd4b3c
ms.sourcegitcommit: ce115fcfb20b4fbc198f0f7b6d0ca3e94d7ce947
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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

- c:\test\compiler_option_FC.cpp(5): hata C2143: sözdizimi hatası: eksik ';' önce '}'

**/FC** kullanırken bir dosya adı tam yolunu görmek istiyorsanız aynı zamanda gereken &#95; &#95; Dosya &#95; &#95; Makro.  Bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md) hakkında daha fazla bilgi &#95; &#95; Dosya &#95; &#95;.

**/FC** seçeneği kapsanan olarak **/zı**. Hakkında daha fazla bilgi için **/zı**, bkz: [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Genişletme **yapılandırma özellikleri** düğümü.

1. Genişletme **C/C++** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **kullanım tam yollarını** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)