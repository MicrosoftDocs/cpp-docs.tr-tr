---
title: Visual Studio 'da C++ kodunu düzenleme ve yeniden düzenleme
description: Kodunuzu biçimlendirmek, gezinmek, anlamak ve yeniden düzenleyin için Visual Studio 'da C++ kod düzenleyicisini kullanın.
ms.date: 05/31/2019
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.topic: overview
ms.openlocfilehash: bf34bf39bc41841be72c9400ec63c501d7aa56a3
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686338"
---
# <a name="edit-and-refactor-c-code-in-visual-studio"></a>Visual Studio 'da C++ kodunu düzenleme ve yeniden düzenleme

Visual Studio, kodunuzu yazma, düzenleme ve yeniden düzenleme konusunda size yardımcı olmak için çeşitli araçlar sağlar.

## <a name="intellisense"></a>IntelliSense

IntelliSense, siz yazarken sizin için semboller ve kod parçacıkları öneren güçlü bir kod tamamlama aracıdır. Visual Studio 'da C++ IntelliSense gerçek zamanlı olarak çalışarak kod tabanınızı güncelleştirerek ve öneriler sunarak analiz etmeniz gerekir. Daha fazla karakter yazdığınızda önerilen sonuçların listesi aşağı doğru azaltıyor.

