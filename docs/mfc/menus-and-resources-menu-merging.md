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
ms.openlocfilehash: 149af83bd53b7a97fd264bd6b18701fc9f64ea1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364766"
---
# <a name="menus-and-resources-menu-merging"></a>Menüler ve Kaynaklar: Menü Birleştirme

Bu makalede, Görsel düzenleme ve yerinde etkinleştirme düzgün işlemek için OLE belge uygulamaları için gerekli adımları ayrıntıları. Yerinde etkinleştirme hem kapsayıcı hem de sunucu (bileşen) uygulamaları için zor bir sorun teşkil eder. Kullanıcı aynı çerçeve penceresinde (kapsayıcı belge bağlamında) kalır, ancak aslında başka bir uygulama (sunucu) çalıştırıyor. Bu, kapsayıcı ve sunucu uygulamalarının kaynakları arasında koordinasyon gerektirir.

Bu makalede ele alınan konular şunlardır:

- [Menü Düzenleri](#_core_menu_layouts)

- [Araç Çubukları ve Durum Çubukları](#_core_toolbars_and_status_bars)

## <a name="menu-layouts"></a><a name="_core_menu_layouts"></a>Menü Düzenleri

İlk adım menü düzenlerini koordine etmektir. Kapsayıcı uygulamaları, yalnızca katıştırılmış öğeler yerinde etkinleştirildiğinde kullanılmak üzere yeni bir menü oluşturmalıdır. En azından, bu menü listelenen sırada aşağıdakilerden oluşmalıdır:

1. Dosya menüsü, dosyalar açıkken kullanılanla aynı. (Genellikle bir sonraki öğeden önce başka menü öğesi yerleştirilmesi yoktur.)

1. İki ardışık ayırıcı.

1. Pencere menüsü, dosyalar açıkken kullanılanla aynıdır (yalnızca bir MDI uygulamasındaki kapsayıcı uygulaması ysa). Bazı uygulamalarda, katıştırılmış bir öğe yerinde etkinleştirildiğinde menüde kalan bu gruba ait Seçenekler menüsü gibi başka menüler de olabilir.

    > [!NOTE]
    >  Yakınlaştırma gibi kapsayıcı belgenin görünümünü etkileyen başka menüler de olabilir. Bu kapsayıcı menüleri, bu menü kaynağındaki iki ayırıcı arasında görünür.

Sunucu (bileşen) uygulamaları da yerinde etkinleştirme için özel olarak yeni bir menü oluşturmalıdır. Dosyalar açıkken kullanılan, ancak veri yerine sunucu belgesini manipüle eden Dosya ve Pencere gibi menü öğeleri olmadan kullanılan menü gibi olmalıdır. Genellikle, bu menü aşağıdakilerden oluşur:

1. Dosyalar açıkken kullanılan menüyle aynı menüyü edin.

1. Ayırıcı.

1. Karalama örnek uygulamasındaki Kalem menüsü gibi nesne düzenleme menüleri.

1. Ayırıcı.

1. Yardım menüsü.

Örneğin, kapsayıcı ve sunucu için bazı örnek sıralı menülerin düzenine bakın. Her menü öğesinin ayrıntıları, örneği daha net hale getirmek için kaldırıldı. Kapsayıcının yerinde menüsünde aşağıdaki girişler vardır:

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

Ardışık ayırıcılar, sunucu menüsünün ilk bölümünün nereye gitmesi gerektiğini gösterir. Şimdi sunucunun yerinde menüsüne bakın:

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

Buradaki ayırıcılar, ikinci kapsayıcı menü öğeleri grubunun nereye gitmesi gerektiğini gösterir. Bu sunucudan bir nesne bu kapsayıcının içinde yerinde etkinleştirildiğinde ortaya çıkan menü yapısı aşağıdaki gibi görünür:

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

Gördüğünüz gibi, ayırıcılar her uygulamanın menüsünden farklı gruplarla değiştirildi.

Yerinde menüyle ilişkili hızlandırıcı tabloları da sunucu uygulaması tarafından sağlanmalıdır. Kapsayıcı bunları kendi hızlandırıcı tablolarına dahil edecektir.

Katıştırılmış bir öğe yerinde etkinleştirildiğinde, çerçeve yerinde menü yükler. Daha sonra sunucu uygulamasından menüsünü yerinde etkinleştirme için ister ve ayırıcıların bulunduğu yere ekler. Menüler bu şekilde birleşir. Dosya ve pencere yerleşiminde çalışma için kapsayıcıdan menüler alırsınız ve öğeüzerinde çalışma için sunucudan menüler alırsınız.

## <a name="toolbars-and-status-bars"></a><a name="_core_toolbars_and_status_bars"></a>Araç Çubukları ve Durum Çubukları

Sunucu uygulamaları yeni bir araç çubuğu oluşturmalı ve bit eşlesini ayrı bir dosyada depolamalıdır. Uygulama sihirbazı tarafından oluşturulan uygulamalar bu bit eşlemi ITOOLBAR adlı bir dosyada saklar. Bmp. Sunucunuzun öğesi yerinde etkinleştirildiğinde yeni araç çubuğu kapsayıcı uygulamanın araç çubuğunun yerini alır ve normal araç çubuğunuzla aynı öğeleri içermelidir, ancak Dosya ve Pencere menülerinde öğeleri temsil eden simgeleri kaldırmalı.

Bu araç çubuğu, `COleIPFrameWnd`uygulama sihirbazı tarafından sizin için oluşturulan -türetilmiş sınıfınızda yüklenir. Durum çubuğu kapsayıcı uygulaması tarafından işlenir. Yerinde çerçeve pencerelerin uygulanması hakkında daha fazla bilgi için [bkz.](../mfc/servers-implementing-a-server.md)

## <a name="see-also"></a>Ayrıca bkz.

[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Etkinleştirme](../mfc/activation-cpp.md)<br/>
[Sunucular](../mfc/servers.md)<br/>
[Kapsayıcılar](../mfc/containers.md)
