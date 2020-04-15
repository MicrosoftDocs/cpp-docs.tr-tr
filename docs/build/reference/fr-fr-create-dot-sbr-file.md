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
ms.openlocfilehash: 58f55811f5d2bb81bc77da38a87c35bae91ce6cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320512"
---
# <a name="fr-fr-create-sbr-file"></a>/FR, /Fr (.Sbr Dosyası Oluştur)

.sbr dosyaları oluşturur.

## <a name="syntax"></a>Sözdizimi

```
/FR[pathname[\filename]]
/Fr[pathname[\filename]]
```

## <a name="remarks"></a>Açıklamalar

> [!WARNING]
> BSCMAKE hala Visual Studio yüklü olmasına rağmen, artık IDE tarafından kullanılmaz. Visual Studio 2008'den bu yana, göz atma ve sembol bilgileri çözüm klasöründe bir SQL Server .sdf dosyasında otomatik olarak depolanır.

Oluşturma işlemi sırasında, Microsoft Gözat Bilgi Dosya Bakım Programı (BSCMAKE) oluşturmak için bu dosyaları kullanır. Gözatma bilgilerini görüntülemek için kullanılan BSC dosyası.

**/FR,** tam sembolik bilgiler içeren bir .sbr dosyası oluşturur.

**/Fr,** yerel değişkenler hakkında bilgi olmadan bir .sbr dosyası oluşturur.

Belirtmezseniz `filename`, .sbr dosyası kaynak dosyayla aynı temel adı alır.

**/Fr** amortismana lı; bunun yerine **/FR** kullanın. Daha fazla bilgi için, [Kategoriye Göre Listelenen Derleyici Seçeneklerinde](compiler-options-listed-by-category.md)Azalan ve Kaldırılan Derleyici Seçenekleri'ne bakın.

> [!NOTE]
> .sbr uzantısını değiştirmeyin. BSCMAKE bu uzantıya sahip olmak için ara dosyaların olmasını gerektirir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Gezinti bölmesinde **C/C++**, **Gözat Bilgileri** özelliği sayfasını seçin.

1. **Gözat Bilgileri Dosyasını** değiştirin veya **Bilgilere Gözat** özelliğini etkinleştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bakın <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>ve .

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
