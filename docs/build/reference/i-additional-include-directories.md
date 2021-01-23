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
ms.openlocfilehash: 36da00f9a6d5a55e60efd60a941ac3a9b3bfa4ec
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712797"
---
# <a name="i-additional-include-directories"></a>`/I` (Ek ekleme dizinleri)

İçerme dosyaları için aranan dizinler listesine bir dizin ekler.

## <a name="syntax"></a>Syntax

> **`/I`***Dizin*

### <a name="arguments"></a>Bağımsız değişkenler

*dizinden*\
İçerme dosyaları için aranan dizinlerin listesine eklenecek dizin. `/I`Ve *dizini* arasındaki alan isteğe bağlıdır. Boşluk içeren dizinlerin çift tırnak içine alınması gerekir. Dizin mutlak bir yol veya göreli bir yol olabilir.

## <a name="remarks"></a>Açıklamalar

Birden fazla dizin eklemek için bu seçeneği birden çok kez kullanın. Dizinler yalnızca belirtilen içerme dosyası bulunana kadar aranır.

Bu seçeneği ([ `/X` (Standart içerme yolları yoksay)](x-ignore-standard-include-paths.md)seçeneği ile aynı komut satırında kullanabilirsiniz.

Bir [ `#include` yönerge](../../preprocessor/hash-include-directive-c-cpp.md) çift tırnak (veya yerel ilk) biçiminde belirtilebilir, örneğin, `#include "local.h"` . Ya da, örneğin, açılı ayraç (veya Include-Path-First) biçiminde belirtilebilir `#include <iostream>` .

Derleyici dizinleri aşağıdaki sırayla arar:

1. **`#include`** Yönerge çift tırnak formu kullanılarak belirtilmişse, önce yerel dizinleri arar. Arama, yönergeyi içeren dosyayla aynı dizinde başlar **`#include`** . Dosyayı bulamazsa, açık olan ekleme dosyalarının dizinlerindeki bir dahaki sefer açıldıkları ters sırada arama yapar. Arama, üst öğe ekleme dosyası dizininde başlar ve herhangi bir doğru üst öğe içerme dosyasının dizinleriyle devam eder.

1. Yönerge, **`#include`** açılı ayraç biçiminde belirtilmişse veya yerel dizin araması başarısız olduysa, seçeneği kullanılarak belirtilen dizinleri, **`/I`** komut satırında belirtildikleri sırayla arar.

1. Ortam değişkeninde belirtilen dizinler **`INCLUDE`** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** özellik sayfasını seçin.

1. **Ek Içerme dizinleri** özelliğini değiştirin. Bu özellikte bir anda birden fazla dizin belirtebilirsiniz. Dizinler noktalı virgül () ile ayrılmalıdır **`;`** .

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut, aşağıdaki sıraya göre istenen içerme dosyalarını arar *`main.c`* : ilk olarak, Çift tırnaklar kullanılarak belirtilmişse, yerel dosyalar aranır. Sonra, arama *`\include`* dizinde, sonra *`\my\include`* dizinde ve son olarak, ortam değişkenine atanan dizinlerde, **`INCLUDE`** soldan sağa doğru sırada devam eder.

```cmd
CL /I \include /I\my\include main.c
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
