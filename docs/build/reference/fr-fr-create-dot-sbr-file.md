---
title: -FR, -Fr (oluşturun. SBR dosyası) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BrowseInformation
- VC.Project.VCCLCompilerTool.BrowseInformation
- /fr
- VC.Project.VCCLCompilerTool.BrowseInformationFile
- VC.Project.VCCLWCECompilerTool.BrowseInformationFile
dev_langs:
- C++
helpviewer_keywords:
- /FR compiler option [C++]
- -FR compiler option [C++]
- FR compiler option [C++]
- symbolic browser information
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6afcd4aa8ba2e86d687739bc3891f45f2da5672c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379172"
---
# <a name="fr-fr-create-sbr-file"></a>/FR, /Fr (.Sbr Dosyası Oluştur)

.SBR dosyaları oluşturur.

## <a name="syntax"></a>Sözdizimi

```
/FR[pathname[\filename]]
/Fr[pathname[\filename]]
```

## <a name="remarks"></a>Açıklamalar

Derleme işlemi sırasında Microsoft Gözat bilgi dosya Bakımı yardımcı programı (BSCMAKE) oluşturmak için bu dosyaları kullanan bir. BSC dosyası, gözatma bilgilerini görüntülemek için kullanılır.

**/FR** tam sembolik bilgilerle .sbr dosyası oluşturur.

**/FR** yerel değişkenlerde bilgileri olmadan .sbr dosyası oluşturur.

Siz belirtmezseniz `filename`, kaynak dosyası olarak aynı temel adlı .sbr dosyası alır.

**/FR** kullanım dışıdır; kullanın **/FR** yerine. Daha fazla bilgi için bkz: kullanım dışı ve kaldırıldı derleyici seçeneklerinde [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).

> [!NOTE]
>  .Sbr uzantısı değiştirmeyin. BSCMAKE Ara dosyaları uzantıya sahip olmasını gerektirir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Gezinti bölmesinde **C/C++**, **göz atma bilgisi** özellik sayfası.

1. Değiştirme **Gözat bilgi dosyası** veya **göz atma bilgisi etkinleştirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)