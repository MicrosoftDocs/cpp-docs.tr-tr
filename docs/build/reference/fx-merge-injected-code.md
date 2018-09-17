---
title: -Fx (eklenen kodu Birleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExpandAttributedSource
- /Fx
- VC.Project.VCCLCompilerTool.ExpandAttributedSource
dev_langs:
- C++
helpviewer_keywords:
- Fx compiler option [C++]
- -Fx compiler option [C++]
- injected code
- merging injected code
- /Fx compiler option [C++]
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bd95ea00a63f28f04874f873cf0a4e991fac0fc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710527"
---
# <a name="fx-merge-injected-code"></a>/Fx (Eklenen Kodu Birleştir)

Eklenen kodu kaynak birleştirilmiş ile her kaynak dosyasının bir kopyasını oluşturur.

## <a name="syntax"></a>Sözdizimi

```
/Fx
```

## <a name="remarks"></a>Açıklamalar

Özgün bir kaynak dosyasından birleştirilmiş kaynak dosyası ayırt etmek için **/Fx** .mrg uzantı arasında dosya uzantısı ve dosya adını ekler. Örneğin, bir dosya adlı öznitelik kodu içeren MyCode.cpp ve ile oluşturulmuş **/Fx** aşağıdaki kodu içeren MyCode.mrg.cpp adlı bir dosya oluşturur:

```
//+++ Start Injected Code
[no_injected_text(true)];      // Suppress injected text, it has
                               // already been injected
#pragma warning(disable: 4543) // Suppress warnings about skipping
                               // injected text
#pragma warning(disable: 4199) // Suppress warnings from attribute
                               // providers
//--- End Injected Code
```

Bir .mrg dosyasında nedeniyle bir öznitelik eklenmiş kod şu şekilde ayrılır:

```
//+++ Start Injected Code
...
//--- End Injected Code
```

[No_injected_text](../../windows/no-injected-text.md) özniteliği olmadan reinjected metin .mrg dosyanın derleme için sağlayan bir .mrg dosyasında gömülüdür.

.Mrg kaynak dosyası derleyici tarafından eklenmiş kaynak kodunu bir temsilini olması amaçlanmıştır bilmeniz gerekir. .Mrg dosyası değil derleme veya tam olarak özgün kaynak dosyası olarak çalıştırın.

Makrolar .mrg dosyasında genişletilmiş değil.

Programınızı eklenen kodu kullanan bir üstbilgi dosyası içeriyorsa **/Fx** oluşturur bir. mrg.h dosya, üst bilgisi için. **/FX** olmayan birleştirme eklenen kodu kullanmayan dosyaları içermez.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Çıkış dosyalarını** özellik sayfası.

1. Değiştirme **öznitelikli kaynağı Genişlet** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)