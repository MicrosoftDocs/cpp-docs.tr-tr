---
title: Visual Studio 'da C++ kodunu okuma ve anlama
description: Kodunuzu biçimlendirmek ve anlamak için Visual Studio 'da C++ kod düzenleyicisini kullanın.
ms.date: 05/28/2019
ms.openlocfilehash: cd152ffbbd106c6a31a21da35d08b53555047209
ms.sourcegitcommit: 6284bca6549e7b4f199d4560c30df6c1278bd4a0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96188906"
---
# <a name="read-and-understand-c-code-in-visual-studio"></a>Visual Studio 'da C++ kodunu okuma ve anlama

C++ kod Düzenleyicisi ve Visual Studio IDE birçok kodlama yardımı sağlar. Bazıları C++ ' a özeldir ve bazıları aslında tüm Visual Studio dilleri için aynıdır. Paylaşılan Özellikler hakkında daha fazla bilgi için bkz. kod [ve metin düzenleyicisinde kod yazma](/visualstudio/ide/writing-code-in-the-code-and-text-editor).  

## <a name="colorization"></a>Renklendirme

Visual Studio, dil anahtar kelimeleri, tür adları, değişken adları, işlev parametreleri, dize sabit değerleri vb. gibi sembol türlerini ayırt etmek için sözdizimi öğelerini renklendirir.

![Kod renklendirme](../ide/media/code-outline-colorization.png "C++ renklendirme")

