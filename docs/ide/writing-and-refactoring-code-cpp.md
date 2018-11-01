---
title: Yazma ve yeniden düzenleme kod (C++)
ms.date: 04/30/2018
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.openlocfilehash: bc839a759d2ff3f403ca001ab32702d3fe27833e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570436"
---
# <a name="writing-and-refactoring-code-c"></a>Yazma ve yeniden düzenleme kod (C++)

Visual C++ Kod Düzenleyicisi ve IDE birçok kodlama yardımları sağlar. Bazı C++ için özeldir ve bazı temel olarak tüm Visual Studio dilleri için aynıdır. Paylaşılan özellikler hakkında daha fazla bilgi için bkz. [kodu ve metin düzenleyicisi kod yazma](/visualstudio/ide/writing-code-in-the-code-and-text-editor). Etkinleştirme ve C++ diline özgü özelliklere yapılandırma seçenekleri altında bulunur **Araçları &#124; seçenekleri &#124; metin düzenleyici &#124; C/C++**. Hangi seçeneği ayarlamak istediğiniz seçtikten sonra daha fazla yardım tuşuna basarak alabilirsiniz **F1** iletişim kutusu, odakta olduğunda. Biçimlendirme seçenekleri genel kodunu yazın `Editor C++` içine **hızlı başlatma**.

Visual Studio, gelecek bir sürümünde bulunmayabilir veya olabilir, Deneysel özellikler bulunur [metin düzenleyicisi C++ Deneysel](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) iletişim. Visual Studio 2017'de etkinleştirebilirsiniz **Tahmine dayalı IntelliSense** bu iletişim kutusunda.

## <a name="adding-new-files"></a>Yeni dosyaları ekleme

Yeni dosyaları bir projeye eklemek için Çözüm Gezgini'nde proje düğümüne sağ tıklayın ve seçin **Ekle &#124; yeni**.

## <a name="formatting-options"></a>Biçimlendirme seçenekleri

Biçimlendirme seçenekleri girintileri, küme ayracı tamamlama ve renklendirme gibi ayarlamak için "Biçimlendirme C++" yazdığınız **hızlı başlatma** penceresi. Visual Studio 2017 sürüm 15.7 ve üzeri ClangFormat destekler. İçinde yapılandırabileceğiniz [C/C++ biçimlendirme özellik sayfası](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting) altında **Araçları &#124; seçenekleri &#124; metin düzenleyici &#124; C/C++ &#124; biçimlendirme**.

![C++, biçimlendirme seçenekleri](media/cpp-formatting-options.png)

## <a name="intellisense"></a>IntelliSense

IntelliSense üyeler, türler ve işlev aşırı yüklemelerinin satır içi bilgi sağlayan bir dizi adıdır. Siz yazarken görüntülenen üye listesi açılır aşağıda gösterilmiştir. Seçili öğe metni kod dosyanıza girmek için SEKME tuşuna basabilirsiniz.