![C&#43;&#43; üye listesi açılan listesi](../ide/media/cpp-statement-completion.png)

Sonuçların daralmasına yardımcı olmak için bazı semboller otomatik olarak atlanır. Örneğin, sınıfın dışından bir sınıf nesnesi üyelerine erişirken, varsayılan olarak veya korumalı Üyeler (bir alt sınıf bağlamında değilseniz) özel üyeleri göremezsiniz. En alttaki düğmeleri kullanarak filtrelemeyi ayarlayabilirsiniz.

Aşağı açılan listeden simgeyi seçtikten sonra, **sekme**, **giriş**veya diğer tamamlama karakterlerinden biri (varsayılan olarak:) ile otomatik olarak bu seçeneği kullanabilirsiniz `{ } [ ] ( ) . , : ; + - * / % & | ^ ! = ? @ # \` . Bu listeye karakter eklemek veya kaldırmak için **Hızlı başlatma** bölümünde "IntelliSense" araması yapın (CTRL + Q) ve **metin düzenleyici > C/C++ > gelişmiş** seçeneğini belirleyin. **Üye listesi tamamlama karakterleri** seçeneği, listeyi istediğiniz değişikliklerle özelleştirmenizi sağlar.

**Üye listesi filtre modu** seçeneği, ne tür IntelliSense AutoComplete önerilerini görmenizi denetler. Varsayılan olarak, **belirsiz**olarak ayarlanır. Benzer bir aramada, *Myawesomeclass*adlı bir sembolünüz varsa, "Mac" yazabilir ve otomatik tamamlama önerileriniz içinde sınıfı bulabilirsiniz. Benzer algoritma, simgelerin listede görünmesi için uyması gereken minimum eşiği ayarlar. **Akıllı** filtreleme, yazdıklarınız ile eşleşen alt dizeleri içeren tüm sembolleri görüntüler. **Ön ek** filtrelemesi, yazdıklarıyla başlayan dizeleri arar.

C++ IntelliSense hakkında daha fazla bilgi için bkz. IntelliSense için [Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense) ve [C++ projesi yapılandırma](/visualstudio/ide/visual-cpp-intellisense-configuration).

## <a name="intellicode"></a>IntelliCode

Intellicode, AI destekli IntelliSense 'dir. En olası adayı tamamlanma listenizin en üstüne koyar. Intellicode önerileri, GitHub üzerindeki binlerce açık kaynaklı projeyi, her biri 100 yıldızlı yıldızla temel alır. Kodunuzun bağlamı ile birleştirildiğinde, tamamlanma listesi ortak uygulamaları yükseltmek için tasarlanmıştır.

C++ yazarken, C++ standart kitaplığı gibi popüler kitaplıklar kullanılırken ıntellicode yardımcı olacaktır. Kodunuzun bağlamı öncelikle en faydalı önerileri sağlamak için kullanılır. Aşağıdaki örnekte, `size` üye işlevi genellikle `sort` işleviyle kullanılır, bu nedenle sonuçlar listesinin en üstüne gelir.

![C&#43;&#43; ıntellicode](../ide/media/intellicode-cpp.png "C++ ıntellicode")

::: moniker range="vs-2019"

Visual Studio 2019 ' de, ıntellicode, **C++ masaüstü geliştirme** iş yükünde isteğe bağlı bir bileşen olarak sunulmaktadır. Intellicode 'un C++ için etkin olduğundan emin olmak için, **Araçlar**  >  **Seçenekler**  >  **ıntellicode**  >  **genel** ' e gidin ve **C++ temel modelini** **etkin**olarak ayarlayın.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 ' de, ıntellicode Visual Studio Market bir uzantı olarak kullanılabilir.

::: moniker-end

## <a name="predictive-intellisense-experimental"></a>Tahmine dayalı IntelliSense (deneysel)

Tahmine **dayalı IntelliSense** , IntelliSense açılan listesinde görüntülenen sonuçların sayısını sınırlamak için bağlamsal tanıma kullanan deneysel bir özelliktir. Algoritma, yalnızca beklenen türle eşleşen sonuçları görüntüleyecek şekilde tür eşleştirmeyi uygular. En basit durumda, `int x =` IntelliSense açılan listesini yazıp çağırdığınızda yalnızca tamsayılar döndüren tamsayılar veya işlevler görürsünüz. Hala geliştirilme aşamasında olduğundan, bu özellik varsayılan olarak kapalıdır. Genel simgelerle en iyi şekilde çalışmaktadır; üye işlevleri henüz desteklenmiyor. **Hızlı başlatma** bölümünde "tahmine dayalı" yazarak veya **Araçlar**  >  **Seçenekler**  >  **metin Düzenleyicisi**  >  **C/C++**  >  **deneysel**tahmine  >  **dayalı IntelliSense 'i etkinleştir**' e giderek bunu açabilirsiniz.

Tahmine **dayalı IntelliSense** 'i geçersiz kılmak ve uzun listesini göstermek için **CTRL + J**tuşlarına basın. Tahmine dayalı **IntelliSense** açık Ise, **CTRL + J** çağırma, tahmine dayalı Filtreyi kaldırır. **CTRL + J** tuşlarına basıldığında, Ilgili yerlerde üye listesi sonuçlarından erişilebilirlik filtresi kaldırılır. IntelliSense açılan listesinin altındaki ([+]) düğmesi, **CTRL + J**ile aynı şeyi yapar. Gösterilmekte olan özellikler hakkında araç ipucu bilgilerini görmek için düğmenin üzerine gelin.

![C&#43;&#43; tahmine dayalı IntelliSense](../ide/media/predictive-intellisense-cpp.png "Tahmine dayalı IntelliSense")

Önceki ekran görüntüsünde, açılan liste altında birkaç düğme gösterilmektedir. Bunlar, farklı türlerde sonuçlar için IntelliSense filtrelerini etkinleştirir:

- Değişkenler ve sabitler
- İşlevler
- Türler
- Makrolar
- Numaralandırmalar
- Ad alanları

Bir düğme yalnızca geçerli IntelliSense oturumunuzla ilgiliyse görüntülenir. Genellikle tüm düğmeleri aynı anda görmezsiniz.

## <a name="template-intellisense"></a>Şablon IntelliSense

Giriş işareti bir şablon tanımının içindeyken, IntelliSense için örnek şablon bağımsız değişkenleri sağlamanıza olanak tanıyan bir **şablon çubuğu** görünür.

![C&#43;&#43; şablonu IntelliSense mevcut örneklemeleri göster](../ide/media/template-intellisense-cpp-1.png "Şablon IntelliSense mevcut örneklemeleri göster")

**\<T>** **Şablon çubuğunu**genişletmek/daraltmak için simgeye tıklayın. **Düzenle** penceresini açmak için kalem simgesine tıklayın veya **şablon çubuğuna** çift tıklayın.

![C&#43;&#43; şablonu IntelliSense](../ide/media/template-intellisense-cpp-3.png "Şablon IntelliSense")

Pencerede yaptığınız düzenlemeler, etkileri gerçek zamanlı olarak görebileceğiniz şekilde doğrudan kaynak koda uygulanır.

Şablon çubuğu, kodunuzdaki örneklemeleri temel alarak adayları otomatik olarak doldurabilir. Kod tabanınız genelinde şablonu örneklemek için kullanılan tüm somut bağımsız değişkenlerin listesini görmek için **mevcut tüm örneklemeleri Ekle** ' ye tıklayın.

![C&#43;&#43; şablonu IntelliSense sonuçlar listesi](../ide/media/template-intellisense-cpp-2.png "Şablon IntelliSense sonuçlar listesi")

Düzenleyicinin alt kısmındaki bir pencere, her bir örneklemede nerede nerede olduğunu ve bağımsız değişkenlerinin ne olduğunu gösterir.

![C&#43;&#43; şablonu IntelliSense örnek oluşturma eşlemesi](../ide/media/template-intellisense-cpp-4.png "Şablon IntelliSense örnek oluşturma eşlemesi")

**Şablon çubuğu** bilgileri kullanıcıya özgü olarak değerlendirilir. . Vs klasöründe depolanır ve kaynak denetimine uygulanmamalıdır.

## <a name="error-squiggles-and-quick-fixes"></a>Hata dalgalı çizgiler ve hızlı düzeltmeler

Düzenleyici, kodunuzla ilgili sorunları algılarsa, sorunun altında renkli dalgalı çizgiler eklenir. Red dalgalı çizgiler, derlenmeyen kodu gösterir. Yeşil dalgalı çizgiler, hala ciddi olabilecek diğer sorun türlerini gösterir. Sorunlar hakkında daha fazla bilgi edinmek için **hata listesi** penceresini açabilirsiniz.

Yaygın kodlama desenlerinin yanı sıra bazı hatalar için, düzenleyici, dalgalı bir ampulde yer alan bir ampul biçiminde **hızlı bir çözüm** sunar. Önerileri görmek için aşağı oka tıklayın.

Aşağıdaki örnekte, bir `vector` tanımı bildirildi ancak tanım bulunamadı, bu nedenle düzenleyici gerekli üst bilgi dosyasını dahil etmek için:

![Hata dalgalı çizgiler ve düzenleyicinin sunduğu hızlı düzelme gösteren ekran görüntüsü.](../ide/media/quick-fix-for-header-cpp.png "C++ hızlı düzeltilmesi")

Düzenleyici, bazı yeniden düzenleme fırsatları için de hızlı düzeltmeler sağlar. Örneğin, bir başlık dosyasında bir sınıf bildirirseniz, Visual Studio buna ayrı bir. cpp dosyasında bir tanım oluşturmayı sağlar.

![Kanallar nokta C p P 'de kanal yolu yineleyicisinin oluşturma tanımı ile hızlı düzeltilmesi gösteren ekran görüntüsü.](../ide/media/quick-fix.png "C++ hızlı düzeltilmesi")

## <a name="change-tracking"></a>Change tracking

Bir dosyada her değişiklik yaptığınızda, kaydedilmemiş değişikliklerin yapıldığını belirtmek için sol tarafta sarı bir çubuk görüntülenir. Dosyayı kaydettiğinizde, çubuk yeşile döner. Yeşil ve sarı çubuklar belge düzenleyicide açık olduğu sürece korunur. Belgeyi en son açtığınızdan bu yana yapılan değişiklikleri temsil ederler.

![C&#43;&#43; değişiklik izleme](../ide/media/change-tracking-cpp.png "Change tracking")

## <a name="move-code"></a>Kodu taşı

Kod satırlarını, alt tuşunu basılı tutarak ve **yukarı/aşağı** ok tuşlarına basarak yukarı ve aşağı taşıyabilirsiniz.

## <a name="insert-snippets"></a>Kod parçacığı Ekle

Kod parçacığı, kaynak kodu önceden tanımlanmış bir parçasıdır. Bir kod parçacığı eklemek veya seçili metni kod parçacığına çevrelemek için tek bir noktaya veya seçili metinde sağ tıklayın. Aşağıdaki çizimde, for döngüsü ile seçili bir deyimin çevrelemenin üç adımı gösterilmektedir. Son görüntüdeki sarı vurgular sekme tuşuyla erişebileceğiniz düzenlenebilir alanlardır. Daha fazla bilgi için bkz. [kod parçacıkları](/visualstudio/ide/code-snippets).

![C&#43;&#43; kod parçacığı ekleme&#45;aşağı](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

## <a name="add-class"></a>Sınıf Ekle

**Proje** menüsünden veya **Çözüm Gezgini**bağlam menüsünden Yeni bir sınıf ekleyin:

![C&#43;&#43;yeni sınıf Ekle ](../ide/media/vs2017-add-class.png "vs2015_cpp_add_class")

Ayrıca, varolan bir sınıfı değiştirmek veya incelemek için sınıf Sihirbazı 'Nı kullanabilirsiniz.

![C&#43;&#43; sınıfı Sihirbazı](../ide/media/vs2017-class-wizard.png)

Daha fazla bilgi için bkz. [kod sihirbazları Ile Işlevsellik ekleme (C++)](../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="refactoring"></a>Yeniden Düzenle

Yeniden düzenlemeler, hızlı eylem bağlam menüsü altında veya [düzenleyicide bir](/visualstudio/ide/perform-quick-actions-with-light-bulbs) ampulye tıklayarak kullanılabilir.  Bazıları Ayrıca **düzenle > yeniden düzenleme** menüsünde de bulunur.  Bu özellikler şunları içerir:

- [Yeniden Adlandır](refactoring/rename.md)
- [Extract Işlevi](refactoring/extract-function.md)
- [Saf sanalları Uygula](refactoring/implement-pure-virtuals.md)
- [Bildirim/tanım oluştur](refactoring/create-declaration-definition.md)
- [Işlev tanımını taşı](refactoring/move-definition-location.md)
- [Ham dize değişmez değerine Dönüştür](refactoring/convert-to-raw-string-literal.md)
- [Imzayı Değiştir](refactoring/change-signature.md)

## <a name="code-style-enforcement-with-clangformat-and-editorconfig"></a>ClangFormat ve EditorConfig ile kod stili zorlama

Visual Studio 2017 ve üzeri, Clang/LLVM 'yi temel alan C++ için popüler kod biçimlendirme yardımcı programı olan [Clangformat](https://clang.llvm.org/docs/ClangFormat.html)için yerleşik destek sunar. Aşağıdaki ortak biçimlerden birini kullanmak üzere ayarlamak için [hızlı başlatmaya](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) "ClangFormat" yazın:

- LLVM
- Google
- Bulunamazsa Chromium
- Mozilla
- WebKit
- Visual Studio

Ayrıca kendi. Clang-format veya _clang biçimli dosyanızı, tüm kod dosyalarına aynı düzeyde veya altında özel kurallar uygulamak için de sağlayabilirsiniz.

Dosyalar, kaynak denetimi aracılığıyla kolayca paylaşılabilir, bu sayede tüm geliştirme ekibiniz genelinde kodlama kurallarını zorunlu kılabilirsiniz.

![C&#43;&#43; Clang biçimi](../ide/media/clang-format-cpp.png "Clang biçimi")

Visual Studio 2017 ve üzeri, benzer bir şekilde çalışabilen [Editorconfig](https://editorconfig.org/)'i de destekler. Ancak, ClangFormat, C++ ' a özel kurallar da dahil olmak üzere EditorConfig öğesinden daha fazla stil seçeneklerine sahiptir. **Editorconfig**ile, **. editorconfig** dosyaları oluşturur ve bu klasörler ve alt klasörleri için kod stilleri belirtmek üzere kodu kod tabanınızın farklı klasörlerine yerleştirebilirsiniz. Bir **. editorconfig** dosyası, üst klasörlerdeki diğer tüm **. editorconfig** dosyalarının yerini alır ve **Araçlar**  >  **seçenekleri**aracılığıyla yapılandırılan biçimlendirme ayarlarının üzerine yazar. Sekmeler ve boşluklar, girinti boyutu ve daha fazlası için kurallar ayarlayabilirsiniz. Daha fazla bilgi için bkz. [EditorConfig ile taşınabilir, özel düzenleyici ayarları oluşturma](/visualstudio/ide/create-portable-custom-editor-options).

## <a name="other-formatting-options"></a>Diğer biçimlendirme seçenekleri

**Hızlı Başlat** arama kutusu, bir ayar veya aracı bulmanın en hızlı yolunu sağlar. Ana menüde bulunur. Yazmaya başlamanız yeterlidir ve otomatik tamamlama listesi sonuçları filtreleyecek.

![Visual Studio hızlı başlatma](../ide/media/vs2015_cpp_quick_launch.png "Hızlı Başlat")

Girintiler, küme ayracı tamamlama ve renklendirme gibi biçimlendirme seçeneklerini ayarlamak için **Hızlı Başlat** penceresine "C++ Formatting" yazın.

![C++ biçimlendirme seçenekleri](media/cpp-formatting-options.png)

Diğer biçimlendirme seçenekleri **Edit**  >  , ana menüdeki**Gelişmiş** Düzenle altında bulunur.

![C++ Gelişmiş düzenlemesi seçenekleri](media/edit-advanced-cpp.png)

C++ özel düzenleme özelliklerini etkinleştirme ve yapılandırmaya yönelik seçenekler **Araçlar**  >  **Seçenekler**  >  **metin Düzenleyicisi**  >  **C/C++** altında bulunur. Hangi seçeneği ayarlamak istediğinizi seçtikten sonra iletişim kutusu odaklanıldığında **F1** tuşuna basarak daha fazla yardım alabilirsiniz. Genel kod biçimlendirme seçenekleri için `Editor C++` **Hızlı başlatma**' ya yazın.

![Visual Studio Araçları > seçenekleri](../ide/media/tools-options.png "Düzenleyici seçenekleri")

Visual Studio 'nun gelecekteki bir sürümünde yer alan veya dahil olmayan Deneysel özellikler, [metin düzenleyici C++ deneysel](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) iletişim kutusunda bulunur. Visual Studio 2017 ve sonraki sürümlerde, tahmine **dayalı IntelliSense** 'i bu iletişim kutusunda etkinleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[C++ kodunu okuma ve anlama](read-and-understand-code-cpp.md)</br>
[Visual Studio 'da C++ kod tabanınız üzerinde gezinme](navigate-code-cpp.md)</br>
[C++ için Live Share işbirliği yapma](live-share-cpp.md)
