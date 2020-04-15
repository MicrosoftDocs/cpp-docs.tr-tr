---
title: Visual Studio'da C++ kodunu düzenleme ve yeniden düzenleme
description: Kodunuzu biçimlendirmek, gezinmek, anlamak ve yeniden düzenlemek için Visual Studio'daki C++ kod düzenleyicisini kullanın.
ms.date: 05/31/2019
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.topic: overview
ms.openlocfilehash: 070c79e02f6e05adeda5f17a0dde02afdf22703b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353737"
---
# <a name="edit-and-refactor-c-code-in-visual-studio"></a>Visual Studio'da C++ kodunu düzenleme ve yeniden düzenleme

Visual Studio, kodunuzu yazmanıza, düzenlemenize ve yeniden düzenlemenize yardımcı olacak çeşitli araçlar sağlar.

## <a name="intellisense"></a>IntelliSense

IntelliSense, yazarken sizin için semboller ve kod parçacıkları öneren güçlü bir kod tamamlama aracıdır. Visual Studio'daki C++ IntelliSense gerçek zamanlı olarak çalışır, güncellediğiniz gibi kod tabanınızı analiz ederek ve öneriler sunar. Daha fazla karakter yazdıkça, önerilen sonuçlar listesi daralır.

![C&#43;&#43; üye listesi açılır](../ide/media/cpp-statement-completion.png)

Bazı semboller, sonuçları daraltmaya yardımcı olmak için otomatik olarak atlanır. Örneğin, sınıf dışından bir sınıf nesnesinin üyelerine erişirken, varsayılan olarak özel üyeleri veya korumalı üyeleri göremezsinuz (alt sınıf bağlamında değilseniz). Alttaki düğmeleri kullanarak filtrelemi ayarlayabilirsiniz.

Açılan listeden sembolü seçtikten sonra, **Sekme**, **Enter**veya diğer commit karakterlerden biriyle otomatik olarak `{ } [ ] ( ) . , : ; + - * / % & | ^ ! = ? @ # \`tamamlayabilirsiniz (varsayılan olarak: ). Bu listeden karakter eklemek veya kaldırmak için **Hızlı Başlatma** 'da (Ctrl + Q) "IntelliSense"i arayın ve **> C/C++ > Gelişmiş** seçeneğini seçin. **Üye Listesi Karakterleri Commit** seçeneği, listeyi istediğiniz değişikliklerle özelleştirmenize olanak tanır.

**Üye Listesi Filtre Modu** seçeneği, ne tür IntelliSense otomatik tamamlama önerilerini gördüğünüzü denetler. Varsayılan olarak, **Bulanık**olarak ayarlanır. Bulanık bir aramada, *MyAwesomeClass*adında bir sembole sahipseniz , "MAC" yazabilir ve sınıfı otomatik tamamlama önerilerinizde bulabilirsiniz. Bulanık algoritma, sembollerin listede görünabilmesi için karşılaması gereken minimum eşiği ayarlar. **Akıllı** filtreleme, yazdığınız la eşleşen alt dizeleri içeren tüm sembolleri görüntüler. **Önek** filtreleme, yazdığınız la başlayan dizeleri arar.

C++ IntelliSense hakkında daha fazla bilgi için [Visual C++ IntelliSense'e](/visualstudio/ide/visual-cpp-intellisense) bakın ve [IntelliSense için bir C++ projesini yapılandırın.](/visualstudio/ide/visual-cpp-intellisense-configuration)

## <a name="intellicode"></a>IntelliCode

IntelliCode, AI destekli IntelliSense'dir. En olası adayı tamamlama listenizin en üstüne koyar. IntelliCode önerileri, her biri 100'den fazla yıldıza sahip GitHub'daki binlerce açık kaynak projesine dayanmaktadır. Kodunuzu bağlamıyla birleştirildiğinde, tamamlanma listesi yaygın uygulamaları teşvik etmek üzere uyarlanır.

C++'ı yazarken IntelliCode, C++ Standart Kitaplığı gibi popüler kitaplıkları kullanırken yardımcı olur. Kodunuzun bağlamı ilk olarak en yararlı önerileri sağlamak için kullanılır. Aşağıdaki örnekte, `size` üye işlev genellikle `sort` işlevle birlikte kullanılır, bu nedenle sonuç listesinin en üstüne çıkar.

![C&#43;&#43; IntelliCode](../ide/media/intellicode-cpp.png "C++ IntelliCode")

::: moniker range="vs-2019"

Visual Studio 2019'da IntelliCode, **C++ Masaüstü Geliştirme** iş yükünde isteğe bağlı bir bileşen olarak kullanılabilir. IntelliCode'un C++için etkin olduğundan emin olmak için **Tools** > **Options** > **IntelliCode** > **General'e** gidin ve **C++ taban modelini** **Etkin**olarak ayarlayın.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017'de IntelliCode, Visual Studio Marketplace'te uzantı olarak mevcuttur.

::: moniker-end

## <a name="predictive-intellisense-experimental"></a>Predictive IntelliSense (Deneysel)

**Predictive IntelliSense,** IntelliSense açılır listesinde görüntülenen sonuç sayısını sınırlamak için bağlamsal farkındalığı kullanan deneysel bir özelliktir. Algoritma, yalnızca beklenen türle eşleşen sonuçları gösterebilmek için tür eşlemi uygular. En basit durumda, IntelliSense açılır düşüşünü yazıp `int x =` çağırırsanız, yalnızca tamsayıları veya işlevleri niçin döndüreceğini görürsünüz. Bu özellik, hala geliştirilmekte olduğundan varsayılan olarak kapalıdır. Bu küresel semboller ile en iyi çalışır; üye işlevler henüz desteklenmemektedir. **Hızlı Başlatma'da** "Predictive" yazarak veya **Tools** > **Options** > **Text Editor** > **C/C++** > **Experimental** > **Enable Predictive IntelliSense'e**giderek açabilirsiniz.

**Predictive IntelliSense'i** geçersiz kılmak ve uzun listeyi göstermek için **Ctrl + J**tuşuna basın. **Predictive IntelliSense** acındaysa, **Ctrl + J'yi** çağırmak Tahmin filtresini kaldırır. **Ctrl + J** tuşuna basıldığında, ilgili durumlarda Üye Listesi sonuçlarından erişilebilirlik filtresi yine kaldırılır. IntelliSense açılır listesinin altındaki ([+]) düğmesi **Ctrl + J**ile aynı şeyi yapar. Gösterilenler hakkında araç ipucu bilgilerini görmek için düğmenin üzerine titreyin.

![C&#43;&#43; Öngörücü IntelliSense](../ide/media/predictive-intellisense-cpp.png "Tahmine Dayalı IntelliSense")

Önceki ekran görüntüsü açılır liste altında birkaç düğme gösterir. Bunlar, farklı türde sonuçlar için IntelliSense Filtreleri'ni etkinleştirin:

- Değişkenler ve Sabitler
- İşlevler
- Türler
- Makrolar
- Numaralandırmalar
- Ad Alanları

Bir düğme yalnızca geçerli IntelliSense oturumunuzla alakalıysa görüntülenir. Genellikle tüm düğmeleri aynı anda görmezsiniz.

## <a name="template-intellisense"></a>Şablon IntelliSense

Basamak bir şablon tanımının içindeyken, IntelliSense için örnek şablon bağımsız değişkenleri sağlamanıza olanak tanıyan bir **Şablon Çubuğu** görüntülenir.

![C&#43;&#43; Şablon ItelliSense Mevcut Anlık Açıklamaları Göster](../ide/media/template-intellisense-cpp-1.png "Şablon IntelliSense Mevcut Anlık Açıklamaları Göster")

Şablon ** \<** **Çubuğu'nu**genişletmek/daraltmak için T>simgesini tıklatın. Kalem simgesini tıklatın veya **Edit** penceresini açmak için **Şablon Çubuğu'nu** çift tıklatın.

![C&#43;&#43; Şablon IntelliSense](../ide/media/template-intellisense-cpp-3.png "Şablon IntelliSense")

Pencerede yaptığınız edeişler, efektleri gerçek zamanlı olarak görebilmeniz için doğrudan kaynak koduna uygulanır.

Şablon Çubuğu, kodunuzdaki anlık açıklamalara göre adayları otomatik olarak doldurabilir. Şablonu kod tabanınız boyunca anında görüntülemek için kullanılan tüm somut bağımsız değişkenlerin listesini görmek için **Varolan Tüm Anlık Değişkenleri Ekle'yi** tıklatın.

![C&#43;&#43; Şablon IntelliSense Sonuç Listesi](../ide/media/template-intellisense-cpp-2.png "Şablon IntelliSense Sonuç Listesi")

Düzenleyicinin altındaki bir pencere, her anlık noktanın nerede bulunduğunu ve bağımsız değişkenlerinin ne olduğunu gösterir.

![C&#43;&#43; Şablon ItelliSense Anlık Harita](../ide/media/template-intellisense-cpp-4.png "Şablon IntelliSense Anlık Harita")

**Şablon Çubuğu** bilgileri kullanıcıya özel olarak kabul edilir. .vs klasöründe depolanır ve kaynak denetimine bağlı değildir.

## <a name="error-squiggles-and-quick-fixes"></a>Hata squiggles ve hızlı düzeltmeler

Düzenleyici kodunuzun sorunlarını algılarsa, sorunun altına renkli dalgalar ekler. Kırmızı dalgalı lar derlemeyen kodu gösterir. Yeşil dalgalı hala potansiyel olarak ciddi olabilir sorunların diğer tür gösterir. Sorunlar hakkında daha fazla bilgi almak için **Hata Listesi** penceresini açabilirsiniz.

Bazı hatalar, yanı sıra ortak kodlama desenleri için, editör dalgalı üzerinde gezinmek zaman görünen bir ampul şeklinde bir **Quick Fix** sunacak. Önerileri görmek için aşağı oka tıklayın.

Aşağıdaki örnekte, `vector` bir beyan edildi, ancak tanım bulunamadı, bu nedenle düzenleyici gerekli üstbilgi dosyasını eklemeyi teklif ediyor:

![C&#43;&#43; hızlı düzeltme](../ide/media/quick-fix-for-header-cpp.png "C++ Hızlı Düzeltme")

Editör ayrıca bazı refactoring fırsatları için Hızlı Düzeltmeler sunuyor. Örneğin, bir üstbilgi dosyasında bir sınıf bildirirseniz, Visual Studio bunun için ayrı bir .cpp dosyasında bir tanım oluşturmayı teklif edecektir.

![C&#43;&#43; hızlı düzeltme](../ide/media/quick-fix.png "C++ Hızlı Düzeltme")

## <a name="change-tracking"></a>Değişiklik izleme

Bir dosyada değişiklik yaptığınızda, kaydedilmemiş değişikliklerin yapıldığını belirtmek için solda sarı bir çubuk görüntülenir. Dosyayı kaydettiğinizde, çubuk yeşile döner. Belge düzenleyicide açık olduğu sürece yeşil ve sarı çubuklar korunur. Belgeyi en son açtığınız için yapılan değişiklikleri temsil ederler.

![C&#43;&#43; değişiklik izleme](../ide/media/change-tracking-cpp.png "Değişiklik izleme")

## <a name="move-code"></a>Kodu taşıma

Kod satırlarını seçerek, Alt'ı basılı tutarak ve **Yukarı/Aşağı** ok tuşlarına basarak yukarı ve aşağı hareket ettirebilirsiniz.

## <a name="insert-snippets"></a>Parçacık ekleme

Parçacık, kaynak kodunun önceden tanımlanmış bir parçasıdır. Bir parçacık eklemek veya seçili metni snippet ile çevrelemek için tek bir noktaya veya seçili metne sağ tıklayın. Aşağıdaki resimde, seçili bir ifadeyi for döngüsüyle çevreleyen üç adım gösterilmektedir. Son görüntüdeki sarı vurgular, sekme tuşuyla erişebildiğiniz değiştirilebilir alanlardır. Daha fazla bilgi için [Kod Parçacıkları'na](/visualstudio/ide/code-snippets)bakın.

![C&#43;&#43; Eklemek Snippet Bırak&#45;aşağı](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

## <a name="add-class"></a>Sınıf Ekle

**Project** menüsünden veya **Çözüm Gezgini'ndeki**bağlam menüsünden yeni bir sınıf ekleyin:

![C&#43;&#43;Yeni Sınıf Ekle](../ide/media/vs2017-add-class.png "vs2015_cpp_add_class")

Varolan bir sınıfı değiştirmek veya incelemek için Sınıf Sihirbazı'nı da kullanabilirsiniz.

![C&#43;&#43; Sınıf Sihirbazı](../ide/media/vs2017-class-wizard.png)

Daha fazla bilgi için kod [sihirbazları (C++) ile İşlevsellik Ekleme'ye](../ide/adding-functionality-with-code-wizards-cpp.md)bakın.

## <a name="refactoring"></a>Yeniden Düzenle

Refactorings Hızlı Eylem bağlam menüsü altında veya düzenleyici bir [ampul](/visualstudio/ide/perform-quick-actions-with-light-bulbs) tıklayarak kullanılabilir.  Bazıları da **Edit > Refactor** menüsünde bulunur.  Bu özellikler şunlardır:

- [Yeniden Adlandır](refactoring/rename.md)
- [Ayıklama Fonksiyonu](refactoring/extract-function.md)
- [Saf Sanalları Uygula](refactoring/implement-pure-virtuals.md)
- [Beyanname Oluşturma / Tanım](refactoring/create-declaration-definition.md)
- [İşlev Tanımını Taşı](refactoring/move-definition-location.md)
- [Ham String Literal dönüştürün](refactoring/convert-to-raw-string-literal.md)
- [İmzayı Değiştir](refactoring/change-signature.md)

## <a name="code-style-enforcement-with-clangformat-and-editorconfig"></a>ClangFormat ve EditorConfig ile kod stili zorlama

Visual Studio 2017 ve daha sonra [Clang/LLVM](https://clang.llvm.org/docs/ClangFormat.html)tabanlı C++ için popüler bir kod biçimlendirme programı olan ClangFormat için yerleşik destek le birlikte gelir. Bu ortak biçimlerden birini kullanacak şekilde ayarlamak için [Hızlı Başlatma'ya](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) "ClangFormat" yazın:

- LLVM
- Google
- Krom
- Mozilla
- Webkit
- Visual Studio

Ayrıca, aynı düzeyde veya aşağıda tüm kod dosyalarına özel kurallar uygulamak için kendi .clang formatı veya _clang biçimi dosyanızı da sağlayabilirsiniz.

Dosyalar kaynak denetimi yoluyla kolayca paylaşılabilir, böylece tüm geliştirme ekibiniz arasında kodlama kurallarını uygulayabilirsiniz.

![C&#43;&#43; Clang Formatı](../ide/media/clang-format-cpp.png "Clang Biçimi")

Visual Studio 2017 ve daha sonra da benzer bir şekilde çalışır [EditorConfig](https://editorconfig.org/)destekler. Ancak ClangFormat, C++'a özgü kurallar da dahil olmak üzere EditorConfig'den daha fazla stil seçeneğine sahiptir. **EditorConfig**ile **.editorconfig** dosyaları oluşturur ve bu klasörler ve alt klasörleri için kod stilleri belirtmek için kod tabanınızın farklı klasörlerine yerebilirsiniz. Bir **.editorconfig** dosyası, üst klasörlerdeki diğer **.editorconfig** dosyalarının yerini alıyor ve **Araçlar** > **Seçenekleri**aracılığıyla yapılandırılan biçimlendirme ayarlarının üzerine yazıyor. Sekmeler ve boşluklar, girinti boyutu ve daha fazlası için kurallar ayarlayabilirsiniz. Daha fazla bilgi için bkz: [EditorConfig ile taşınabilir, özel düzenleyici ayarları oluştur.](/visualstudio/ide/create-portable-custom-editor-options)

## <a name="other-formatting-options"></a>Diğer biçimlendirme seçenekleri

**Hızlı Başlatma** arama kutusu, bir ayarı veya aracı bulmanın en hızlı yolunu sağlar. Ana menüde yer almaktadır. Yazmaya başlayın ve otomatik tamamlama listesi sonuçları filtreleyecek.

![Visual Studio Hızlı Lansman](../ide/media/vs2015_cpp_quick_launch.png "Hızlı Başlat")

Girintiler, ayraç tamamlama ve renklendirme gibi biçimlendirme seçeneklerini ayarlamak için Hızlı **Başlatma** penceresine "C++ Biçimlendirme" yazın.

![C++ biçimlendirme seçenekleri](media/cpp-formatting-options.png)

Diğer biçimlendirme seçenekleri ana menüde**Gelişmiş** **Edit** > altında bulunur.

![C++ gelişmiş düzenleme seçenekleri](media/edit-advanced-cpp.png)

C++'a özgü düzenleme özelliklerini etkinleştirme ve yapılandırma seçenekleri **Tools** > **Options** > **Text Editor** > **C/C++** altında yer alır. Hangi seçeneği ayarlamak istediğinizi seçtikten sonra, iletişim odaklandığında **F1** tuşuna basarak daha fazla yardım alabilirsiniz. Genel kod biçimlendirme seçenekleri `Editor C++` için **Hızlı Başlatma'ya**yazın.

![Görsel Stüdyo Araçları > Seçenekleri](../ide/media/tools-options.png "Editör seçenekleri")

Visual Studio'nun gelecekteki bir sürümüne dahil edilebilecek veya dahil edilmeyebilir deneysel özellikler, [Metin Editörü C++ Deneysel](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) iletişim kutusunda bulunur. Visual Studio 2017 ve daha sonra bu iletişim kutusunda **Predictive IntelliSense'i** etkinleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[C++ kodunu okuma ve anlama](read-and-understand-code-cpp.md)</br>
[Visual Studio'da C++ kod tabanınızda gezinme](navigate-code-cpp.md)</br>
[C++ için Live Share ile işbirliği yapın](live-share-cpp.md)
