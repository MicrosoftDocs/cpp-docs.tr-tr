---
title: /bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)
ms.date: 03/26/2019
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: 46399dc0c1ff552b4fc963b686ac6aa6df8b6f71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272981"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)

**/ bigobj** bir nesne dosyasının içerebileceği bölümlerin sayısını arttırır.

## <a name="syntax"></a>Sözdizimi

> **/bigobj**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir nesne dosyası en çok 65,279 içerebilir (yaklaşık 2 ^ 16) adreslenebilir bölüm. Ne olursa olsun hangi hedef platform belirtilirse, bu sınır geçerlidir. **/ bigobj** artırır bu adres kapasitesini 4,294,967,296 (2 ^ 32).

Modüllerinin çoğu hiçbir zaman birden fazla 65,279 bölümleri içeren bir .obj dosyası oluşturur. Ancak, makine tarafından oluşturulan kod veya şablon kitaplıklarını ağır olarak kullanan yapan kod daha fazla bölüm tutan .obj dosyaları gerektirebilir. **/ bigobj** makine tarafından oluşturulan XAML kodu çok sayıda üstbilgi içerdiğinden, Evrensel Windows Platformu (UWP) projeler üzerinde varsayılan olarak etkindir. Bir UWP uygulaması projesi bu seçeneği devre dışı bırakırsanız C1128 derleyici hatasıyla kodunuzu oluşturabilir.

PE COFF nesne dosyası biçimi hakkında daha fazla bilgi için bkz: [PE biçimi](/windows/desktop/debug/pe-format) Windows belgelerinde.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Girin **/bigobj** derleyici seçeneğini **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
