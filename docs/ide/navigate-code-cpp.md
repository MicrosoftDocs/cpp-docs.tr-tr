---
title: Visual C++ Studio 'da koda gitme
description: Kod tabanınızın C++ etrafında gezinmek Için Visual Studio 'daki çeşitli araçları kullanın.
ms.date: 05/28/2019
ms.openlocfilehash: 0877fe64e913ab394d9605b9ff0b9825febca793
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446647"
---
# <a name="navigate-c-code-in-visual-studio"></a>Visual C++ Studio 'da koda gitme

Visual Studio, kod tabanınızda hızlı ve verimli bir şekilde gezinmek için kullanabileceğiniz bir araç paketi sağlar.

## <a name="open-an-included-file"></a>Dahil edilen bir dosyayı açma

`#include` yönergesine sağ tıklayın ve **belgeye git**' i seçin. Ya da dosyayı açmak için bu satırın üzerine imleci ile **F12** ' i seçin.

![C&#43; &#43; belgeye git menü seçeneği](../ide/media/go-to-document.png "Belgeye git")

## <a name="toggle-headercode-file"></a>Üst bilgi/kod dosyası değiştirme

Üst bilgi dosyası ile buna karşılık gelen kaynak dosyası arasında geçiş yapabilirsiniz. Dosyanızda herhangi bir yere sağ tıklayın ve **başlık/kod dosyasını aç**' ı seçin. Ya da **CTRL + K**, **CTRL + O**tuşlarına da seçebilirsiniz.

## <a name="go-to-definitiondeclaration"></a>Tanıma/bildirime git

Düzenleyicide sağ tıklayıp **Tanıma Git**' i seçerek veya **F12**' i seçerek bir kod sembolünün tanımına gidebilirsiniz. Bağlam menüsünü açmak için sağ tıklayarak veya **CTRL + F12**' i seçerek bir bildirime gidebilirsiniz.

![C&#43; &#43; tanıma git](../ide/media/go-to-def.png "Tanıma Git")

## <a name="go-to"></a>Git

**Git** , her birinin belirttiğiniz filtrelere göre belirli bir sonuç türünü sağlayan bir dizi gezinti özelliği anlamına gelir. 

**Git** **' i CTRL + '** de açabilirsiniz. Bu eylem, düzenlemekte olduğunuz belge üzerinde bir arama kutusu oluşturur.

![C&#43; &#43; 'ye git](../ide/media/go-to-cpp.png "Git")

Bu arama filtrelerini içerir **öğesine git** :

- **Satıra git** (**CTRL + G**): geçerli belgenizdeki farklı bir satıra hızlıca atlayın.
- **Tümüne git** (**CTRL +,** ) veya (**CTRL + T**): arama sonuçları, izleyen her şeyi içerir.
- **Dosyaya git** (**CTRL 1, F**): çözümünüzdeki dosyaları arayın.
- **Türe git** (**CTRL 1, T**): arama sonuçları şunları içerir:
  - Sınıflar, yapılar ve Numaralandırmalar.
  - Arabirimler ve Temsilciler (yalnızca yönetilen kod).
- **Üyeye git** (**CTRL 1, e**): arama sonuçları şunları içerir:
  - Genel değişkenler ve genel işlevler.
  - Sınıf üyesi değişkenleri ve üye işlevleri.
  - Lerde.
  - Enum öğeleri.
  - Özellikler ve olaylar.
- **Simgeye git** (**CTRL 1, S**): arama sonuçları şunları içerir:
  - Türlere git ve üyelere git sonuçları.
  - Makrolar içeren C++ tüm kalan dil yapıları.

**CTRL +** ile **Git** ' i Ilk kez çağırdığınızda, **tümüne git** etkinleştirilir (arama sonuçlarında filtre yoktur). Ardından, arama kutusunun yakınında bulunan düğmeleri kullanarak istediğiniz filtreyi seçebilirsiniz. Karşılık gelen klavye kısayolunu kullanarak belirli bir filtreyi çağırabilirsiniz. Bunun yapılması, bu filtrenin önceden seçilmiş olduğu arama kutusuna **Git** ' i açar. Tüm klavye kısayolları yapılandırılabilir.

Bir metin filtresi uygulamak için, arama sorgunuzu filtrenin karşılık gelen karakteriyle ve ardından bir boşluk ile başlatın. (**Satıra git** , isteğe bağlı olarak boşluğu atlayabilir.) Bu metin filtreleri kullanılabilir:

- Tümüne git: (metin filtresi yok)
- Satır numarasına git::
- Dosyaya git: f
- Türe git: t
- Üyeye git: e
- Simgeye git: #

Aşağıdaki örnek, "f" filtresi kullanılarak bir *Dosya go* işleminin sonuçlarını gösterir:

![C&#43; &#43; Git menüsü](../ide/media/vs2017-go-to-results.png "Menüye git")

Metin filtrelerinin listesini görmek için şunu yazın: ardından bir boşluk gelir. Ayrıca, **düzenleme** menüsüyle komutlara **Git** komutlarına de erişebilirsiniz. Bu, kendinizi ana klavye kısayollarına **anımsatmak için başka** bir yoldur.

![C&#43; &#43; Git menüsü](../ide/media/go-to-menu-cpp.png "Menüye git")

## <a name="find-or-find-in-files"></a>Dosyaları bulma veya bulma

Çözümünüzde **bul** (**Ctrl + f**) veya **dosyalarda bul** (**Ctrl + Shift + f**) ile çözümünüzdeki herhangi bir şey için bir metin araması çalıştırabilirsiniz.

**Bul** , seçim, geçerli belge, tüm açık belgeler, geçerli proje ya da tüm çözüm kapsamına eklenebilir. Normal ifadeler ve düz metin kullanabilirsiniz. Ayrıca, IDE 'de tüm eşleşmeleri otomatik olarak vurgular.

![C&#43; &#43; bul](../ide/media/find-cpp.png "Bul")

**Dosyalarda bul** , sonuçları **bul** penceresinde sonuçları görüntüleyen bir **bul** 'un daha güçlü bir sürümüdür. Dış kod bağımlılıklarını arayabilir, dosya türlerine göre filtreleyebilirsiniz ve daha fazlasını yapabilirsiniz. 

![Dosyalarda&#43; &#43; C bul](../ide/media/find-in-files-cpp.png "Dosyalarda Bul")

**Dosya bulma** sonuçlarını iki pencere ile düzenleyebilirsiniz. Birden çok aramadan sonuçları bir araya getirebilirsiniz. Dosyadaki bu konuma gitmek için bir sonuç seçin.

![Dosyalarda&#43; &#43; C bul](../ide/media/vs2017-find-in-files-results.png "Dosyalarda Bul")

Daha fazla bilgi için bkz. Visual Studio belgelerindeki [dosyalarda bulma](/visualstudio/ide/find-in-files) .

## <a name="find-all-references"></a>Tüm Başvuruları Bul

Kod tabanınızdaki bir sembolün tüm kullanımlarını bulmak için, giriş işaretini simgenin içine veya hemen arkasına yerleştirin, sağ tıklayın ve ardından **tüm başvuruları bul**' u seçin. Sonuçları birçok farklı yolla filtreleyebilir, sıralayabilir veya gruplandırabilirsiniz. Sonuçlar artımlı olarak doldurulur. Bunlar, sistem üst bilgileri veya diğer kitaplıkların aksine, çözümünüzde neler olduğunu görmenizi sağlayacak okuma veya yazma olarak sınıflandırılmaktadır.

![C&#43; &#43; tüm başvuruları bul](../ide/media/find-all-references-results-cpp.png "Tüm başvuruları Bul")

Sonuçları aşağıdaki kategorilere göre gruplandırabilirsiniz:

- Proje sonra tanım
- Yalnızca tanım
- Tanım sonra proje
- Tanım sonra yol
- Tanım, proje sonra yol

#### <a name="filter-results"></a>Sonuçları filtreleme

Sonuçları filtrelemek için bir sütunun üzerine gelin ve açılan filtre simgesini seçin. , Görmek istemediğiniz dize ve açıklama başvuruları gibi şeyleri gizlemek için ilk sütundan sonuçları filtreleyebilirsiniz.

![C&#43; &#43; tüm başvuruları bul filtreleri](../ide/media/find-all-references-filters-cpp.png "Tüm başvuru filtrelerini bul")

- **Onaylanan sonuçlar**: gerçek kod, aranmakta olan simgeye başvurur. Örneğin, `Size` adlı bir üye işlevi aramak, `Size`tanımlayan sınıfın kapsamıyla eşleşen `Size` tüm başvuruları döndürür.

- **Onaylanan sonuçlar**: Bu filtre varsayılan olarak kapalıdır çünkü adı eşleşen sembolleri gösterir, ancak Aradığınız simgeye gerçek başvurulardır. Örneğin, her biri `Size`adlı bir üye işlevi tanımladıysanız ve bir `Class1`nesnesinden bir başvuru üzerinde `Size` için bir arama çalıştırırsanız, `Class2` `Size` yapılan tüm başvurular onaylanmamış olarak görünür.

- **İşlenmemiş sonuçlar**: **tüm başvuruları bul** , daha büyük kod tabanlarında tamamlanması zaman alabilir, bu nedenle sonuçlar listesi burada "işlenmemiş" sonuçları gösterir. İşlenmemiş sonuçlar, aranmakta olan sembolün adıyla eşleşir ancak henüz gerçek kod başvuruları onaylanmamıştır. Daha hızlı sonuçlar elde etmek için bu filtreyi açabilirsiniz. Yalnızca bazı sonuçların fiili başvurular olabileceğini unutmayın.

#### <a name="sort-results"></a>Sonuçları sıralama

Bu sütunu seçerek sonuçları herhangi bir sütuna göre sıralayabilirsiniz. Sütunu yeniden seçerek artan veya azalan sırada takas edebilirsiniz.

## <a name="navigation-bar"></a>Gezinti Çubuğu

Düzenleyici penceresinin üzerindeki **Gezinti çubuğunu** kullanarak bir dosyadaki bir türün tanımına veya üye türüne gidebilirsiniz.

![C&#43; &#43; gezinti çubuğu](../ide/media/navbar-cpp.png "Gezinti Çubuğu")

## <a name="see-also"></a>Ayrıca bkz.

- [Kodu okuyun ve C++ anlayın](read-and-understand-code-cpp.md)</br>
- [Kodu düzenleme ve C++ yeniden düzenleme](read-and-understand-code-cpp.md)</br>
- [İçin Live Share işbirliği yapınC++](live-share-cpp.md)
