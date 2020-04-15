---
title: Visual Studio'da C++ kodlama tercihlerinizi ayarlayın
ms.description: Customize C++ formatting, colors, layout, line numbers, and menus in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: e3a665ead7a314b343ec3320e95b189f83a38a47
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365386"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Visual Studio'da C++ kodlama tercihlerinizi ayarlayın

Visual Studio'yı kişiselleştirerek C++ kodlama deneyiminizi daha kullanışlı, üretken ve keyifli hale getirebilirsiniz. Şunları yapabilirsiniz:

- Menüleri ve araç çubuklarını özelleştirin.
- Pencere düzenini düzenleyin.
- Renk temalarını ayarlayın.
- ClangFormat'ın çeşitli stilleri de dahil olmak üzere C++ biçimlendirme kurallarını belirtin.
- Özel klavye kısayolları oluşturun.

Tercihlerinizi birden çok makine de senkronize edebilir, birden çok tercih kümesi oluşturabilir ve depolayabilir ve bunları takım arkadaşlarıyla paylaşabilirsiniz. Visual Studio Marketplace'ten uzantılar yükleyerek davranışı özelleştirmek için ek seçenekler sunabilirsiniz. Daha fazla bilgi için [Visual Studio IDE'yi Kişiselleştir'e](/visualstudio/ide/personalizing-the-visual-studio-ide)bakın.

## <a name="arrange-window-layout"></a>Pencere düzenini düzenleme

Visual Studio penceresinde, alan ana menüye, araç çubuğuna, kod düzenleyicisine (veya belge penceresine) ve araç pencerelerine (Çözüm Gezgini ve Hata Listesi gibi) ayrılır. Bazı pencereler aynı konumda birbiriyle çakışıyor. Örneğin, Çözüm Gezgini, Sınıf Görünümü, Kaynak Görünümü ve Kaynak Denetim Gezgini'nin tümü aynı varsayılan konumu paylaşır. Çerçevenin altındaki sekmeleri seçerek aralarında geçiş yapabilirsiniz. Bu pencerelerden iki veya daha fazlasını aynı anda görünür hale getirmek için, bunlardan birini başlık çubuğuna göre yeni bir konuma sürüklemeleri gereken bir yer. Visual Studio ana pencere kenarlıklarından birine sabitleyebilir veya yüzdürebilirsiniz.

Aşağıdaki ekran **görüntüsü, Team Explorer** penceresinin varsayılan konumundan kod düzenleyicisinin sol tarafındaki yeni, sabitlenmiş bir konuma sürüklendiğini gösterir. Mavi gölgeli alan, fare düğmesi bırakıldığında pencerenin nereye yerleştirileceğini gösterir.

![Düzen değişikliği vurgulanmış Visual Studio Team Explorer penceresinin ekran görüntüsü](media/window-layout-move-team-explorer.png)

Belge penceresinde, her açık dosya sekmeli bir çerçeveiçinde bulunur. Bu sekmeleri, alet pencereleri gibi yüzdürebilir veya kilitleyebilirsiniz. Daha fazla bilgi için [Visual Studio'daki pencere düzenlerini özelleştir'e](/visualstudio/ide/customizing-window-layouts-in-visual-studio)bakın.

Tüm araç pencerelerini gizlemek ve Kod Düzenleyicisi penceresini en üst düzeye çıkarmak *için, tam ekran modunu*değiştirmek için **Alt** + **Shift** + **Enter** tuşuna basın.

## <a name="set-c-coding-styles-and-formatting"></a>C++ kodlama stillerini ve biçimlendirmeyi ayarlama

Girinti ve ayraç pozisyonları gibi birçok ayrı kod biçimlendirme seçeneği belirtebilirsiniz. Bunu yapmak için **Araçlar** > **Seçenekleri** > **Metin** > **Düzenleyicisi C/C++** > **Biçimlendirme** 'ne gidin (veya **Ctrl + Q** yazın ve "Biçimlendirme"yi arayın). Alternatif olarak, [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html) stillerinden birini (veya kendi özel ClangFormat stilinizi) belirtebilirsiniz.

![ClangFormat seçeneklerinin ekran görüntüsü](media/clang-format-ide.png)

