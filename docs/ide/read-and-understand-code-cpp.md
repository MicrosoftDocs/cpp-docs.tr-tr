---
title: Visual Studio'da C++ kodunu okuyun ve anlayın
description: Visual Studio'daki C++ kod düzenleyicisini kullanarak kodunuzu biçimlendirin ve anlayın.
ms.date: 05/28/2019
ms.openlocfilehash: 9ed0a20fb73e4cc976392bc5e5f698f9658a0b48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377298"
---
# <a name="read-and-understand-c-code-in-visual-studio"></a>Visual Studio'da C++ kodunu okuyun ve anlayın

C++ kod düzenleyicisi ve Visual Studio IDE birçok kodlama yardımcıları sağlar. Bazıları C++'a özgüdür ve bazıları tüm Visual Studio dilleri için temelde aynıdır. Paylaşılan özellikler hakkında daha fazla bilgi için [Kod ve Metin Düzenleyicisi'nde Kod Yazma'ya](/visualstudio/ide/writing-code-in-the-code-and-text-editor)bakın.  

## <a name="colorization"></a>Renklendirme

Visual Studio sözdizimi öğelerini dil anahtar kelimeleri, tür adları, değişken adları, işlev parametreleri, dize literalleri ve benzeri sembollerin türlerini ayırt etmek için renklendirin.

![Kod renklendirme](../ide/media/code-outline-colorization.png "C++ renklendirme")

Kullanılmayan kod (#if 0 altında kod gibi) daha fazla renk soluk.

![Etkin olmayan kod](../ide/media/inactive-code-cpp.png "C++ etkin olmayan kod")

**Hızlı Başlatma'da**"Yazı Tipleri" yazıp sonra **Yazı Tipleri ve Renkler'i**seçerek renkleri özelleştirebilirsiniz. Yazı **Tipleri ve Renkler** iletişim kutusunda C/C++ seçeneklerine gidin ve ardından özel bir yazı tipi ve/veya renk seçin.

## <a name="outlining"></a>Anahat Oluşturma

Kaynak kod dosyasındaki herhangi bir yere sağ tıklayın ve yalnızca ilgilendiğiniz koda göz atmanızı kolaylaştırmak için kod bloklarını ve/veya özel bölgeleri daraltmak veya genişletmek için **Anahat'ı** seçin. Daha fazla bilgi için [Anahat'a](/visualstudio/ide/outlining)bakın.

