---
title: Düzenleme ve yeniden düzenleme C++ Visual Studio'daki kod
description: Kullanım C++ Kod Düzenleyicisi'nde Visual Studio biçimlendirme, gitmeniz, anlamak ve kodunuzu yeniden düzenleyin.
ms.date: 05/31/2019
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.openlocfilehash: d4a74608a95df0fdd461f55d26fee97332a66aa8
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741623"
---
# <a name="edit-and-refactor-c-code-in-visual-studio"></a>Düzenleme ve yeniden düzenleme C++ Visual Studio'daki kod

Visual Studio, yazma, yardımcı olacak çeşitli araçlar düzenleyin ve kodunuzu yeniden düzenleme sağlar.

##  <a name="intellisense"></a>IntelliSense

IntelliSense siz yazarken, simgeler ve kod parçacıkları, öneren bir güçlü kod tamamlama aracıdır. C++Visual Studio IntelliSense çalıştıran gerçek zamanlı olarak analiz etme ve önerileri sağlama güncelleştirirken codebase. Daha fazla karakter yazarken önerilen sonuçların listesini daraltır.

![C&#43; &#43; üye listesi açılır](../ide/media/cpp-statement-completion.png)

Bazı simgeleri sonuçları daraltmaya yardımcı olmak için otomatik olarak çıkarılır. Örneğin, bir sınıf nesnesinin üyeleri sınıf dışındaki erişirken, varsayılan veya korumalı üyeler özel üyeleri (bir alt sınıfı bağlamında kök kullanıcı değilseniz) görmek mümkün olmayacaktır. Alttaki düğmeleri kullanarak filtreleme yapabilirsiniz.

Sembol aşağı açılan listeden seçtikten sonra otomatik tamamlama için onunla **sekmesini**, **Enter**, veya diğer işleme karakterlerden birini (varsayılan: {} [ ](). ,:; +-* / % & | ^! =? @#\). Ekleyip karakterleri bu listeden kaldırmak için arama "İçin IntelliSense" içinde **hızlı başlatma** (Ctrl + Q) ve **metin düzenleyicisi > C /C++ > Gelişmiş** seçeneği. **Üye listesi işleme karakterleri** seçeneği, istediğiniz değişiklikleri listesiyle özelleştirmenize olanak sağlar.

**Üye listesi filtre modu** seçeneği denetimleri IntelliSense otomatik tamamlama önerileri ne tür görürsünüz. Varsayılan olarak ayarlanmış **Fuzzy**. Belirsiz arama adlı bir simge varsa *MyAwesomeClass*, "MAC" yazın ve otomatik tamamlama önerilerinizi sınıfı bulun. Belirsiz algoritması sembolleri listede gösterilmesi için karşılaması gereken en az bir eşik ayarlar. **Akıllı** filtreleme, yazdığınızla eşleşen alt dizeler içeren tüm simgeleri görüntüler. **Önek** filtreleme, yazdığınız ile başlayan dizeleri arar.

Hakkında daha fazla bilgi için C++ IntelliSense, bkz: [Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense) ve [yapılandırma bir C++ IntelliSense için proje](/visualstudio/ide/visual-cpp-intellisense-configuration).

## <a name="intellicode"></a>IntelliCode

Intellicode, yapay ZEKA destekli IntelliSense olur. Bunu üst tamamlama listenizin en olası aday yerleştirir. Intellicode öneriler her GitHub üzerinde açık kaynak projeleri 100'den fazla yıldız ile binlerce temel alır. Kodunuzun bağlamı ile birleştirildiğinde tamamlama listesi ortak uygulamaları öne çıkaracak şekilde Uyarlanır.

Yazarken C++, Intellicode yardımcı popüler kitaplıkları gibi kullanırken C++ standart kitaplığı. Kodunuzun bağlamı, en yararlı önerileri ilk sağlamak için kullanılır. Aşağıdaki örnekte, `size` üye işlevi ile kullanılan yaygın olarak `sort` işlevi için sonuç listesinde üstüne kullanıma sunulur.

![C&#43;&#43; IntelliCode](../ide/media/intellicode-cpp.png "C++ IntelliCode")

::: moniker range="vs-2019"

Visual Studio 2019 ' isteğe bağlı olarak Intellicode kullanılabilir  **C++ masaüstü geliştirme** iş yükü. Intellicode etkin olduğundan emin olmak için C++Git **Araçları** > **seçenekleri** > **Intellicode**  >  **Genel** ayarlayıp  **C++ temel modele** için **etkin**.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017'de Intellicode Visual Studio Market'te bir uzantısı olarak kullanılabilir.

::: moniker-end

## <a name="predictive-intellisense-experimental"></a>Tahmine dayalı IntelliSense (Deneysel)

**Tahmine dayalı IntelliSense** IntelliSense açılan listede görüntülenen sonuçların sayısını sınırlamak için bağlamsal tanıma kullanan Deneysel bir özelliğidir. Algoritma türü beklenen türle eşleşen sonuçları gösterir böylece eşleşen geçerlidir. En basit durumda yazarsanız `int x =` ve IntelliSense açılan çağırmak, yalnızca tamsayılar ya da tamsayı döndüren işlevler görürsünüz. Geliştirme aşamasında olduğu için bu özellik varsayılan olarak kapalıdır. Genel simgeler ile en iyi şekilde çalışır; üye işlevleri henüz desteklenmemektedir. "Tahmine dayalı" yazarak içinde açabilirsiniz **hızlı başlatma** veya giderek **Araçları** > **seçenekleri** > **MetinDüzenleyicisi**  >  **C /C++**  > **Deneysel** > **Tahmine dayalı IntelliSense'i etkinleştirme**.

Geçersiz kılınacak **Tahmine dayalı IntelliSense** gösterin uzun basın listesinde **Ctrl + J**. Varsa **Tahmine dayalı IntelliSense** açıktır, çağırma **Ctrl + J** Tahmine dayalı filtre kaldırır. Tuşuna basarak **Ctrl + J** yeniden üye listesinden erişilebilirlik filtre sonuçlarını ilgili olduğunda kaldırır. ([+]) Düğmesinin altındaki açılan listede aynı şeyi yapar IntelliSense **Ctrl + J**. Ne gösterilmekte olduğunu hakkında araç ipucu bilgisini görmek için düğmesinin üzerine getirin.

![C&#43; &#43; Tahmine dayalı IntelliSense](../ide/media/predictive-intellisense-cpp.png "Tahmine dayalı IntelliSense")

Önceki ekran açılır listesi altında birkaç düğme gösterilmektedir. Bunlar, IntelliSense filtre sonuçlarını farklı türleri için etkinleştirin:

- Değişkenler ve sabitler
- İşlevler
- Türler
- Makrolar
- Numaralandırmalar
- Ad Alanları

Yalnızca geçerli IntelliSense oturumunuzu ilgili ise, bir düğme görüntülenir. Genellikle aynı anda tüm düğmeler görmez.

## <a name="template-intellisense"></a>Şablon IntelliSense

Giriş işaretini bir şablon tanımının içinde olduğunda bir **şablon çubuğu** görünen örnek şablon bağımsız değişkenleri için IntelliSense vermenizi sağlar. 

![C&#43; &#43; şablon IntelliSense Show varolan Örneklemeleri](../ide/media/template-intellisense-cpp-1.png "şablon IntelliSense Show Örneklemeleri var")

Tıklayın **<T>** için Genişlet/Daralt simgesi **şablon çubuğu**. Kalem simgesine tıklayın veya çift **şablon çubuğu** açmak için **Düzenle** penceresi. 

![C&#43; &#43; şablon IntelliSense](../ide/media/template-intellisense-cpp-3.png "şablon IntelliSense")

Gerçek zamanlı etkileri görebilmeniz için penceresinde yaptığınız düzenlemeleri doğrudan kaynak kodu için uygulanır. 

Şablon çubuğu otomatik-kodunuzda örneklemeleri göre adayları doldurabilirsiniz. Tıklayarak **eklemek için tüm mevcut Örneklemeleri** şablonun tamamında kod tabanınızın örneklemek için kullanılan tüm somut bağımsız değişkenlerin bir listesi görmek için.

![C&#43; &#43; şablon IntelliSense sonuçları listesinde](../ide/media/template-intellisense-cpp-2.png "şablon IntelliSense sonuçları listesi")

Düzenleyici altındaki bir pencere bağımsız değişkenlerinden neler başlatılmalı ve her örneklemesi bulunduğu gösterir.

![C&#43; &#43; şablon IntelliSense örnekleme eşlemesi](../ide/media/template-intellisense-cpp-4.png "şablon IntelliSense örnekleme eşlemesi")

**Şablon çubuğu** bilgileri kullanıcıya özel kabul edilir. .Vs klasöründeki ve kaynak denetimine teslim edilmemiş.

##  <a name="error-squiggles-and-quick-fixes"></a>Hata ilişkilendirmelerini ve hızlı düzeltmeler

Düzenleyiciden kodunuz ile ilgili sorunlar algılarsa, sorun altında renkli dalgalı çizgiler ekleyeceksiniz. Kırmızı dalgalı çizgiler derlenemeyecektir kodu belirtin. Yeşil dalgalı çizgiler diğer tür yine de ciddi olabilecek olabilecek sorunları gösterir. Açabileceğiniz **hata listesi** sorunlar hakkında daha fazla bilgi almak için penceresi.

Bazı hata türleri için de gibi ortak desenleri, kodlama Düzenleyicisi sunacaktır bir **hızlı düzeltme** beliren bir ampul biçiminde dalgalı çizgi gelin. Önerileri görmek için aşağı oka tıklayın. 

Aşağıdaki örnekte, bir `vector` olduğu bildirildi ancak Düzenleyici gerekli üstbilgi dosyasını dahil sağlamadığından müşteri tanım bulundu:

![C&#43; &#43; hızlı düzeltme](../ide/media/quick-fix-for-header-cpp.png " C++ hızlı düzeltme")

Düzenleyici, bazı düzenleme olanaklarını hızlı düzeltmeler de sunar. Örneğin, bir sınıfta bir üstbilgi dosyası bildirirseniz, ayrı .cpp dosyasında bir tanımı oluşturmak Visual Studio sunacaktır. 

![C&#43; &#43; hızlı düzeltme](../ide/media/quick-fix.png " C++ hızlı düzeltme")

## <a name="change-tracking"></a>Change tracking

Bir dosyaya bir değişiklik yaptığınızda, sarı çubuk kaydedilmemiş değişiklikler yapıldığını belirtmek için soldaki bölmede görünür. Dosyayı kaydettiğinizde, çubuk yeşile döner. Belge Düzenleyicisi'nde açık olduğu sürece, yeşil veya sarı çubukları korunur. En son belge açtığınızdan bu yana yapılan değişiklikler temsil ederler.

![C&#43; &#43; değişiklik izleme](../ide/media/change-tracking-cpp.png "değişiklik izleme")

## <a name="move-code"></a>Kodu Taşı

Kod satırlarını yukarı ve aşağı seçip Alt tuşunu basılı tutup tuşuna basarak taşıyabilirsiniz **yukarı/aşağı** ok tuşları.

##  <a name="insert-snippets"></a>Kod parçacıkları ekleme

Bir kod parçacığı, kaynak kodu önceden tanımlanmış bir parçasıdır. Bir kod parçacığı Ekle ya da seçili metni parçacığıyla çevreleyen seçili metni veya tek bir nokta üzerinde sağ tıklayın. Seçili deyimiyle kapsamak için üç adım aşağıdaki çizimde bir for döngüsü. Son görüntüde sarı vurgular ile sekmesindeki anahtara erişim düzenlenebilir alanlardır. Daha fazla bilgi için [kod parçacıkları](/visualstudio/ide/code-snippets).

![C&#43; &#43; kod parçacığı Ekle bırak&#45;aşağı](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

##  <a name="add-class"></a>Sınıf ekleme

Yeni bir sınıf ekleyin **proje** menüsünde, bağlam menüsünden veya **Çözüm Gezgini**:

![C'de yeni sınıf ekleyin&#43;&#43;](../ide/media/vs2017-add-class.png "vs2015_cpp_add_class")

Sınıf Sihirbazı, değiştirin veya varolan bir sınıf incelemek için de kullanabilirsiniz.

![C&#43; &#43; sınıf Sihirbazı](../ide/media/vs2017-class-wizard.png)

Daha fazla bilgi için [işlevsellik ekleme kodu sihirbazları (C++) ile](../ide/adding-functionality-with-code-wizards-cpp.md).

##  <a name="refactoring"></a>Yeniden Düzenle

Yeniden düzenlemeler tıklayarak veya, hızlı eylem bağlam menüsü altında kullanılabilir bir [ampul](/visualstudio/ide/perform-quick-actions-with-light-bulbs) Düzenleyicisi.  Bazı de bulunan **Düzenle > yeniden düzenleme** menüsü.  Bu özellikler şunlardır:

* [Yeniden Adlandır](refactoring/rename.md)
* [İşlevi Ayıkla](refactoring/extract-function.md)
* [Saf Sanalları Uygula](refactoring/implement-pure-virtuals.md)
* [Bildirim / Tanım Oluştur](refactoring/create-declaration-definition.md)
* [Move İşleminin Tanımı](refactoring/move-definition-location.md)
* [Ham Dize Sabit Değerine Dönüştür](refactoring/convert-to-raw-string-literal.md)
* [İmzayı Değiştir](refactoring/change-signature.md)

## <a name="code-style-enforcement-with-clangformat-and-editorconfig"></a>ClangFormat ve EditorConfig ile kod stili zorlama

Visual Studio 2017 ve üzeri için yerleşik destek ile birlikte gelen [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html), popüler bir kod biçimlendirme yardımcı programı için C++ Clang/LLVM göre. "ClangFormat" denetimine yazdığınız [hızlı başlatma](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) ortak şu biçimlerden birini kullanmak üzere ayarlamak için:

- LLVM
- Google
- Chromium
- Mozilla
- WebKit
- Visual Studio

Tüm kod dosyaları için aynı düzeyde veya aşağıda özel kuralları uygulamak için kendi .clang-format veya _clang-format dosyası de sağlayabilirsiniz.

Dosyaları kaynak denetimine kolayca paylaşılabilir olduğundan tüm geliştirme ekibinizde kodlama kurallarını uygulayabilirsiniz.

![C&#43; &#43; Clang biçimi](../ide/media/clang-format-cpp.png "Clang biçimi")

Visual Studio 2017 ve sonrasında de destekler [EditorConfig](https://editorconfig.org/), benzer şekilde çalışır. ClangFormat, ancak sahip EditorConfig özgü kuralları dahil olmak üzere, daha fazla bir stil seçeneği C++. İle **EditorConfig**, oluşturduğunuz **.editorconfig** dosyaları ve bunları farklı klasörlerde yerleştirin, bu klasörleri ve bunların alt klasörlerinde kod stilleri belirtmek için kod tabanı. Bir **.editorconfig** diğer tüm dosya yerine geçen **.editorconfig** dosyaları üst klasörlerinde ve herhangi bir biçimlendirme aracılığıyla yapılandırılan ayarları geçersiz kılar **Araçları**  >  **Seçenekleri**. Sekmeleri boşluk, girinti boyutu ve diğer karşılaştırması için kurallar ayarlayabilirsiniz. Daha fazla bilgi için [EditorConfig ile taşınabilir, özel düzenleyici ayarları oluşturma](/visualstudio/ide/create-portable-custom-editor-options).

## <a name="other-formatting-options"></a>Diğer biçimlendirme seçenekleri

**Hızlı başlatma** en hızlı yolu, bir ayar veya aracı bulmak için arama kutusu sağlar. Bu, ana menüsünde yer alır. Yazmaya başlayın ve otomatik tamamlama listesi, sonuçları filtre uygular.

![Visual Studio hızlı başlatma](../ide/media/vs2015_cpp_quick_launch.png "hızlı başlatma")

Biçimlendirme seçenekleri girintileri, küme ayracı tamamlama ve renklendirme gibi ayarlamak için şunu yazın "C++ biçimlendirme" içine **hızlı başlatma** penceresi.

![C++, biçimlendirme seçenekleri](media/cpp-formatting-options.png)

Diğer biçimlendirme seçenekleri altında bulunan **Düzenle** > **Gelişmiş** da ana menüde.

![C++Gelişmiş Düzenleme Seçenekleri](media/edit-advanced-cpp.png)

Etkinleştirme ve yapılandırma seçenekleri C++-belirli bir düzenleme özellikleri altında bulunur **Araçları** > **seçenekleri** > **metin düzenleyici**  >  **C /C++** . Hangi seçeneği ayarlamak istediğiniz seçtikten sonra daha fazla yardım tuşuna basarak alabilirsiniz **F1** iletişim kutusu, odakta olduğunda. Biçimlendirme seçenekleri genel kodunu yazın `Editor C++` içine **hızlı başlatma**.

![Visual Studio Araçlar > Seçenekler](../ide/media/tools-options.png "Düzenleyici Seçenekleri")

Visual Studio, gelecek bir sürümünde bulunmayabilir veya olabilir, Deneysel özellikler bulunur [metin düzenleyicisi C++ Deneysel](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) iletişim. Visual Studio 2017 ve üzeri etkinleştirebilirsiniz **Tahmine dayalı IntelliSense** bu iletişim kutusunda.

## <a name="see-also"></a>Ayrıca Bkz.

[Okumanız ve anlamanız C++ kod](read-and-understand-code-cpp.md)</br>
[Git, C++ Visual Studio'da temel kod](navigate-code-cpp.md)</br>
[Canlı paylaşım için işbirliği yapınC++](live-share-cpp.md)