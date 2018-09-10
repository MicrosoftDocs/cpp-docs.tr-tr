---
title: -I (ek içeren dizinler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
dev_langs:
- C++
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 506f0900cfc7ef5f84e11b2c76d4b593f81d10ba
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109090"
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

1.  Kaynak dosyayı içeren dizinler.

2.  İle belirtilen dizinlerde **/I** CL bunları karşılaştığında sırada seçeneği.

3.  Belirtilen dizinleri **INCLUDE** ortam değişkeni.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

2.  Tıklayın **C/C++** klasör.

3.  Tıklayın **genel** özellik sayfası.

4.  Değiştirme **ek içerik dizinleri** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Örnek
Aşağıdaki komutu şu sırayla MAIN.c tarafından talep edilen dahil edilme dosyalarını arar: ilk MAIN.c, ardından içinde \INCLUDE dizini'a ve ardından \MY\INCLUDE dizinde içeren ve son olarak dizinler atanmış EKLEMEYLE dizinde ortam değişkeni.

```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```  

## <a name="see-also"></a>Ayrıca Bkz.
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)