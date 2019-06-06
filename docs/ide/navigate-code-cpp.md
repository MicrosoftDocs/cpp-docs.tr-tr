---
title: Gezinme C++ Visual Studio'daki kod
description: Geçici olarak gezinmek için Visual Studio'da çeşitli araçlar kullanın, C++ kod tabanı.
ms.date: 05/28/2019
ms.openlocfilehash: 5f01307cc82fb1e61ba6fd0c922ea376279fba8b
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66743386"
---
# <a name="navigate-c-code-in-visual-studio"></a>Gezinme C++ Visual Studio'daki kod

Visual Studio Paketi, geçici olarak gezinmek izin vermek için araçlar sağlar, hızlı ve verimli bir şekilde kod tabanı.

## <a name="open-an-included-file"></a>Eklenen bir dosyayı açma

Sağ tıklayın bir `#include` yönergesi ve **belgeye Git**, veya basın **F12** dosyayı açmak için bu satırı imleci ile.

![C&#43; &#43; belgeye Git menü seçeneği](../ide/media/go-to-document.png "belge gidin")

## <a name="toggle-headercode-file"></a>Başlık/kod dosyası Aç/Kapat

Dosyanızda herhangi bir yere sağ tıklayıp seçerek, ilgili kaynak dosyadan bir üst bilgi dosyası arasında geçebilirsiniz **geçiş başlık / kod dosyası** veya basarak **Ctrl + K, Ctrl + O**.

## <a name="go-to-definitiondeclaration"></a>Tanımı/bildirimine gidin

Düzenleyicide sağ tıklayıp seçerek bir kod simgesi tanımına gidebilirsiniz **tanıma**, ya basarak **F12**. Bir bildirimi için benzer şekilde tuşuna basarak veya sağ tıklatın ve bağlam menüsünden gezinebileceğiniz **Ctrl + F12**.

![C&#43; &#43; Tanıma Git](../ide/media/go-to-def.png "Tanıma Git")

## <a name="go-to"></a>Git

**Git** sağlayan her filtreleriyle belirli bir sonuç türünü temel özellikleri belirtin Gezinti kümesine başvuruyor. 

Açabileceğiniz **Git** ile **Ctrl +,** . Bu belgenin düzenlemekte olduğunuz bir arama kutusu oluşturur.

![C&#43; &#43; Git](../ide/media/go-to-cpp.png "gidin")

**Git** bu arama filtreleri içerir:

- **Satıra Git (Ctrl + G)** : hızlı bir şekilde, geçerli belgede farklı bir satıra atla
- **Tümüne Git (Ctrl +,)** veya **(Ctrl + T)** : arama sonuçları aşağıdaki her şeyi içerir
- **Git için dosya (Ctrl 1, F)** : Çözümünüzde dosyaları arayın
- **Git için türü (Ctrl 1, T)** : arama sonuçları içerir:
  - Sınıflar, yapılar, sabit listeleri
  - Arabirimler ve temsilciler (yalnızca yönetilen kod)
- **Git için üye (Ctrl 1, M)** : arama sonuçları içerir:
  - Genel değişkenler ve genel işlevler
  - Sınıf üyesi değişkenleri ve üye işlevleri
  - Sabitler
  - Sabit listesi öğeleri
  - Özellikler ve olaylar
- **Git için Sembol (Ctrl 1, S)** : arama sonuçları içerir:
  - Üyeleri türlerine Git ve Git sonuçları
  - Tüm kalan C++ makroları dahil olmak üzere, dil yapıları

İlk çağırdığınızda **Git** ile **Ctrl +** , **tümüne Git** olduğu (filtreler arama sonuçları) etkinleştirildi. Ardından, arama metin kutusu yakınlarında düğmeleri kullanarak, istenen filtre seçebilirsiniz. İlgili olarak klavye kısayolunu kullanarak belirli bir filtre çağırabilirsiniz. Bu durumda açılır yapılması **gitmek için** önceden seçilen filtre arama kutusu. Tüm klavye kısayollarını yapılandırılabilir özelliktedir.

Bir metin filtre uygulamak için arama sorgunuz filtrenin karaktere karşılık gelen bir boşluk ile başlatın. (**Satıra Git** isteğe bağlı olarak alan atlayabilirsiniz.) Kullanılabilir metin filtreleri şunlardır:

- Tümüne Git: (metin filtre yok)
- Satır numarası gidin::
- Dosyaya gidin: f
- Tür gidin: t
- Üye gidin: m
- Sembol gidin: #

Aşağıdaki örnek, sonuçları gösterir. bir *dosyaya Git* 'f' filtresini kullanarak işlemi:

![C&#43; &#43; menüsüne gidin](../ide/media/vs2017-go-to-results.png "menüsüne gidin")

Metin filtreleri listesini görmek için şunu yazın bir? ardından bir boşluk. Da erişebilirsiniz **Git** ile komutları **Düzenle** menüsü. Bu ana gitmek için klavye kısayolları kendiniz anımsatmak için başka bir yoludur.

![C&#43; &#43; menüsüne gidin](../ide/media/go-to-menu-cpp.png "menüsüne gidin")

## <a name="find--find-in-files"></a>Bul / dosyalarda Bul

Her şey için bir metin arama çözümünüzü ile çalıştırabileceğiniz **Bul (Ctrl + F)** veya **(Ctrl + Shift + F) dosyalarda Bul**.

Bul seçimi, geçerli belgede, bütün açık belgeleri, geçerli proje veya çözümün tamamını sınırlayabilirsiniz. Düz metin yanı sıra normal ifadeler kullanabilirsiniz. Ayrıca, tüm eşleşmeleri IDE içinde otomatik olarak vurgular.

![C&#43; &#43; Bul](../ide/media/find-cpp.png "bulun")

**Dosyalarda Bul** daha güçlü bir sürümü **Bul** sonuçları görüntüler **sonuçları Bul** penceresi. Dış kod bağımlılıklarını, filtre tarafından dosya türleri ve diğer arama yapabilirsiniz. 

![C&#43; &#43; dosyalarda Bul](../ide/media/find-in-files-cpp.png "dosyalarda Bul")

Organize edebilirsiniz **dosyalarda Bul** iki windows sonuçlanır. Birden çok arama sonuçlarından birlikte ekleyebilirsiniz. Bir sonuç dosyayı bu konuma gitmek için tıklayın.

![C&#43; &#43; dosyalarda Bul](../ide/media/vs2017-find-in-files-results.png "dosyalarda Bul")

Daha fazla bilgi için [dosyalarda Bul](/visualstudio/ide/find-in-files) Visual Studio belgelerinde.

## <a name="find-all-references"></a>Tüm Başvuruları Bul

Kod tabanınızdaki bir simgenin tüm kullanımları bulmak için veya sembol hemen sonra giriş işaretinin yerleştirin sonra sağ tıklatın ve seçin **tüm başvuruları Bul**. Filtre, sıralama veya birçok farklı şekilde sonuçları gruplandırabilirsiniz. Sonuçları artımlı olarak doldurun. Bunlar okur veya yazar çözümünüzü aksine, sistem üstbilgileri veya diğer kitaplıkları neler olacağıyla yardımcı olması olarak sınıflandırılır.

![C&#43; &#43; tüm başvuruları Bul](../ide/media/find-all-references-results-cpp.png "tüm başvuruları Bul")

Sonuçlar aşağıdaki kategorilere göre gruplandırma:

- Proje sonra tanım
- Yalnızca tanım
- Önce tanım sonra proje
- Tanım sonra yol
- Tanım, proje ve sonra yol

 #### <a name="filter-results"></a>Sonuçları filtreleme

Sonuçları filtrelemek için bir sütun üzerinde gelin ve açılan filtre simgesine tıklayın. Sonuçları görmek için istemeyebilirsiniz dize ve yorum başvuruları gibi şeyleri gizlemek için ilk sütunundaki filtre uygulayabilirsiniz.

![C&#43; &#43; filtreler tüm başvuruları Bul](../ide/media/find-all-references-filters-cpp.png "filtreler tüm başvuruları Bul")

- **Sonuçlar onaylanmış**: Gerçek kod başvurularını Aranan sembol. Örneğin, bir üye işlev için arama adlı `Size` yapılan tüm başvurular döndürür `Size` sınıfı tanımlayan kapsamını eşleşen `Size`.

- **Sonuçları disconfirmed**: Adıyla eşleşir, ancak gerçek aradığınız sembol başvuruları olmayan sembolleri gösterir çünkü bu filtre varsayılan olarak kapalıdır. Örneğin, her adında bir üye işlevi tanımlayan iki sınıfınız varsa `Size`, ve arama için çalıştırma `Size` bir başvurudan bir nesne üzerinde `Class1`, yönelik tüm başvuruları `Size` gelen `Class2` disconfirmed olarak görünür.

- **İşlenmemiş sonuçları**: **Tüm başvuruları Bul** işlemleri üzerinde tamamlanması zaman alabilir büyük sonuçlar listesinden buraya "İşlenmemiş" sonuçları gösterecek şekilde çıkabilirsiniz. İşlenmemiş sonuçlar Aranan simgenin adını eşleşen ancak gerçek kod başvurularını doğrulanmamıştır. Daha hızlı sonuçlar almak için bu filtreyi kapatabilirsiniz. Yalnızca bazı sonuçları gerçek başvuruları olmayabileceğini unutmayın.

 #### <a name="sort-results"></a>Sonuçları sıralama

Sütun üzerinde tıklayarak sonuçları herhangi bir sütuna göre sıralama yapabilirsiniz. Sütunu yeniden tıklayarak artan/azalan sıra arasında değiştirebilir.

## <a name="navigation-bar"></a>Gezinti Çubuğu

Bir dosyadaki veya üyeleri kullanarak yazmak için bir tür tanımı gidebilirsiniz **gezinti çubuğu** Düzenleyicisi penceresinin üzerinde olmasıdır.

![C&#43; &#43; gezinti çubuğu](../ide/media/navbar-cpp.png "gezinti çubuğu")

## <a name="see-also"></a>Ayrıca Bkz.

[Okumanız ve anlamanız C++ kod](read-and-understand-code-cpp.md)</br>
[Düzenleme ve yeniden düzenleme C++ kod](read-and-understand-code-cpp.md)</br>
[Canlı paylaşım için işbirliği yapınC++](live-share-cpp.md)