![C&#43; &#43; üye listesi açılan](../ide/media/vs2015_cpp_statement_completion.png "vs2015_cpp_statement_completion")

Tam bilgi için bkz. [Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense).

## <a name="insert-snippets"></a>Kod parçacıkları ekleme

Bir kod parçacığı, kaynak kodu önceden tanımlanmış bir parçasıdır. Bir kod parçacığı Ekle ya da seçili metni parçacığıyla çevreleyen seçili metni veya tek bir nokta üzerinde sağ tıklayın. Seçili deyimiyle kapsamak için üç adım aşağıdaki çizimde bir for döngüsü. Son görüntüde sarı vurgular ile sekmesindeki anahtara erişim düzenlenebilir alanlardır. Daha fazla bilgi için [kod parçacıkları](/visualstudio/ide/code-snippets).

![Visual C&#43; &#43; kod parçacığı Ekle bırak&#45;aşağı](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

## <a name="add-class"></a>Sınıf ekleme

Yeni bir sınıf ekleyin **proje** sınıfı Sihirbazı'nı kullanarak menüsü.

![Visual C yeni sınıf ekleyin&#43;&#43;](../ide/media/vs2015_cpp_add_class.png "vs2015_cpp_add_class")

Sınıf Sihirbazı, değiştirin veya varolan bir sınıf incelemek için de kullanabilirsiniz.

![Visual C&#43; &#43; sınıf Sihirbazı](../ide/media/vs2015_cpp_class_wizard.png "vs2015_cpp_class_wizard")

Daha fazla bilgi için [işlevsellik ekleme kodu sihirbazları (C++) ile](../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="refactoring"></a>Yeniden Düzenle

Yeniden düzenlemeler tıklayarak veya, hızlı eylem bağlam menüsü altında kullanılabilir bir [ampul](/visualstudio/ide/perform-quick-actions-with-light-bulbs) Düzenleyicisi.  Bazı de bulunan **Düzenle > yeniden düzenleme** menüsü.  Bu özellikler şunlardır:

* [Yeniden Adlandır](refactoring/rename.md)
* [İşlevi Ayıkla](refactoring/extract-function.md)
* [Saf Sanalları Uygula](refactoring/implement-pure-virtuals.md)
* [Bildirim / Tanım Oluştur](refactoring/create-declaration-definition.md)
* [Move İşleminin Tanımı](refactoring/move-definition-location.md)
* [Ham Dize Sabit Değerine Dönüştür](refactoring/convert-to-raw-string-literal.md)
* [İmzayı Değiştir](refactoring/change-signature.md)

## <a name="navigate-and-understand"></a>Gidin ve anlama

Visual C++, diğer dillerle birlikte birçok kod gezintisi özelliklerinde paylaşır. Daha fazla bilgi için [gezinme kod](/visualstudio/ide/navigating-code) ve [Structure of Code görüntüleme](/visualstudio/ide/viewing-the-structure-of-code).

## <a name="quickinfo"></a>Quickınfo'da

Tür bilgileri görmek için bir değişken üzerinde gezdirin.

![Visual C&#43; &#43; Hızlıbilgi](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")

## <a name="open-document-navigate-to-header"></a>Açık belge (üst bilgi Git)

Üst bilgi adı sağ tıklayın bir `#include` yönergesi ve üst bilgi dosyasını açın.

![Visual C&#43; &#43; açık belge menü seçeneği](../ide/media/vs2015_cpp_open_document.png "vs2015_cpp_open_document")

## <a name="peek-definition"></a>Tanıma göz at

Bir değişken veya işlev bildiriminin sağ tıklayın, ardından gelin seçin **Özet tanım** tanımına bir satır içi görünümünü görmek için. Daha fazla bilgi için [Özet tanım (Alt + F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12).

![Visual C&#43; &#43; Özet tanımı](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

## <a name="go-to-definition"></a>Tanıma Git

Bir değişken veya işlev bildiriminin sağ tıklayın, ardından gelin seçin **tanıma** nesne tanımlandığı belgeyi açmak için.

## <a name="view-call-hierarchy"></a>Çağrı hiyerarşisini görüntüle

Herhangi bir işlev çağrısına sağ tıklayın ve çağrı yaptığı tüm işlevlerin ve çağırdığı tüm işlevlerin resursive listesini görüntüleyin. Listedeki her işlev aynı şekilde genişletilebilir. Daha fazla bilgi için [çağrı hiyerarşisi](/visualstudio/ide/reference/call-hierarchy).

![Visual C&#43; &#43; çağrı hiyerarşisi](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

## <a name="toggle-header--code-file"></a>Başlık / kod dosyası

Sağ tıklatın ve seçin **geçiş başlık / kod dosyası** sürekli bir üstbilgi dosyası ve ilişkili bir kod dosyası arasında geçiş yapmak için.

## <a name="outlining"></a>Anahat Oluşturma

Bir kaynak kodu dosyasında herhangi bir yere sağ tıklayın ve seçin **anahat** tanımları ve/veya yalnızca ilgilendiğiniz bölümlerini Gözat daha kolay hale getirmek için özel bölgeleri'ni genişletin veya daraltın. Daha fazla bilgi için [anahat](/visualstudio/ide/outlining).

![Visual C&#43; &#43; anahat oluşturma](../ide/media/vs2015_cpp_outlining.png "vs2015_cpp_outlining")

## <a name="scrollbar-map-mode"></a>Kaydırma çubuğu eşleme modu

Kaydırma çubuğu eşleme modu hızla kaydırma ve bir kod dosyası geçerli konumunuzu çıkmadan Gözat olanak tanır. Veya bu konuma gitmek için kod Haritası üzerinde herhangi bir yere tıklayın. Daha fazla bilgi için [nasıl yapılır: kaydırma çubuğunu özelleştirerek kodunuzu izleme](/visualstudio/ide/how-to-track-your-code-by-customizing-the-scrollbar).

![Kod haritasında Visual C&#43;&#43;](../ide/media/vs2015_cpp_code_map.png "vs2015_cpp_code_map")

## <a name="generate-graph-of-include-files"></a>Ekleme dosyalarının grafını oluştur

Bir kod dosyası projenize sağ tıklayın ve seçin **ekleme dosyalarının grafını Oluştur** hangi dosyaları diğer dosyalar tarafından eklenir bir grafik görmek için.

![Visual C&#43; &#43; ekleme dosyalarının grafı](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

## <a name="f1-help"></a>F1 Yardımı

Veya hemen sonrasında herhangi bir tür, anahtar sözcüğü veya işlev imleci yerleştirin ve docs.microsoft.com'da doğrudan ilgili başvuru konuya gitmek için F1 tuşuna basın. F1 öğeler için hata listesinden ve birçok iletişim kutularında üzerinde de çalışır.

## <a name="quick-launch"></a>Hızlı Başlat

Herhangi bir pencere veya Visual Studio araç kolayca gitmek için yalnızca kullanıcı arabiriminin sağ üst köşedeki Hızlı Başlat penceresinde adını yazın. Otomatik Tamamlama listesi, siz yazarken filtre uygular.

![Visual Studio hızlı başlatma](../ide/media/vs2015_cpp_quick_launch.png "vs2015_cpp_quick_launch")
