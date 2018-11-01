---
title: '/FU (Zorlanan #using Dosyasını Adlandır)'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
ms.openlocfilehash: ecd9290336cfd6efd183bdd701f1d447b7ddaf2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492098"
---
# <a name="fu-name-forced-using-file"></a>/FU (Zorlanan #using Dosyasını Adlandır)

Alternatif dosya adı olarak kullanabileceğiniz bir derleyici seçeneği [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) kaynak kodundaki.

## <a name="syntax"></a>Sözdizimi

> **/FU** *dosyası*

## <a name="arguments"></a>Arguments

*Dosya*<br/>
Bu derlemeye başvurmak için meta veri dosyası belirtir.

## <a name="remarks"></a>Açıklamalar

/FU anahtarı yalnızca bir dosya adı alır. Birden çok dosyayı belirtmek için her biri ile /FU kullanın.

C + kullanıyorsanız +/ CLI ve kullanmak için meta verileri başvuru [arkadaş derlemeleri](../../dotnet/friend-assemblies-cpp.md) özelliğini kullanamaz **/FU**. Kullanarak kod meta verilerde başvurmalıdır `#using`— ile birlikte `[as friend]` özniteliği. Arkadaş derlemeleri desteklenmez Visual C++ bileşeni uzantılarında C + +/ CX.

Bir derleme veya modül için ortak dil çalışma zamanı (CLR) oluşturma hakkında daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md). C + oluşturma hakkında daha fazla bilgi için +/ CX'deki bkz [uygulamaları ve kitaplıkları oluşturmak](../../cppcx/building-apps-and-libraries-c-cx.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Gelişmiş** özellik sayfası.

1. Değiştirme **zorla #using** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)