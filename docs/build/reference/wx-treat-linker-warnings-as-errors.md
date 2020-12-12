---
description: Daha fazla bilgi edinin:/WX (bağlayıcı uyarılarını hata olarak Işle)
title: /WX (Bağlayıcı Uyarılarını Hata Olarak İşle)
ms.date: 11/04/2016
f1_keywords:
- /WX
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
ms.openlocfilehash: 965c48ff9c9f975350f3c1e54d8090823be8fd2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261040"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Bağlayıcı Uyarılarını Hata Olarak İşle)

```
/WX[:NO]
```

## <a name="remarks"></a>Açıklamalar

/WX, bağlayıcı bir uyarı oluşturursa hiçbir çıkış dosyası oluşturulmasına neden olur.

Bu, derleyici için **/WX** 'e benzerdir (daha fazla bilgi için bkz. [/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](compiler-option-warning-level.md) ). Ancak, derleme için **/WX** 'in belirtilmesi, **/WX** 'in bağlantı aşaması için de geçerli olacağını göstermez; Her araç için açıkça **/WX** belirtmeniz gerekir.

Varsayılan olarak, **/WX** etkin değildir. Bağlayıcı uyarılarını hata olarak değerlendirmek için **/WX** belirtin. **/WX: No** , **/WX** Belirtmemeye benzer.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. Seçeneği **ek seçenekler** kutusuna yazın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
