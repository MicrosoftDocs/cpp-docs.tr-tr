---
title: -Zo (en iyi duruma getirilmiş hata ayıklamayı iyileştirme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- -Zo
- /Zo
dev_langs:
- C++
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b40f7b4fff1d6df6f5fb818e090ce687f12a7b4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412793"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (En İyi Duruma Getirilmiş Hata Ayıklamayı İyileştirme)

Hata ayıklama olmayan yapılarında iyileştirilmiş kod için Gelişmiş hata ayıklama bilgileri oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
/Zo[-]
```

## <a name="remarks"></a>Açıklamalar

**/Zo** derleyici anahtarı iyileştirilmiş kod için Gelişmiş hata ayıklama bilgileri oluşturur. En iyi duruma getirme yerel değişkenler için kayıt defterlerine, kodu yeniden sıralama, döngüler ve satır içi işlev çağrıları vektör hale getirmeye. Bu iyileştirmeler, kaynak kodu ile derlenen nesne kodu arasındaki ilişkiyi gizlememeniz. **/Zo** yerel değişkenleri ve satır içine alınmış işlevler için ek hata ayıklama bilgisi oluşturmak için derleyicinin anahtar bildirir. Değişkenleri görmek için kullanılmakta **Otolar**, **Yereller**, ve **Watch** adım adım windows kod Visual Studio hata ayıklayıcısında iyileştirilmiş. Ayrıca, satır içine alınmış işlevler WinDBG hata ayıklayıcıda göstermek yığın izlemesi sağlar. Hata ayıklama iyileştirmeleri devre dışı yapıları ([/Od](../../build/reference/od-disable-debug.md)) oluşturulduğunda ek hata ayıklama bilgisi gerekmez **/Zo** belirtilir. Kullanım **/Zo** yayın yapılandırmaları iyileştirme açıkken hata ayıklamak için anahtar. En iyi duruma getirme anahtarları hakkında daha fazla bilgi için bkz. [/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md). **/Zo** seçeneği etkin olduğunda varsayılan olarak Visual Studio ile hata ayıklama bilgilerini belirttiğinizde **/zi** veya **/z7**. Belirtin **/Zo-** açıkça Bu derleyici seçeneğini devre dışı bırakmak için.

**/Zo** anahtarıdır Visual Studio 2013 güncelleştirme 3'te kullanıma ve daha önce belgelenmemiş değiştirir **/d2Zi+** geçin.

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>/Zo derleyici seçeneğini Visual Studio'da ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri**, **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik `/Zo` seçip **Tamam**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O Seçenekler (Kodu İyileştir)](../../build/reference/o-options-optimize-code.md)<br/>
[/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md)<br/>
[Düzenle ve Devam Et](/visualstudio/debugger/edit-and-continue)