![C&#43;&#43; Anahat](../ide/media/vs2015_cpp_outlining.png "Anahat Oluşturma")

İmlecinizi kıvırcık bir ayraç önüne yerleştirdiğinizde, '{' veya '}', düzenleyici eşleşen muadili vurgular.

Diğer anahat seçenekleri ana menüde**Anahat** **Düzenle** > altında yer alır.

## <a name="line-numbers"></a>Satır numaraları

**Araçlar** > **Seçenekleri** > **Metin Editörü** > **Tüm Diller** > **Genel'e** giderek veya Hızlı **Başlatma (Ctrl + Q)** ile "line num" arayarak projenize satır numaraları ekleyebilirsiniz. Satır numaraları tüm diller için veya C++ dahil olmak üzere yalnızca belirli diller için ayarlanabilir.

## <a name="scroll-and-zoom"></a>Kaydırma ve yakınlaştırma

**Ctrl** tuşuna basarak ve fare tekerleğiile kaydırarak düzenleyiciyi yakınlaştırabilir veya uzaklaştırabilirsiniz. Ayrıca sol alt köşedeki yakınlaştırma ayarını kullanarak yakınlaştırabilirsiniz.

![C&#43;&#43; Yakınlaştırma Kontrolü](../ide/media/zoom-control.png "Yakınlaştırma denetimi")

Scrollbar **Harita Modu,** geçerli konumunuzu terk etmeden bir kod dosyasında hızlı bir şekilde gezinmenizi ve göz atmanızı sağlar. Doğrudan o konuma gitmek için kod haritasında herhangi bir yere tıklayabilirsiniz.

![C&#43;&#43;Kod Haritası](../ide/media/vs2015-cpp-code-map.png "Kod Haritası")

**Harita Modunu**açmak için, ana araç çubuğundaki **Hızlı Başlat** arama kutusuna "harita" yazın ve **harita modunu kullan'ı**seçin. Daha fazla bilgi için [bkz: Kaydırma çubuğunu özelleştirerek kodunuzu izleyin.](/visualstudio/ide/how-to-track-your-code-by-customizing-the-scrollbar)

**Harita Modu** kapalıyken, kaydırma çubuğu dosyada yaptığınız değişiklikleri yine de vurgular. Yeşil kaydedilen değişiklikleri gösterir ve sarı kaydedilmemiş değişiklikleri gösterir.

## <a name="quick-info-and-parameter-info"></a>Hızlı Bilgi ve Parametre Bilgileri

Bildirim de dahil olmak üzere bu konuda bilgi almak için herhangi bir değişkenin, işlevin veya diğer simgenin ve hemen öncesinde bulunan yorumların üzerine geçin.

::: moniker range="vs-2019"

![C&#43;&#43;Hızlı Bilgi](../ide/media/quick-info-vs2019.png "Hızlı Bilgi")

**Hızlı Bilgi** araç ipucunun bir **Arama Çevrimiçi** bağlantısı vardır. Arama sağlayıcısını belirtmek için **Araçlar** > **Seçenekleri** > **Metin Düzenleyicisi** > **C++** > **Görünümü'ne** gidin.

Kodunuzda bir hata varsa, üzerinde gezinebilirsiniz ve **Hızlı Bilgi** hata iletisini görüntüler. Hata Listesi penceresinde hata iletisini de bulabilirsiniz.

![Hata hakkında hızlı bilgi](../ide/media/quickinfo-on-error.png "Hata hakkında hızlı bilgi")

::: moniker-end

::: moniker range="<=vs-2017"

![C&#43;&#43;Hızlı Bilgi](../ide/media/quick-info.png "Hızlı Bilgi")

Kodunuzda bir hata varsa, üzerinde gezinebilirsiniz ve **Hızlı Bilgi** hata iletisini görüntüler. **Hata Listesi** penceresinde hata iletisini de bulabilirsiniz.

![Hata hakkında hızlı bilgi](../ide/media/quickinfo-on-error.png "Hata hakkında hızlı bilgi")

::: moniker-end

Bir işlevi çağırdığınızda, **Parametre Bilgisi** parametrelerin türlerini ve beklendikleri sırayı gösterir.

![C&#43;&#43;'da Parametre Bilgisi](../ide/media/parameter-info.png "Parametre Bilgisi")

## <a name="peek-definition"></a>Tanıma Göz At

Bir değişken veya işlev bildiriminin üzerine tıklayın, ardından geçerli konumunuzdan uzaklaşmadan tanımının satır içi görünümünü görmek için **Peek Tanımı'nı** seçin. Daha fazla bilgi için [Bkz. Peek Tanımı (Alt+F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12).

![C&#43;&#43; Peek Tanımı](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

## <a name="f1-help"></a>F1 Yardımı

İmleci herhangi bir türe, anahtar kelimeye veya fonksiyondan hemen sonra yerleştirin ve docs.microsoft.com ilgili başvuru konusuna doğrudan gitmek için **F1** tuşuna basın. **F1,** hata listesindeki öğeler de ve birçok iletişim kutusunda çalışır.

## <a name="class-view"></a>Sınıf Görünümü

**Sınıf Görünümü,** proje başına düzenlenen tüm kod sembollerinden ve bunların kapsamı ve üst/alt hiyerarşilerinden oluşan aranabilir bir ağaç kümesi görüntüler. **Sınıf Görünümü'nün** Sınıf **Görünümü Ayarlarından** görüntülediğinizi yapılandırabilirsiniz (pencerenin üst kısmındaki vites kutusu simgesini tıklatın).

![C&#43;&#43;Sınıf Görünümü](../ide/media/class-view.png "Sınıf Görünümü")

## <a name="generate-graph-of-include-files"></a>Include dosyalarının grafiğini oluşturma

Projenizdeki bir kod dosyasına sağ tıklayın ve diğer dosyalar tarafından hangi dosyaların dahil edildiğine ilişkin bir grafik görmek için **dosya oluşturma grafiğini** seçin.

![C&#43;&#43; dosya&#43;&#43; grafiği](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

## <a name="view-call-hierarchy"></a>Çağrı Hiyerarşisi'ni görüntüle

Herhangi bir işlev çağrısına sağ tıklayın ve aradığı tüm işlevlerin ve onu çağıran tüm işlevlerin özyinelemeli listesini görüntüleyin. Listedeki her işlev aynı şekilde genişletilebilir. Daha fazla bilgi için [Çağrı Hiyerarşisi'ne](/visualstudio/ide/reference/call-hierarchy)bakın.

![C&#43;&#43; Çağrı Hiyerarşisi](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

## <a name="see-also"></a>Ayrıca Bkz.

[Düzenleme ve yeniden düzenleme kodu (C++)](writing-and-refactoring-code-cpp.md)</br>
[Visual Studio'da C++ kod tabanınızda gezinme](navigate-code-cpp.md)</br>
[C++ için Live Share ile işbirliği yapın](live-share-cpp.md)