Kullanılmayan kod (bir #if 0 ' ın altında kod gibi) renkli olarak daha fafdır.

![Etkin olmayan kod](../ide/media/inactive-code-cpp.png "C++ etkin olmayan kodu")

**Hızlı Başlat**' da "yazı tipleri" yazarak ve ardından **yazı tipleri ve renkler**' i seçerek renkleri özelleştirebilirsiniz. **Yazı tipleri ve renkler** Iletişim kutusunda C/C++ seçeneklerine gidin ve özel bir yazı tipi ve/veya renk seçin.

## <a name="outlining"></a>Anahat Oluşturma

Kaynak kodu dosyasında herhangi bir yere sağ tıklayın ve kod bloklarını ve/veya özel bölgeleri daraltmak veya genişletmek için **anahat oluşturma** 'yı, yalnızca ilgilendiğiniz koda Gözatmayı kolaylaştırmak için seçin. Daha fazla bilgi için bkz. [anahat oluşturma](/visualstudio/ide/outlining).

![C&#43;&#43; anahat oluşturma](../ide/media/vs2015_cpp_outlining.png "Anahat Oluşturma")

İmlecinizi, ' {' veya '} ' küme ayracı önüne yerleştirdiğinizde, düzenleyici eşleşen karşılığı vurgular.

Diğer anahat oluşturma seçenekleri **Edit**  >  Ana menüdeki **anahat** düzenleme altında bulunur.

## <a name="line-numbers"></a>Satır numaraları

**Araçlar**  >  **Seçenekler**  >  **metin Düzenleyicisi**  >  **tüm dillerde**  >  **genel** veya hızlı başlatma ile "satır numarası" araması yaparak projenize satır numaraları ekleyebilirsiniz **(CTRL + Q)**. Satır numaraları, C++ dahil olmak üzere tüm diller veya yalnızca belirli diller için ayarlanabilir.

## <a name="scroll-and-zoom"></a>Kaydırma ve yakınlaştırma

**CTRL** tuşuna basarak ve fare tekerleği inizle kaydırarak düzenleyicide yakınlaştırıp uzaklaştırabilirsiniz. Ayrıca, sol alt köşedeki yakınlaştırma ayarını kullanarak da yakınlaştırma yapabilirsiniz.

![C&#43;&#43; yakınlaştırma denetimi](../ide/media/zoom-control.png "Yakınlaştırma denetimi")

Kaydırma çubuğu **harita modu** , geçerli konumunuzu çıkmadan bir kod dosyasına hızlıca kaydırma yapmanızı ve göz atmanıza olanak sağlar. Doğrudan bu konuma gitmek için kod haritasında herhangi bir yere tıklayabilirsiniz.

![C&#43;&#43;içindeki kod Haritası ](../ide/media/vs2015-cpp-code-map.png "Kod Haritası")

**Harita modunu** açmak için ana araç çubuğundaki **Hızlı başlatma** araması kutusuna "Eşle" yazın ve **kaydırma eşleme modunu kullan**' ı seçin. Daha fazla bilgi için bkz. [nasıl yapılır: kaydırma çubuğunu özelleştirerek kodunuzu izleme](/visualstudio/ide/how-to-track-your-code-by-customizing-the-scrollbar).

**Harita modu** kapalı olduğunda, kaydırma çubuğu hala dosyada yaptığınız değişiklikleri vurgulamaktadır. Yeşil, kaydedilen değişiklikleri ve sarı kaydedilmemiş değişiklikleri gösterir.

## <a name="quick-info-and-parameter-info"></a>Hızlı bilgi ve parametre bilgisi

Bildirim ve hemen öncesinde bulunan tüm yorumlar dahil olmak üzere herhangi bir değişken, işlev veya başka bir simgenin üzerine gelin.

::: moniker range="msvc-160"

![Visual Studio 2019 ' de Hızlı Bilgi ipucu gösteren ekran görüntüsü.](../ide/media/quick-info-vs2019.png "Hızlı Bilgi")

**Hızlı bilgi** araç Ipucunda bir **çevrimiçi arama** bağlantısı vardır. **Tools**  >  **Options**  >  **Text Editor**  >  **C++**  >  Arama sağlayıcısını belirtmek için Araçlar Seçenekler metin düzenleyicisi C++**görünümü** ' ne gidin.

Kodunuzda bir hata varsa, üzerine gelin ve **hızlı bilgi** hata iletisini görüntüler. Hata iletisini Hata Listesi penceresinde de bulabilirsiniz.

![Hata hakkında hızlı bilgi](../ide/media/quickinfo-on-error.png "Hata hakkında hızlı bilgi")

::: moniker-end

::: moniker range="<=msvc-150"

![Visual Studio 2017 ' de Hızlı Bilgi ipucu gösteren ekran görüntüsü.](../ide/media/quick-info.png "Hızlı Bilgi")

Kodunuzda bir hata varsa, üzerine gelin ve **hızlı bilgi** hata iletisini görüntüler. Hata iletisini **hata listesi** penceresinde de bulabilirsiniz.

![Hata hakkında hızlı bilgi](../ide/media/quickinfo-on-error.png "Hata hakkında hızlı bilgi")

::: moniker-end

Bir işlevi çağırdığınızda **parametre bilgisi** parametrelerin türlerini ve beklendikleri sırayı gösterir.

![C&#43;&#43;içindeki parametre bilgisi ](../ide/media/parameter-info.png "Parametre Bilgisi")

## <a name="peek-definition"></a>Tanıma Göz At

Bir değişken veya işlev bildiriminin üzerine gelin, sağ tıklayın ve ardından Geçerli konumunuzda uzaklaşmadan, tanımının satır içi görünümünü görmek için **Gözat** ' ı seçin. Daha fazla bilgi için bkz. [Peek tanımı (alt + F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12).

![C&#43;&#43; Özeti tanımı](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

## <a name="f1-help"></a>F1 Yardımı

İmleci herhangi bir tür, anahtar sözcük veya işlevi üzerine veya hemen sonrasına yerleştirin ve docs.microsoft.com üzerindeki ilgili başvuru konusuna doğrudan gitmek için **F1** 'e basın. **F1** Ayrıca hata listesindeki öğelerde ve birçok iletişim kutusunda da geçerlidir.

## <a name="class-view"></a>Sınıf Görünümü

**Sınıf görünümü** , tüm kod sembolleri ve bunların kapsam ve üst/alt hiyerarşilerinden proje temelinde düzenli olarak aranabilir bir ağaç kümesi görüntüler. **Sınıf görünümü ayarlarından** hangi **sınıf görünümü** görüntüleyeceğini yapılandırabilirsiniz (pencerenin üst kısmındaki dişli kutusu simgesine tıklayın).

![C&#43;&#43;Sınıf Görünümü ](../ide/media/class-view.png "Sınıf Görünümü")

## <a name="generate-graph-of-include-files"></a>Ekleme dosyalarının grafiğini oluştur

Projenizdeki bir kod dosyasına sağ tıklayın ve diğer dosyalar tarafından hangi dosyaların dahil edildiğini gösteren bir grafik görmek için **ekleme dosyaları grafiğini oluştur** ' u seçin.

![İçerme dosyaları&#43;&#43; grafik](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

## <a name="view-call-hierarchy"></a>Çağrı hiyerarşisini görüntüle

Herhangi bir işlev çağrısına sağ tıklayın ve çağırdığı tüm işlevlerin özyinelemeli bir listesini ve bunu çağıran tüm işlevleri görüntüleyin. Listedeki her bir işlev aynı şekilde genişletilebilir. Daha fazla bilgi için bkz. [çağrı hiyerarşisi](/visualstudio/ide/reference/call-hierarchy).

![&#43;&#43; çağrısı hiyerarşisi](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

## <a name="see-also"></a>Ayrıca Bkz.

[Kodu düzenleme ve yeniden düzenleme (C++)](writing-and-refactoring-code-cpp.md)</br>
[Visual Studio 'da C++ kod tabanınız üzerinde gezinme](navigate-code-cpp.md)</br>
[C++ için Live Share işbirliği yapma](live-share-cpp.md)
