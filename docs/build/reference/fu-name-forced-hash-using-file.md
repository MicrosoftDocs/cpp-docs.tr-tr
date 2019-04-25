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
ms.openlocfilehash: c47a45208ac5b5c7e0000516ed114c008feda7ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292295"
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

C + kullanıyorsanız +/ CLI ve kullanmak için meta verileri başvuru [arkadaş derlemeleri](../../dotnet/friend-assemblies-cpp.md) özelliğini kullanamaz **/FU**. Kullanarak kod meta verilerde başvurmalıdır `#using`— ile birlikte `[as friend]` özniteliği. Arkadaş derlemeleri görselde desteklenmez C++ bileşen uzantıları C++/CX.

Bir derleme veya modül için ortak dil çalışma zamanı (CLR) oluşturma hakkında daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md). C + oluşturma hakkında daha fazla bilgi için +/ CX'deki bkz [uygulamaları ve kitaplıkları oluşturmak](../../cppcx/building-apps-and-libraries-c-cx.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Gelişmiş** özellik sayfası.

1. Değiştirme **zorla #using** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
