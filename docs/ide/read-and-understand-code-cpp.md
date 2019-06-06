---
title: Okumanız ve anlamanız C++ Visual Studio'daki kod
description: Kullanım C++ biçimlendirmek ve kodunuzu anlamak için Visual Studio'daki Kod Düzenleyicisi.
ms.date: 05/28/2019
ms.openlocfilehash: c5e4d7f3e53ef37649e3635d11cf99b10cb8a7ee
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66743383"
---
# <a name="read-and-understand-c-code-in-visual-studio"></a>Okumanız ve anlamanız C++ Visual Studio'daki kod

C++ Kod Düzenleyicisi ve Visual Studio IDE birçok kodlama yardımları sağlayın. Bazı C++ için özeldir ve bazı temel olarak tüm Visual Studio dilleri için aynıdır. Paylaşılan özellikler hakkında daha fazla bilgi için bkz. [kodu ve metin düzenleyicisi kod yazma](/visualstudio/ide/writing-code-in-the-code-and-text-editor).  

## <a name="colorization"></a>Renklendirme

Visual Studio dil anahtar sözcükleri, tür adları, değişken adları, işlev parametrelerini, dize sabit değerleri ve benzeri gibi simgeleri türlerini birbirinden ayırmak için söz dizimi öğeleri renklendirmesi.

