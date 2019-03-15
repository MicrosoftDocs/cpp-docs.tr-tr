---
title: /bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)
ms.date: 11/04/2016
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: a9685834fc3e1de246c9d9d60d206538b744ce3e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809866"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)

**/ bigobj** bir nesne dosyasının içerebileceği bölümlerin sayısını arttırır.

## <a name="syntax"></a>Sözdizimi

```
/bigobj
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir nesne dosyası en çok 65.536 (2 ^ 16) adreslenebilir bölüm. Hangi hedef platform belirtilirse durum budur. **/ bigobj** artırır bu adres kapasitesini 4,294,967,296 (2 ^ 32).

Modüllerinin çoğu hiçbir zaman birden fazla 65.536 bir .obj dosyası oluşturur. Ancak, makinede oluşturulan kod veya şablon kitaplıklarını ağır olarak kullanan yapan kod daha fazla bölüm tutan .obj dosyaları gerekebilir. **/ bigobj** makine tarafından oluşturulan XAML kodu çok sayıda üstbilgi içerdiğinden, Evrensel Windows Platformu (UWP) projeler üzerinde varsayılan olarak etkindir. Bir UWP uygulaması projesi bu seçeneği devre dışı bırakırsanız C1128 derleyici hatasıyla karşılaşabilirsiniz.

Visual C++ 2005'ten önce sevk okuyamaz ile üretilmiş .obj dosyalarını **/bigobj**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
