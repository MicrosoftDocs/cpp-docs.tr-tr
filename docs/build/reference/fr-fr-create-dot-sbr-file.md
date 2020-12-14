---
description: :/FR,/fr (Oluştur) hakkında daha fazla bilgi edinin. Sbr dosyası)
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
ms.openlocfilehash: 9142e7afedb55a7b0f4ed0cdb56e4288524d7afc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200422"
---
# <a name="fr-fr-create-sbr-file"></a>/FR, /Fr (.Sbr Dosyası Oluştur)

. Sbr dosyaları oluşturur.

## <a name="syntax"></a>Syntax

```
/FR[pathname[\filename]]
/Fr[pathname[\filename]]
```

## <a name="remarks"></a>Açıklamalar

> [!WARNING]
> BSCMAKE, Visual Studio ile hala yüklü olsa da artık IDE tarafından kullanılmıyor. Visual Studio 2008 ' den itibaren, gezinme ve sembol bilgileri çözüm klasöründeki bir SQL Server. sdf dosyasında otomatik olarak depolanır.

Oluşturma işlemi sırasında, Microsoft 'A ait bilgi dosyası Bakımı yardımcı programı (BSCMAKE), oluşturmak için bu dosyaları kullanır. BSC dosyası, tarama bilgilerini göstermek için kullanılır.

**/Fr** , tamamen sembolik bilgileri olan bir. sbr dosyası oluşturur.

**/Fr** yerel değişkenler hakkında bilgi içermeyen bir. sbr dosyası oluşturur.

Belirtmezseniz `filename` ,. sbr dosyası kaynak dosyayla aynı temel adı alır.

**/Fr** kullanım dışıdır; Bunun yerine **/fr** kullanın. Daha fazla bilgi için, bkz. [kategoriye göre listelenen derleyici seçeneklerinde](compiler-options-listed-by-category.md)kullanım dışı ve kaldırılmış derleyici seçenekleri.

> [!NOTE]
> . Sbr uzantısını değiştirmeyin. BSCMAKE, ara dosyaların bu uzantıya sahip olmasını gerektirir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Gezinti bölmesinde **C/C++**, **bilgi görüntüle** özellik sayfasını seçin.

1. **Tarama bilgi dosyasını** değiştirin veya **bilgileri görüntüle özelliğini etkinleştirin** .

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A> . ve.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Yol adını belirtme](specifying-the-pathname.md)
