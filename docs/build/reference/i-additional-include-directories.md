---
title: /I (Ek İçeren Dizinler)
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
ms.openlocfilehash: b922a4472246bb13bfed4022f2f85061c5d1217b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563871"
---
# <a name="i-additional-include-directories"></a>/I (Ek İçeren Dizinler)

Bir dizin dahil etme dosyaları için Aranan dizinleri listesine ekler.

## <a name="syntax"></a>Sözdizimi

```
/I[ ]directory
```

## <a name="arguments"></a>Arguments

*Dizin*<br/>
Dizinleri listesine eklenecek dizine dahil etme dosyaları için Aranan.

## <a name="remarks"></a>Açıklamalar

Birden fazla dizin eklemek için bu seçeneği birden çok kez kullanın. Yalnızca belirlenen içerme dosyasına bulunana kadar dizinlerde arama yapılır.

Ignore Standard INCLUDE Paths ile bu seçeneği kullanabilirsiniz ([/X (Ignore Standard INCLUDE Paths)](../../build/reference/x-ignore-standard-include-paths.md)) seçeneği.

Derleyici dizinleri şu sırayla arar:

1. Kaynak dosyayı içeren dizinler.

1. İle belirtilen dizinlerde **/I** CL bunları karşılaştığında sırada seçeneği.

1. Belirtilen dizinleri **INCLUDE** ortam değişkeni.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **genel** özellik sayfası.

1. Değiştirme **ek içerik dizinleri** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komutu şu sırayla MAIN.c tarafından talep edilen dahil edilme dosyalarını arar: ilk MAIN.c, ardından içinde \INCLUDE dizini'a ve ardından \MY\INCLUDE dizinde içeren ve son olarak dizinler atanmış EKLEMEYLE dizinde ortam değişkeni.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)