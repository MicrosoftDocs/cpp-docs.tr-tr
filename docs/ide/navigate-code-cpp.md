---
title: Gezinme C++ Visual Studio'daki kod
description: Geçici olarak gezinmek için Visual Studio'da çeşitli araçlar kullanın, C++ kod tabanı.
ms.date: 05/28/2019
ms.openlocfilehash: c2d3a1aa4a26cb820ff4a1e87d6eae88b1b8e739
ms.sourcegitcommit: 96f48079cdc402e4c2c1578d1f1eed4846a484dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2019
ms.locfileid: "67576520"
---
# <a name="navigate-c-code-in-visual-studio"></a>Gezinme C++ Visual Studio'daki kod

Visual Studio takımının bir geçici olarak gezinmek için kullanabileceğiniz araçlar sağlar, hızlı ve verimli bir şekilde kod tabanı.

## <a name="open-an-included-file"></a>Eklenen bir dosyayı açma

Sağ bir `#include` yönerge ve select **belgeye Git**. Ya da seçin **F12** dosyayı açmak için bu satırı üzerinden imleç.

![C&#43; &#43; belgeye Git menü seçeneği](../ide/media/go-to-document.png "belge gidin")

## <a name="toggle-headercode-file"></a>Başlık/kod dosyası Aç/Kapat

Karşılık gelen kaynak dosyası ve üstbilgi dosyası arasında geçiş yapabilirsiniz. Dosya ve seçme içinde herhangi bir yeri sağ **geçiş başlık/kod dosyası**. Ya da seçebilirsiniz **Ctrl + K**, **Ctrl + O**.

## <a name="go-to-definitiondeclaration"></a>Tanımı/bildirimine gidin

Düzenleyicide sağ tıklatıp seçerek bir kod simgesi tanımına gidebilirsiniz **tanıma**, seçerek veya **F12**. Bir bildirimi için benzer şekilde bağlam menüsünü açmak için sağ tıklayarak veya seçerek gezinebileceğiniz **Ctrl + F12**.

![C&#43; &#43; Tanıma Git](../ide/media/go-to-def.png "Tanıma Git")

## <a name="go-to"></a>Git

**Git** sağlayan her filtreleriyle belirli bir sonuç türünü temel özellikleri belirtin Gezinti kümesine başvuruyor. 

Açabileceğiniz **Git** ile **Ctrl +** . Bu eylem, düzenlediğiniz belge üzerinde bir arama kutusu oluşturur.

![C&#43; &#43; Git](../ide/media/go-to-cpp.png "gidin")

**Git** bu arama filtreleri içerir:

- **Satıra Git** (**Ctrl + g'tuşlarını**): Hızlı bir şekilde, geçerli belgede farklı bir satıra atla.
- **Tümüne Git** (**Ctrl +** ) veya (**Ctrl + T**): Arama sonuçları izleyen her şeyi içerir.
- **Dosyaya gidin** (**Ctrl 1, F**): Çözümünüzde dosyaları arayın.
- **Tür Git** (**Ctrl 1, T**): Arama sonuçlarını şunlardır:
  - Sınıflar, yapılar ve sabit listeleri.
  - Arabirimlerde ve temsilcilerde (yalnızca yönetilen kod).
- **Üye Git** (**Ctrl 1, M**): Arama sonuçlarını şunlardır:
  - Genel değişkenler ve genel işlevler.
  - Sınıf üyesi değişkenleri ve üye işlevleri.
  - Sabitler.
  - Sabit listesi öğeleri.
  - Özellikler ve olaylar.
- **Sembol Git** (**Ctrl 1, S**): Arama sonuçlarını şunlardır:
  - Üye sonuç türleri Git ve Git.
  - Tüm kalan C++ makroları içeren dil yapıları.

İlk çağırdığınızda **Git** ile **Ctrl +** , **tümüne Git** olduğu (filtreler arama sonuçları) etkinleştirildi. Ardından, arama kutusuna düğmeleri kullanarak istediğiniz filtreyi seçebilirsiniz. İlgili olarak klavye kısayolunu kullanarak belirli bir filtre çağırabilirsiniz. Bu durumda açılır yapılması **Git** arama kutusuyla seçilmiş Bu filtre. Tüm klavye kısayollarını yapılandırılabilir özelliktedir.

Bir metin filtre uygulamak için arama sorgunuz filtrenin karaktere karşılık gelen bir boşluk ile başlatın. (**Satıra Git** isteğe bağlı olarak alan atlayabilirsiniz.) Bu metin filtreler mevcuttur:

- Tümüne Git: (metin filtre yok)
- Satır numarası gidin::
- Dosyaya gidin: f
- Tür gidin: t
- Üye gidin: m
- Sembol gidin: #

Aşağıdaki örnek, sonuçları gösterir. bir *dosyaya Git* "f" filtresini kullanarak işlemi:

![C&#43; &#43; menüsüne gidin](../ide/media/vs2017-go-to-results.png "menüsüne gidin")

Metin filtreleri listesini görmek için şunu yazın bir? ardından bir boşluk. Da erişebilirsiniz **Git** ile komutları **Düzenle** menüsü. Kendinize ana anımsatmak için başka bir yolu budur **Git** klavye kısayolları.

![C&#43; &#43; menüsüne gidin](../ide/media/go-to-menu-cpp.png "menüsüne gidin")

## <a name="find-or-find-in-files"></a>Bulmak veya dosyalarda Bul

Her şey için bir metin arama çözümünüzü ile çalıştırabileceğiniz **Bul** (**Ctrl + F**) veya **dosyalarda Bul** (**Ctrl + SHIFT + F**).

**Bulma** seçimi, geçerli belgede, bütün açık belgeleri, geçerli proje veya çözümün tamamını kapsamlandırılabilir. Normal ifadeler ve düz metin kullanabilirsiniz. Ayrıca, tüm eşleşmeleri IDE içinde otomatik olarak vurgular.

![C&#43; &#43; Bul](../ide/media/find-cpp.png "bulun")

**Dosyalarda Bul** daha güçlü bir sürümü **Bul** sonuçları görüntüler **sonuçları Bul** penceresi. Dış kod bağımlılıklarını, dosya türleri tarafından filtre ve daha fazla arama yapabilirsiniz. 

![C&#43; &#43; dosyalarda Bul](../ide/media/find-in-files-cpp.png "dosyalarda Bul")

Organize edebilirsiniz **dosyalarda Bul** iki windows sonuçlanır. Birden çok arama sonuçlarından birlikte ekleyebilirsiniz. Dosyayı bu konuma gitmek için bir sonuç seçin.

![C&#43; &#43; dosyalarda Bul](../ide/media/vs2017-find-in-files-results.png "dosyalarda Bul")

Daha fazla bilgi için [dosyalarda Bul](/visualstudio/ide/find-in-files) Visual Studio belgelerinde.

## <a name="find-all-references"></a>Tüm Başvuruları Bul

Kod tabanınızdaki bir simgenin tüm kullanımları bulmak için giriş işaretini veya sembol, sağ tıklayın ve ardından hemen sonra yerleştirin **tüm başvuruları Bul**. Filtre, sıralama veya birçok farklı şekilde sonuçları gruplandırabilirsiniz. Sonuçları artımlı olarak doldurun. Bunlar okur veya yazar çözümünüzü aksine, sistem üstbilgileri veya diğer kitaplıkları neler olacağıyla yardımcı olması olarak sınıflandırılmış.

![C&#43; &#43; tüm başvuruları Bul](../ide/media/find-all-references-results-cpp.png "tüm başvuruları Bul")

Sonuçlar aşağıdaki kategorilere göre gruplandırma:

- Proje sonra tanım
- Yalnızca tanım
- Önce tanım sonra proje
- Tanım sonra yol
- Tanım, proje ve sonra yol

 #### <a name="filter-results"></a>Sonuçları filtreleme

Sonuçları filtrelemek için bir sütun gelin ve açılan filtreleme simgesini seçin. Sonuçları görmek için istemeyebilirsiniz dize ve yorum başvuruları gibi şeyleri gizlemek için ilk sütunundaki filtre uygulayabilirsiniz.

![C&#43; &#43; filtreler tüm başvuruları Bul](../ide/media/find-all-references-filters-cpp.png "filtreler tüm başvuruları Bul")

- **Onaylanmış sonuçları**: Gerçek kod başvurularını Aranan sembol. Örneğin, bir üye işlev için arama adlı `Size` yapılan tüm başvurular döndürür `Size` tanımlayan sınıf kapsamı eşleşen `Size`.

- **Sonuçları disconfirmed**: Adıyla eşleşir, ancak gerçek aradığınız sembol başvuruları olmayan sembolleri gösterir çünkü bu filtre varsayılan olarak kapalıdır. Örneğin, her adında bir üye işlevi tanımlayan iki sınıfınız varsa `Size`, ve arama için çalıştırma `Size` bir başvurudan bir nesne üzerinde `Class1`, yönelik tüm başvuruları `Size` gelen `Class2` disconfirmed olarak görünür.

- **İşlenmemiş sonuçları**: **Tüm başvuruları Bul** işlemleri üzerinde tamamlanması zaman alabilir büyük sonuçlar listesinden buraya "İşlenmemiş" sonuçları gösterecek şekilde çıkabilirsiniz. İşlenmemiş sonuçlar Aranan simgenin adını eşleşen ancak henüz gerçek kod başvurularını onaylanmış henüz. Daha hızlı sonuçlar almak için bu filtreyi kapatabilirsiniz. Yalnızca bazı sonuçları gerçek başvuruları olmayabileceğini unutmayın.

 #### <a name="sort-results"></a>Sonuçları sıralama

Bu sütun seçerek herhangi bir sütuna göre sonuçları sıralayabilirsiniz. Artan veya azalan sütunu tekrar seçerek arasında değiştirebilir.

## <a name="navigation-bar"></a>Gezinti Çubuğu

Bir dosyadaki veya üyeleri kullanarak yazmak için bir tür tanımı gidebilirsiniz **gezinti çubuğu** Düzenleyicisi penceresinin üzerinde olmasıdır.

![C&#43; &#43; gezinti çubuğu](../ide/media/navbar-cpp.png "gezinti çubuğu")

## <a name="see-also"></a>Ayrıca bkz.

- [Okumanız ve anlamanız C++ kod](read-and-understand-code-cpp.md)</br>
- [Düzenleme ve yeniden düzenleme C++ kod](read-and-understand-code-cpp.md)</br>
- [Canlı paylaşım için işbirliği yapınC++](live-share-cpp.md)
