---
title: / SOURCELINK (PDB dosyasında Sourcelink dahil)
ms.date: 08/20/2018
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: a5a01ca56a49791a608c5c836312c7728e9328c3
ms.sourcegitcommit: fe1e21df175cd004d21c6e4659082efceb649a8b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53978289"
---
# <a name="sourcelink-include-source-link-file-in-pdb"></a>/ SOURCELINK (PDB dosyasında kaynak bağlantısı dahil)

Bağlayıcı tarafından oluşturulmuş bir PDB dosyası eklemek için kaynak bağlantısı yapılandırma dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ SOURCELINK:**_dosya adı_

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Kaynak dosyasının nereye alınabilir basit bir yerel dosya yollarını URL'lere eşleşme içeren bir JSON biçimli yapılandırma dosyasını görüntü hata ayıklayıcı tarafından belirtir. Bu dosya biçimi hakkında daha fazla bilgi için bkz. [kaynak bağlantı JSON şeması](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md#source-link-json-schema).

## <a name="remarks"></a>Açıklamalar

Kaynak bağlantısı kaynak ikili dosyalar için hata ayıklama sağlamak için bir dil ve kaynak denetimi belirsiz sistemidir. Visual Studio 2017 sürüm 15,8 başlangıç yerel C++ ikililer için kaynak bağlantısı desteklenir. Kaynak bağlantısı genel bakış için bkz. [kaynak bağlantısı](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md). Projelerinizi kaynak bağlantısı kullanmayı ve projenizin bir parçası olarak SourceLink dosyası oluşturma hakkında daha fazla bilgi için bkz. [kaynak bağlantısı kullanılarak](https://github.com/dotnet/sourcelink#using-source-link-in-c-projects).

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>Visual Studio'da / sourcelink bağlayıcı seçeneğini ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda **/sourcelink:**_filename_ seçip **Tamam** veya **Uygula**yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bu seçenek, bir program eşdeğerini yok.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