Tüm biçimlendirme seçenekleri hakkında daha fazla bilgi için [Seçenekler, Metin Düzenleyicisi, C/C++, Biçimlendirme'ye](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)bakın.

## <a name="set-the-color-theme"></a>Renk tesini ayarlama

Açık veya koyu arka plan ayarlamak için **Ctrl + Q** yazın ve "Renk Teması"nı arayın. Ayrıca **Araçlar** > **Seçenekleri** > **Ortamı**giderek bu bulabilirsiniz , ve Renk **Tema**seçerek .

![Renk temalarının ekran görüntüsü](media/tools-options-color-theme.png)

Örneğin, karanlık tema şunlardır:

![Koyu renk teonu ile Visual Studio ekran görüntüsü](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>Kod renklendirmeyi özelleştirme

Visual Studio 2019'da, önceden tanımlanmış üç *renk düzeni*arasından seçim yapabilirsiniz. Bunlar, kod öğelerinin düzenleyicide nasıl renklendirilebildiğini belirtir. Bir tema seçmek için **Araçlar** > **Seçenekleri** > **Metin Düzenleyicisi** > **C/C++** > **Görünümü'ne**gidin ve **Renk Düzeni'ni**seçin:

![Gelişmiş vurgulanmış C++ Renk Düzeni seçeneklerinin ekran görüntüsü](media/color-schemes.png)

**Visual Studio 2017**adı verilen renk düzeninde çoğu kod öğesi sadece siyahtır. **Geliştirilmiş** renk düzeninde işlevler, yerel değişkenler, makrolar ve diğer öğeler renklendirilir. Gelişmiş **(Globals vs. Üyeler)** şemasında, genel işlevler ve değişkenler sınıf üyeleriyle kontrast olacak şekilde renklenir. Varsayılan mod **Geliştirilmiştir**ve şuna benzer:

![Geliştirilmiş renk düzeninin ekran görüntüsü](media/color-scheme-enhanced.png)

Hangi tema veya renk düzeni etkin olursa olsun, yazı tipini ve renkleri tek tek kod öğeleri için özelleştirebilirsiniz. Bunu yapmak için **Araçlar** > **Seçenekleri** > **Çevre** > **Yazı Tipleri ve Renkleri** 'ne gidin (veya **Ctrl + Q** yazın ve "Yazı Tipleri"ni arayın). C++ seçeneklerini görene kadar görüntü öğeleri listesini aşağı kaydırın.

![C++ yazı tipi ve renk seçeneklerinin ekran görüntüsü](media/tools-options-cpp-colors.png)

Burada ayarladığınız renkler, renk düzenleri için tanımlanan değerleri geçersiz kılar. Renk düzeni için varsayılan renklere geri dönmek istiyorsanız, rengi **Varsayılan**olarak geri ayarlayın.

## <a name="customize-the-toolbars"></a>Araç çubuklarını özelleştirme

Araç çubukları, menüleri veya klavye kısayollarını kullanmak yerine komutları tek bir tıklamayla vermek için kullanışlı bir yol sağlar. Visual Studio standart bir araç çubuğu kümesi içerir. Standart C++ geliştirme için en kullanışlı araç çubukları büyük olasılıkla Standart, Metin Düzenleyicisi, Oluşturma, Hata Ayıklama, Kaynak Denetimi ve Dosyaları Karşılaştır'dır. Windows geliştirme için, İletişim Düzenleyicisi ve Görüntü Düzenleyicisi iletişim kutuları düzenlemek ve simgeleri düzenlemek için yararlıdır.

Hangi komutu temsil ettiğine görmek için araç çubuğundaki simgelerin üzerine tıklayın:

![Araç çubuğu simgelerinin ekran görüntüsü, komut bilgileri örneği havada mevcuttur](media/toolbar-mouse-hover.png)

Aşağı oku seçerek komutlar ekleyebilir veya kaldırabilir veya özel bir araç çubuğu oluşturabilirsiniz. Araç çubuğunu yeni bir konuma taşımak için, soldaki noktalı çubuğun yanında sürükleyin.

![Aşağı ok ve noktalı çubuğu vurgulanmış araç çubuğunun ekran görüntüsü](media/toolbar-move-edit.png).

Daha fazla bilgi için [bkz: Visual Studio'da menüleri ve araç çubuklarını özelleştirin.](/visualstudio/ide/how-to-customize-menus-and-toolbars-in-visual-studio)

## <a name="show-or-hide-line-numbers"></a>Satır numaralarını gösterme veya gizleme

Satır numaralarının düzenleyici pencerelerinin solunda gösterip göstermediğini belirtebilirsiniz. **Seçenekler'de**, **C/C++** altında **Genel'i**seçin. **Ayarlar** bölümünde, tercihinize bağlı olarak **Satır numaralarını**seçin veya temizleyin.

![Satır numaraları vurgulanmış genel seçeneklerin ekran görüntüsü](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>Klavye kısayolları oluşturma

Visual Studio'daki birçok komutta *klavye kısayolları,* Ctrl, Alt ve Shift tuşları ile tuş kombinasyonları vardır. Bu klavye kısayollarını değiştirebilir veya Visual Studio'da kendi klavyelerinizi oluşturabilirsiniz. **Araçlar** > **Seçenekleri** > **Ortam** > **Klavyesine** gidin (veya **Ctrl + Q** yazın ve "kısayollar" için arama yapın). Daha fazla bilgi için [Visual Studio'da klavye kısayollarını tanımla ve özelleştir'](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)e bakın.
