---
description: Daha fazla bilgi edinin:/ı (ek ekleme dizinleri)
title: /I (Ek içeren dizinler)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
ms.openlocfilehash: ad44abec28bbb87f91f449765a9ea2f30f2bffa8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191348"
---
# <a name="i-additional-include-directories"></a>/I (Ek içeren dizinler)

İçerme dosyaları için aranan dizinler listesine bir dizin ekler.

## <a name="syntax"></a>Syntax

> **/İ**[]*dizini*

### <a name="arguments"></a>Arguments

*dizinden*<br/>
İçerme dosyaları için aranan dizinler listesine eklenecek dizin.

## <a name="remarks"></a>Açıklamalar

Birden fazla dizin eklemek için bu seçeneği birden çok kez kullanın. Dizinler yalnızca belirtilen içerme dosyası bulunana kadar aranır.

Bu seçeneği ([/x (Standart Içerme yolları yoksay)](x-ignore-standard-include-paths.md)) seçeneğiyle kullanabilirsiniz.

Derleyici dizinleri aşağıdaki sırayla arar:

1. Çift tırnak biçiminde bir [#include yönergesi](../../preprocessor/hash-include-directive-c-cpp.md) kullanılarak belirtilmişse, önce yerel dizinleri arar. Arama, **#include** ifadesini içeren dosyayla aynı dizinde başlar. Bu dosyayı bulamazsa, açık olan içerme dosyalarının dizinlerinde açıldıkları ters sırada arama yapar. Arama, üst öğe ekleme dosyası dizininde başlar ve herhangi bir doğru üst öğe içerme dosyasının dizinleriyle devam eder.

1. Açılı ayraç biçiminde bir **#include** yönergesi kullanılarak belirtilmişse veya yerel dizin araması başarısız olduysa, **/ı** seçeneği KULLANıLARAK belirtilen dizinleri, CL 'nin komut satırında karşılaştığı sırayla arar.

1. **Include** ortam değişkeninde belirtilen dizinler.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** özellik sayfasını seçin.

1. **Ek Içerme dizinleri** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut, ana. c tarafından istenen içerme dosyalarını şu sırayla arar: Ilk olarak, Çift tırnaklar kullanılarak belirtilmişse yerel dosyalar aranır. Sonra, arama \ içerme dizininde, sonra \MY\INCLUDE dizininde ve son olarak DAHIL etme ortamı değişkenine atanan dizinlerde devam eder.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
