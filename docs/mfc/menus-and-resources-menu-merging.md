---
title: 'Menüler ve Kaynaklar: Menü Birleştirme'
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
ms.openlocfilehash: 03d27443f90634b5d787eee25acc951d24178f42
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626219"
---
# <a name="menus-and-resources-menu-merging"></a>Menüler ve Kaynaklar: Menü Birleştirme

Bu makalede, OLE belge uygulamalarının görsel düzenlemesini ve yerinde etkinleştirmeyi doğru şekilde işlemesi için gereken adımlar ayrıntılı olarak anlatılmaktadır. Yerinde etkinleştirme, hem kapsayıcı hem de sunucu (bileşen) uygulamaları için bir zorluk doğurur. Kullanıcı aynı çerçeve penceresinde (kapsayıcı belge bağlamı içinde) kalır, ancak aslında başka bir uygulama (sunucu) çalıştırıyor. Bu, kapsayıcının kaynakları ve sunucu uygulamaları arasında eşgüdüm gerektirir.

Bu makalede ele alınan konular şunları içerir:

- [Menü düzenleri](#_core_menu_layouts)

- [Araç çubukları ve durum çubukları](#_core_toolbars_and_status_bars)

## <a name="menu-layouts"></a><a name="_core_menu_layouts"></a>Menü düzenleri

İlk adım menü düzenlerini koordine etmek için kullanılır. Kapsayıcı uygulamalar yalnızca katıştırılmış öğeler etkinken kullanılacak yeni bir menü oluşturmamalıdır. En azından bu menü, listelenen sırayla aşağıdakilerden birini içermelidir:

1. Dosya menüsü, dosyalar açıkken kullanılan ile aynıdır. (Genellikle başka bir menü öğesi bir sonraki öğeden önce yerleştirilmez.)

1. Birbirini izleyen iki ayırıcı.

1. Dosyalar açık olduğunda kullanılan bir pencere menüsü (yalnızca bir MDI uygulamasında kapsayıcı uygulama ise) ile aynıdır. Bazı uygulamalarda, bu gruba ait olan seçenekler menüsü gibi başka menüler olabilir, bu da eklenmiş bir öğe etkin olduğunda menüde kalır.

    > [!NOTE]
    >  Yakınlaştırma gibi kapsayıcı belge görünümünü etkileyen başka menüler de olabilir. Bu kapsayıcı menüleri, bu menü kaynağındaki iki ayırıcı arasında görünür.

Sunucu (bileşen) uygulamaları, özellikle de yerinde etkinleştirme için yeni bir menü oluşturmamalıdır. Dosyalar açık olduğunda, ancak veri yerine sunucu belgesini işleyen dosya ve pencere gibi menü öğeleri olmadan kullanılan menü gibi olmalıdır. Genellikle, bu menü aşağıdakilerden oluşur:

1. Dosyalar açıkken kullanılan ile aynı düzenleme menüsü.

1. Ayırıcı.

1. Karalama örnek uygulamasındaki kalem menüsü gibi nesne düzenleyici menüleri.

1. Ayırıcı.

1. Yardım menüsü.

Bir örnek için, bir kapsayıcı ve sunucu için bazı örnek yerinde menülerin düzenine göz atın. Her bir menü öğesinin ayrıntıları, örneği daha anlaşılır hale getirmek için kaldırılmıştır. Kapsayıcının yerinde menüsü aşağıdaki girişlere sahiptir:

```
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&File C1"
    MENUITEM SEPARATOR
    POPUP "&Zoom C2"
    MENUITEM SEPARATOR
    POPUP "&Options C3"
    POPUP "&Window C3"
END
```

Ardışık ayırıcılar, sunucu menüsünün ilk bölümünün gitmesi gereken yeri belirtir. Şimdi sunucunun yerinde menüsüne göz atın:

```
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&Edit S1"
    MENUITEM SEPARATOR
    POPUP "&Format S2"
    MENUITEM SEPARATOR
    POPUP "&Help S3"
END
```

Buradaki ayırıcılar, ikinci kapsayıcı menü öğelerinin gideceği yeri belirtir. Bu sunucudaki bir nesne bu kapsayıcı içinde etkin olduğunda ortaya çıkan menü yapısı şuna benzer:

```
BEGIN
    POPUP "&File C1"
    POPUP "&Edit S1"
    POPUP "&Zoom C2"
    POPUP "&Format S2"
    POPUP "&Options C3
    POPUP "&Window C3"
    POPUP "&Help S3"
END
```

Görebileceğiniz gibi, ayırıcılar her bir uygulamanın menüsünün farklı gruplarıyla değiştirilmiştir.

Yerinde menüsüyle ilişkili Hızlandırıcı tabloları da sunucu uygulaması tarafından sağlanmalıdır. Kapsayıcı bunları kendi Hızlandırıcı tablolarına katacaktır.

Eklenmiş bir öğe yerinde etkinleştirildiğinde, çerçeve yerinde menüsünü yükler. Daha sonra sunucu uygulamasını yerinde etkinleştirme için sunucu uygulamasına sorar ve ayırıcıların bulunduğu yere ekler. Menülerin birleşme şekli aşağıda gösterilmiştir. Dosya ve pencere yerleşimi üzerinde çalışma için kapsayıcılardan menüler alır ve sunucudan öğe için çalışma için menüler alırsınız.

## <a name="toolbars-and-status-bars"></a><a name="_core_toolbars_and_status_bars"></a>Araç çubukları ve durum çubukları

Sunucu uygulamaları yeni bir araç çubuğu oluşturmalı ve bit eşlemini ayrı bir dosyaya depolemelidir. Uygulama Sihirbazı tarafından oluşturulan uygulamalar, bu bit eşlemi ıTOOLBAR adlı bir dosyada depolar. BMP. Yeni araç çubuğu, sunucunuzun öğesi etkinken kapsayıcı uygulamasının araç çubuğunun yerini alır ve normal araç çubuğudur aynı öğeleri içermelidir, ancak dosya ve pencere menülerindeki öğeleri temsil eden simgeleri kaldırır.

Bu araç çubuğu, `COleIPFrameWnd` Uygulama Sihirbazı tarafından sizin için oluşturulan türetilmiş sınıfınıza yüklenir. Durum çubuğu kapsayıcı uygulama tarafından işlenir. Yerinde çerçeve pencerelerinin uygulaması hakkında daha fazla bilgi için bkz. [sunucular: sunucu uygulama](servers-implementing-a-server.md).

## <a name="see-also"></a>Ayrıca bkz.

[Menüler ve kaynaklar (OLE)](menus-and-resources-ole.md)<br/>
[Etkinleştirme](activation-cpp.md)<br/>
[Sunucular](servers.md)<br/>
[Kapsayıcılar](containers.md)
