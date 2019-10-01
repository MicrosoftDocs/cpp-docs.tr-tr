---
title: Visual Studio C++ 'da kodlama tercihlerinizi ayarlama
ms.description: Customize C++ formatting, colors, layout, line numbers, menus and more in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: 90c9f39135b90a2c5015861a78dd8760b9a8aeed
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686889"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Visual Studio C++ 'da kodlama tercihlerinizi ayarlama

Visual Studio 'Yu kişiselleştirerek C++ kodlama deneyiminizi daha rahat, üretken ve güvenilir hale getirebilirsiniz. Menüleri ve araç çubuklarını özelleştirebilir, pencere yerleşimini düzenleyebilir, renk temalarını ayarlayabilir, ClangFormat 'ın C++ çeşitli özellikleri de dahil olmak üzere biçimlendirme kurallarını belirtebilir ve özel klavye kısayolları oluşturabilirsiniz. Tercihlerinizi birden çok makine genelinde eşitleyebilir, birden çok grup kümesi oluşturup saklayabilir ve bunları ekip mates ile paylaşabilirsiniz. Uzantıları, ek özel davranış sağlayan Visual Studio Market yükleyebilirsiniz. Bu seçeneklerin çoğu [, Visual STUDIO IDE 'Yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide)bölümünde belgelenmiştir.

## <a name="arrange-window-layout"></a>Pencere yerleşimini Düzenle

Visual Studio penceresinde, boşluk ana menüye, araç çubuğuna, kod düzenleyicisine (veya belge penceresine) ve araç penceresine (**Çözüm Gezgini**, **hata listesi**vb.) ayrılır. Bazı pencereler aynı konumda birbirleriyle çakışacak. Örneğin, **Çözüm Gezgini**, **sınıf görünümü**, **kaynak görünümü**ve **Kaynak Denetim Gezgini** aynı varsayılan konumu paylaşır. Çerçevenin altındaki sekmelere tıklayarak bunlar arasında geçiş yapabilirsiniz. Bu pencerelerin iki veya daha fazlasını aynı anda görünür yapmak için, bunlardan birini başlık çubuğuna göre yeni bir konuma sürüklemeniz yeterlidir. Visual Studio ana pencere kenarlıklarınına göre yerleştirebilirsiniz veya onu de yerleştirebilirsiniz. Aşağıdaki çizimde, ' ın varsayılan konumundan, kod düzenleyicisinin sol tarafındaki yeni bir sabitlenmiş konuma sürüklenme sürecinde **Takım Gezgini** penceresi gösterilmektedir. Mavi gölgeli alan, fare düğmesi serbest bırakıldığında pencerenin nereye yerleştirileceğini gösterir.

![Pencere yerleşimini değiştirme](media/window-layout-move-team-explorer.png)

Belge penceresinde, her açık dosya sekmeli bir çerçevede yer alır. Bu sekmeleri tıpkı araç pencereleri gibi float veya kilitle. Daha fazla bilgi için bkz. [Visual Studio 'da pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Tüm araç pencerelerini gizlemek ve kod Düzenleyicisi penceresini en üst düzeye çıkarmak için **Alt** + **SHIFT**@no__t **-3 '** e basarak *tam ekran modunu*değiştirin.

## <a name="set-c-coding-styles-and-formatting"></a>Kodlama C++ stillerini ve biçimlendirmeyi ayarlama

**Araçlar** > **Seçenekler** > **metin Düzenleyicisi** > **C/C++**  > **biçimlendirme** (veya tür **CTRL + Q** ve "biçimlendirme" araması yapın). Alternatif olarak, [Clangformat](https://clang.llvm.org/docs/ClangFormat.html) stillerinden birini (veya kendi özel clangformat stilinizi) belirtebilirsiniz:

![ClangFormat seçenekleri](media/clang-format-ide.png)

Biçimlendirme seçenekleri hakkında daha fazla bilgi için bkz. [Seçenekler, metin düzenleyici, CC++/, biçimlendirme](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting).

## <a name="set-the-color-theme"></a>Renk temasını ayarlama

Açık veya koyu bir arka plan ayarlamak için **CTRL + Q** yazın ve "renkli tema" araması yapın. Ayrıca **araçlar**@no__t-**3 @no__t ve** **renk teması** **' nı** seçerek de buradan ulaşabilirsiniz:

![Renk temaları](media/tools-options-color-theme.png)

Aşağıdaki görüntüde koyu Tema gösterilmektedir:

![Koyu tema](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>Kod renklendirmeyi özelleştirme

Visual Studio 2019 ' de, kod öğelerinin düzenleyicide nasıl renklendirilmeyeceğini belirten üç önceden tanımlı *renk düzeni* arasından seçim yapabilirsiniz. Bir tema seçmek için **Araçlar** > **Seçenekler** > **metin Düzenleyicisi** > **C/C++**  > **görünümü** ' ne gidin ve **renk şeması**' nı seçin:

![C++Renk şemaları](media/color-schemes.png)

**Visual Studio 2017** renk şemasında, çoğu kod öğesi yalnızca siyah olur. **Gelişmiş** renk şemasında, işlevler, yerel değişkenler, makrolar ve diğer öğeler renklendirililmiştir. **Gelişmiş (Globals vs. Members)** düzeninde, genel işlevler ve değişkenler sınıf üyeleri ile karşıtlığa göre renklendirilir. Varsayılan mod **geliştirilmiştir** ve şuna benzer:

![Gelişmiş renk düzeni](media/color-scheme-enhanced.png)

Hangi tema veya renk şemasının etkin olduğuna bakılmaksızın, tek tek kod öğelerinin yazı tipi ve renklerini,  > **seçenekleri** > **ortam** > **yazı tipi ve renk** (veya tür **) giderek özelleştirebilirsiniz. CTRL + Q** ve "yazı tipleri" için arama yapın. C++ Seçenekleri görene kadar görüntüleme öğelerinin listesini aşağı kaydırın:

![C++yazı tipi ve renk seçenekleri](media/tools-options-cpp-colors.png)

Burada ayarladığınız renkler, renk şemaları için tanımlanan değerleri geçersiz kılar. Değişiklik yaptıysanız ancak renk düzeni için varsayılan renkleri kullanmak istiyorsanız, **varsayılan** olarak bir renk ayarlamanız gerekir.

## <a name="customize-the-toolbars"></a>Araç çubuklarını özelleştirme

Araç çubukları, menüleri veya klavye kısayollarını kullanmak yerine tek bir fare tıklaması ile komut vermek için kullanışlı bir yol sağlar. Visual Studio, standart bir araç çubuğu kümesi içerir. Standart C++ geliştirme için en yararlı araç çubukları muhtemelen standart, metin düzenleyici, derleme, hata ayıklama, kaynak denetimi ve muhtemelen dosya karşılaştırmaktır. Windows geliştirme için Iletişim kutusu Düzenleyicisi ve görüntü Düzenleyicisi, Iletişim kutularını ve düzenleme simgelerini düzenlemek için yararlıdır.

Hangi komutun temsil ettiğini görmek için araç çubuğundaki simgelerin üzerine gelin:

![Araç çubuğu hızlı bilgi](media/toolbar-mouse-hover.png)

Aşağı oka tıklayarak komut ekleyebilir veya kaldırabilir veya özel bir araç çubuğu oluşturabilirsiniz. Araç çubuğunu yeni bir konuma taşımak için sol taraftaki noktalı çubuğa göre sürükleyin:

![Araç çubuğunu özelleştirme veya taşıma](media/toolbar-move-edit.png).

Daha fazla bilgi için bkz. [nasıl yapılır: Visual Studio 'da menüleri ve araç çubuklarını özelleştirme](/visualstudio/ide/how-to-customize-menus-and-toolbars-in-visual-studio).

## <a name="show-or-hide-line-numbers"></a>Satır numaralarını göster veya gizle

Düzenleyici pencerelerinin sol tarafında satır numaralarının gösterilip gösterilmeyeceğini belirtmek için, **Satır numaralarına**gidin ve bunları kaldırın veya kontrol edin:

![Satır numaraları](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>Klavye kısayolları oluşturma

Visual Studio 'daki tüm komutlar, CTRL, alt ve Shift tuşlarıyla çeşitli anahtar bileşimleri kullanılarak klavye kısayollarıyla yapılabilir. **Araçlar** > **seçeneklerine**@no__t-**3 @no__t-** 5**klavye** (veya **CTRL + Q** yazıp "kısayollar" araması) giderek kendi kısayollarınızı oluşturabilirsiniz. Daha fazla bilgi için bkz. [Visual Studio 'da klavye kısayollarını tanımlamak ve özelleştirmek](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).
