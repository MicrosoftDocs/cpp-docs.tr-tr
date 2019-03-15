---
title: /FR, /Fr (.Sbr Dosyası Oluştur)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BrowseInformation
- VC.Project.VCCLCompilerTool.BrowseInformation
- /fr
- VC.Project.VCCLCompilerTool.BrowseInformationFile
- VC.Project.VCCLWCECompilerTool.BrowseInformationFile
helpviewer_keywords:
- /FR compiler option [C++]
- -FR compiler option [C++]
- FR compiler option [C++]
- symbolic browser information
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
ms.openlocfilehash: a75a9d143012dee7946591d708921d6734b2acda
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811881"
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

**/FR** kullanım dışıdır; kullanın **/FR** yerine. Daha fazla bilgi için bkz: kullanım dışı ve kaldırıldı derleyici seçeneklerinde [kategoriye göre listelenmiş derleyici seçenekleri](compiler-options-listed-by-category.md).

> [!NOTE]
>  .Sbr uzantısı değiştirmeyin. BSCMAKE Ara dosyaları uzantıya sahip olmasını gerektirir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Gezinti bölmesinde **C/C++**, **göz atma bilgisi** özellik sayfası.

1. Değiştirme **Gözat bilgi dosyası** veya **göz atma bilgisi etkinleştirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