![Renklendirme kodu](../ide/media/code-outline-colorization.png " C++ renklendirme")

 Kullanılmayan kod (örneğin, bir #if 0 altındaki kodu), rengi daha soluk.

 ![Pasif kod](../ide/media/inactive-code-cpp.png " C++ pasif kod")

Renkleri "Yazı tiplerini" yazarak, özelleştirebileceğiniz **hızlı başlatma**ve ardından **yazı tipleri ve renkler**. İçinde **yazı tipleri ve renkler** C iletişim kaydırın /C++ seçenekleri ve bir özel yazı tipi ve/veya renk seçin.

## <a name="outlining"></a>Anahat Oluşturma

Bir kaynak kodu dosyasında herhangi bir yere sağ tıklayın ve seçin **anahat** kod bloklarını ve/veya yalnızca ilgilendiğiniz koda göz atmak daha kolay hale getirmek için özel bölgeleri'ni genişletin veya daraltın. Daha fazla bilgi için [anahat](/visualstudio/ide/outlining).

![C&#43; &#43; anahat oluşturma](../ide/media/vs2015_cpp_outlining.png "anahat oluşturma")

İmlecinizi bir küme ayracı önüne yerleştirdiğinizde ' {' veya '}', düzenleyici eşleşen çözümlemesiyle vurgular.

Diğer anahat oluşturma seçenekleri altında bulunan **Düzenle** > **anahat** da ana menüde.

## <a name="line-numbers"></a>Satır numaraları

Satır numaraları giderek projenize ekleyebilirsiniz **Araçları** > **seçenekleri** > **metin düzenleyici** > **tüm Diller** > **genel** ya da "satır numaraları için" ile arayarak **Hızlı Başlat (Ctrl + Q)** . Satır numaraları ayarlanabilir tüm diller için veya yalnızca belirli diller için de dahil olmak üzere C++.

## <a name="scroll-and-zoom"></a>Kaydırma ve yakınlaştırma

Tuşlarına basarak veya dışarı düzenleyicisinde yakınlaştırabilirsiniz **Ctrl** anahtar ve fare tekerleğini kaydırma. Ayrıca, sol alt köşedeki yakınlaştırma ayarını kullanarak yakınlaştırma yapabilirsiniz.

![C&#43; &#43; yakınlaştırma denetimi](../ide/media/zoom-control.png "yakınlaştırma denetimi")

Kaydırma çubuğu **eşleme modu** hızla kaydırma ve bir kod dosyası geçerli konumunuzu çıkmadan Gözat olanak tanır. Herhangi bir yere bu konuma gitmek için kod Haritası tıklayabilirsiniz.

![Kod eşlemesi C'de&#43;&#43;](../ide/media/vs2015-cpp-code-map.png "kod eşlemesi")

Açmak için **eşleme modu**, türü "Bağlan" **hızlı başlatma** seçin ve arama kutusuna ana araç çubuğunda **kaydırma eşleme modunu kullan**. Daha fazla bilgi için [nasıl yapılır: Kaydırma çubuğunu özelleştirerek kodunuzu izleme](/visualstudio/ide/how-to-track-your-code-by-customizing-the-scrollbar).

Zaman **eşleme modu** kapalıysa, kaydırma çubuğu, dosyada yaptığınız değişiklikleri yine de vurgular. Yeşil kaydedilen değişiklikleri gösterir ve sarı kaydedilmemiş değişiklikleri gösterir.

## <a name="quick-info-and-parameter-info"></a>Hızlı bilgi ve parametre bilgisi

Herhangi bir değişken, işlev veya, ilgili bildirim ve yalnızca önceki bulunan açıklamalar da dahil olmak üzere bilgi almak için başka bir simge üzerine getirin.

::: moniker range="vs-2019"

![Hızlı bilgi C'de&#43;&#43;](../ide/media/quick-info-vs2019.png "hızlı bilgi")

**Hızlı bilgi** araç ipucu olan bir **çevrimiçi Ara** bağlantı. Git **Araçları** > **seçenekleri** > **metin düzenleyici**  >  **C++**  >  **Görünümü** arama sağlayıcısı belirtmek için. 

Kodunuzda bir hata varsa, üzerine gelerek ve **hızlı bilgi** hata iletisini görüntüler. Hata Listesi penceresindeki hata iletisi da bulabilirsiniz.

![Hızlı bilgi hata](../ide/media/quickinfo-on-error.png "hata hızlı bilgi")

::: moniker-end

::: moniker range="<=vs-2017"

![Hızlı bilgi C'de&#43;&#43;](../ide/media/quick-info.png "hızlı bilgi")

Kodunuzda bir hata varsa, üzerine gelerek ve **hızlı bilgi** hata iletisini görüntüler. Hata iletisinde de bulabilirsiniz **hata listesi** penceresi.

![Hızlı bilgi hata](../ide/media/quickinfo-on-error.png "hata hızlı bilgi")

::: moniker-end

Bir işlev çağırdığınızda **parametre bilgisi** parametreleri ve bunların beklenen sırası türleri gösterilmektedir.

![Parametre bilgisi C'de&#43;&#43;](../ide/media/parameter-info.png "parametre bilgisi")

## <a name="peek-definition"></a>Tanıma göz at

Bir değişken veya işlev bildiriminin sağ tıklayın, ardından gelin seçin **Özet tanım** geçerli konumunuzu uzağa gitmeden tanımına bir satır içi görünümünü görmek için. Daha fazla bilgi için [Özet tanım (Alt + F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12).

![C&#43; &#43; Özet tanımı](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

##  <a name="f1-help"></a>F1 Yardımı

Ya da herhangi bir tür, anahtar sözcüğü veya işlevi ve basın hemen sonra imlecin yerleştirileceği **F1** docs.microsoft.com'da doğrudan ilgili başvuru konusuna gidin. **F1** öğeler için hata listesinden ve birçok iletişim kutularında üzerinde de çalışır.

## <a name="class-view"></a>Sınıf Görünümü

**Sınıf Görünümü** ağaçları tüm kod sembolleri proje başına olarak düzenlenmiş kendi kapsamı ve üst/alt öğe hiyerarşileri ve aranabilir bir kümesini görüntüler. Ne yapılandırabileceğiniz **sınıf görünümü** gelen görüntüler **sınıf görünümü ayarlar** (pencerenin üst kısmındaki dişli kutusu simgesine tıklayın).

![Sınıf Görünümü'nde C&#43;&#43;](../ide/media/class-view.png "sınıf görünümü")

## <a name="generate-graph-of-include-files"></a>Ekleme dosyalarının grafını oluştur

Bir kod dosyası projenize sağ tıklayın ve seçin **ekleme dosyalarının grafını Oluştur** hangi dosyaları diğer dosyalar tarafından eklenir bir grafik görmek için.

![C&#43; &#43; ekleme dosyalarının grafı](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

## <a name="view-call-hierarchy"></a>Çağrı hiyerarşisini görüntüle

Herhangi bir işlev çağrısına sağ tıklayın ve çağrı yaptığı tüm işlevlerin ve çağırdığı tüm işlevlerin özyinelemeli listesini görüntüleyin. Listedeki her işlev aynı şekilde genişletilebilir. Daha fazla bilgi için [çağrı hiyerarşisi](/visualstudio/ide/reference/call-hierarchy).

![C&#43; &#43; çağrı hiyerarşisi](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

## <a name="see-also"></a>Ayrıca Bkz.

[Düzenleme ve yeniden düzenleme, kod (C++)](writing-and-refactoring-code-cpp.md)</br>
[Git, C++ Visual Studio'da temel kod](navigate-code-cpp.md)</br>
[Canlı paylaşım için işbirliği yapınC++](live-share-cpp.md)
