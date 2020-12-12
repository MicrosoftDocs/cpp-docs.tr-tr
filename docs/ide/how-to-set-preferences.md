---
description: "Daha fazla bilgi edinin: Visual Studio 'da C++ kodlama tercihlerinizi ayarlama"
title: Visual Studio 'da C++ kodlama tercihlerinizi ayarlama
ms.description: Customize C++ formatting, colors, layout, line numbers, and menus in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: 9a82c0771c097bb1246737f748077bbc303ac9f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240916"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Visual Studio 'da C++ kodlama tercihlerinizi ayarlama

Visual Studio 'Yu kişiselleştirerek C++ kodlama deneyiminizi daha rahat, üretken ve güvenilir hale getirebilirsiniz. Şunları yapabilirsiniz:

- Menüleri ve araç çubuklarını özelleştirin.
- Pencere yerleşimini düzenleyin.
- Renk temalarını ayarlayın.
- Birkaç ClangFormat stili dahil C++ biçimlendirme kurallarını belirtin.
- Özel klavye kısayolları oluşturun.

Tercihlerinizi birden çok makine genelinde eşitleyebilir, birden çok grup kümesi oluşturup saklayabilir ve bunları ekip mates ile paylaşabilirsiniz. Visual Studio Market uzantıları, özelleştirme davranışını özelleştirmek için ek seçenekler sunarak yükleyebilirsiniz. Daha fazla bilgi için bkz. [Visual STUDIO IDE 'Yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="arrange-window-layout"></a>Pencere yerleşimini Düzenle

Visual Studio penceresinde, boşluk ana menüye, araç çubuğuna, kod düzenleyicisine (veya belge penceresine) ve araç penceresine (örneğin, Çözüm Gezgini ve Hata Listesi) ayrılır. Bazı pencereler aynı konumda birbirleriyle çakışacak. Örneğin, Çözüm Gezgini, Sınıf Görünümü, Kaynak Görünümü ve Kaynak Denetim Gezgini aynı varsayılan konumu paylaşır. Çerçevenin altındaki sekmeleri seçerek bunlar arasında geçiş yapabilirsiniz. Bu pencerelerin iki veya daha fazlasını aynı anda görünür yapmak için, bunlardan birini başlık çubuğuna göre yeni bir konuma sürüklemeniz yeterlidir. Visual Studio ana pencere kenarlıklarınına göre yerleştirebilirsiniz veya onu de yerleştirebilirsiniz.

Aşağıdaki ekran görüntüsünde, **Takım Gezgini** penceresinin varsayılan konumundan, kod düzenleyicisinin sol tarafındaki yeni, sabitlenmiş bir konuma sürüklenmesi gösterilmektedir. Mavi gölgeli alan, fare düğmesi serbest bırakıldığında pencerenin nereye yerleştirileceğini gösterir.

![Düzen değişikliği vurgulanmış şekilde Visual Studio Takım Gezgini penceresinin ekran görüntüsü](media/window-layout-move-team-explorer.png)

Belge penceresinde, her açık dosya sekmeli bir çerçevede yer alır. Araç pencereleri gibi bu sekmeleri de float veya kilitle. Daha fazla bilgi için bkz. [Visual Studio 'da pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Tüm araç pencerelerini gizlemek ve kod Düzenleyicisi penceresini en üst düzeye çıkarmak için,   +    +  *tam ekran modunu* değiştirmek üzere alt SHIFT **ENTER** tuşuna basın.

## <a name="set-c-coding-styles-and-formatting"></a>C++ kodlama stillerini ve biçimlendirmesini ayarlama

Girinti ve ayraç konumları gibi birçok bağımsız kod biçimlendirme seçeneği belirtebilirsiniz. Bunu yapmak için, **Araçlar**  >  **Seçenekler**  >  **metin Düzenleyicisi**  >  **C/C++**  >  **biçimlendirme** (veya **CTRL + Q** yazın ve "biçimlendirme" için arama yapın) bölümüne gidin. Alternatif olarak, [Clangformat](https://clang.llvm.org/docs/ClangFormat.html) stillerinden birini (veya kendi özel clangformat stilinizi) belirtebilirsiniz.

![ClangFormat seçeneklerinin ekran görüntüsü](media/clang-format-ide.png)

Biçimlendirme seçenekleri hakkında daha fazla bilgi için bkz. [Seçenekler, metin düzenleyici, C/C++, biçimlendirme](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting).

## <a name="set-the-color-theme"></a>Renk temasını ayarlama

Açık veya koyu bir arka plan ayarlamak için **CTRL + Q** yazın ve "renkli tema" araması yapın. Bunları ayrıca **Araçlar**  >  **Seçenekler**  >  **ortamına** gidip **renk teması**' nı seçerek de bulabilirsiniz.

![Renk temalarının ekran görüntüsü](media/tools-options-color-theme.png)

Örneğin, şu şekilde Koyu tema verilmiştir:

![Koyu renkli tema içeren Visual Studio ekran görüntüsü](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>Kod renklendirmeyi özelleştirme

Visual Studio 2019 ' de, önceden tanımlanmış üç *renk düzeni* arasından seçim yapabilirsiniz. Bunlar, kod öğelerinin düzenleyicide renk oluşturma şeklini belirtir. Bir tema seçmek için **Araçlar**  >  **Seçenekler**  >  **metin Düzenleyicisi**  >  **C/C++**  >  **görünümü**' ne gidin ve **renk şeması**' nı seçin:

![Genişletilmiş vurgulanmış C++ renk şeması seçeneklerinin ekran görüntüsü](media/color-schemes.png)

**Visual Studio 2017** adlı renk şemasında çoğu kod öğesi yalnızca siyah olur. **Gelişmiş** renk şemasında, işlevler, yerel değişkenler, makrolar ve diğer öğeler renklendirililmiştir. **Gelişmiş (Globals vs. Members)** düzeninde, genel işlevler ve değişkenler sınıf üyeleri ile karşıtlığa göre renklendirilir. Varsayılan mod **geliştirilmiştir** ve şuna benzer:

![Gelişmiş renk düzeninin ekran görüntüsü](media/color-scheme-enhanced.png)

Hangi tema veya renk şemasının etkin olduğuna bakılmaksızın, bağımsız kod öğeleri için yazı tipi ve renkler özelleştirebilirsiniz. Bunu yapmak için, **Araçlar**  >  **Seçenekler**  >  **ortam**  >  **yazı tipleri ve renkler** ' e gidin (veya **CTRL + Q** yazın ve "yazı tipleri" için arama yapın). C++ seçeneklerini görene kadar görüntüleme öğeleri listesini aşağı kaydırın.

![C++ yazı tipi ve renk seçeneklerinin ekran görüntüsü](media/tools-options-cpp-colors.png)

Burada ayarladığınız renkler, renk şemaları için tanımlanan değerleri geçersiz kılar. Renk düzeninin varsayılan renklerine geri dönmek isterseniz, bir rengi **varsayılana** geri doğru ayarlayın.

## <a name="customize-the-toolbars"></a>Araç çubuklarını özelleştirme

Araç çubukları, menüleri veya klavye kısayollarını kullanmak yerine, tek tıklamayla komutları vermek için kullanışlı bir yol sağlar. Visual Studio, standart bir araç çubuğu kümesi içerir. Standart C++ geliştirmesi için en yararlı araç çubukları muhtemelen standart, metin düzenleyici, derleme, hata ayıklama, kaynak denetimi ve dosya karşılaştırmaktır. Windows geliştirme için Iletişim kutusu Düzenleyicisi ve görüntü Düzenleyicisi, iletişim kutularını ve düzenleme simgelerini düzenlemek için yararlıdır.

Hangi komutun temsil ettiğini görmek için araç çubuğundaki simgelerin üzerine gelin:

![Araç çubuğu simgelerinin, üzerine gelindiğinde kullanılabilen komut bilgileri örneği ile ekran görüntüsü](media/toolbar-mouse-hover.png)

Aşağı oku seçerek komut ekleyebilir veya kaldırabilir veya özel bir araç çubuğu oluşturabilirsiniz. Araç çubuğunu yeni bir konuma taşımak için sol taraftaki noktalı çubuğa göre sürükleyin.

![Aşağı ok ve noktalı çubuğun vurgulandığı araç çubuğunun ekran görüntüsü](media/toolbar-move-edit.png).

Daha fazla bilgi için bkz. [nasıl yapılır: Visual Studio 'da menüleri ve araç çubuklarını özelleştirme](/visualstudio/ide/how-to-customize-menus-and-toolbars-in-visual-studio).

## <a name="show-or-hide-line-numbers"></a>Satır numaralarını göster veya gizle

Çizgi numaralarının düzenleyici pencerelerinin solunda gösterilip gösterilmeyeceğini belirtebilirsiniz. **Seçenekler**' de, **C/C++** altında **genel**' i seçin. **Ayarlar** bölümünde, tercihlerinize bağlı olarak **satır numaralarını** seçin veya temizleyin.

![Satır numaraları vurgulanmış şekilde genel seçeneklerin ekran görüntüsü](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>Klavye kısayolları oluşturma

Visual Studio 'daki birçok komut *klavye kısayollarına*, CTRL, alt ve SHIFT tuşlarına sahip tuş birleşimlerine sahiptir. Bu klavye kısayollarını değiştirebilir veya Visual Studio 'da kendi yeni bir tane oluşturabilirsiniz. **Araçlar**  >  **Seçenekler**  >  **ortam**  >  **klavyesi** ' ne gidin (veya **CTRL + Q** yazın ve "kısayollar" için arama yapın). Daha fazla bilgi için bkz. [Visual Studio 'da klavye kısayollarını tanımlamak ve özelleştirmek](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).
