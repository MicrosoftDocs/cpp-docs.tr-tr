---
description: Daha fazla bilgi edinin:/Zo (Iyileştirilmiş hata ayıklamayı geliştirme)
title: /Zo (En İyi Duruma Getirilmiş Hata Ayıklamayı İyileştirme)
ms.date: 11/04/2016
f1_keywords:
- -Zo
- /Zo
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
ms.openlocfilehash: b2d5fb37205a6cf58492d7e6bc9080867ebacf54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224354"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (En İyi Duruma Getirilmiş Hata Ayıklamayı İyileştirme)

Hata ayıklama olmayan derlemelerde iyileştirilmiş kod için gelişmiş hata ayıklama bilgileri oluşturun.

## <a name="syntax"></a>Syntax

```cpp
/Zo[-]
```

## <a name="remarks"></a>Açıklamalar

**/Zo** derleyici anahtarı iyileştirilmiş kod için gelişmiş hata ayıklama bilgileri oluşturur. İyileştirme yerel değişkenler için Yazmaçları, kodu yeniden sıralama, vektörleştirme döngülerini ve satır içi işlev çağrılarını kullanabilir. Bu iyileştirmeler, kaynak kodu ve derlenen nesne kodu arasındaki ilişkiyi gizlebilirler. **/Zo** anahtarı, derleyiciye yerel değişkenler ve satır içi işlevler için ek hata ayıklama bilgileri oluşturmasını söyler. Visual Studio hata ayıklayıcısında en iyi duruma getirilmiş kod ile adımlayın ve sonra, **oto**, **Yereller** ve **izleme** pencerelerinde değişkenleri görmek için bunu kullanın. Ayrıca, yığın izlemelerinin WinDBG hata ayıklayıcısında satır içine alınmış işlevleri göstermesini sağlar. Devre dışı iyileştirmeleri olan hata ayıklama derlemeleri ([/od](od-disable-debug.md)), **/zo** belirtildiğinde oluşturulan ek hata ayıklama bilgileri gerektirmez. İyileştirme açıkken yayın yapılandırmalarının hatalarını ayıklamak için **/zo** anahtarını kullanın. Optimizasyon anahtarları hakkında daha fazla bilgi için bkz. [/O Seçenekler (kodu iyileştirme)](o-options-optimize-code.md). **/Zi** veya **/Z7** ile hata ayıklama bilgilerini belirttiğinizde, **/zo** seçeneği Visual Studio 'da varsayılan olarak etkindir. Bu derleyici seçeneğini açıkça devre dışı bırakmak için **/zo-** belirtin.

**/Zo** anahtarı Visual Studio 2013 güncelleştirme 3 ' den başlayarak kullanılabilir ve daha önce belgelenmemiş **/D2zi +** anahtarının yerini almıştır.

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Visual Studio 'da/Zo derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** özelliğini içerecek şekilde değiştirin `/Zo` ve ardından **Tamam**' ı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O seçenekler (kodu Iyileştirme)](o-options-optimize-code.md)<br/>
[/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](z7-zi-zi-debug-information-format.md)<br/>
[Düzenle ve Devam Et](/visualstudio/debugger/edit-and-continue)
