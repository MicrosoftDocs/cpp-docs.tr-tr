---
title: 'Menüler ve kaynaklar: menü birleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f4e76902335477ba507e6f3e7a66c5f862b8543
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418677"
---
# <a name="menus-and-resources-menu-merging"></a>Menüler ve Kaynaklar: Menü Birleştirme

Bu makalede OLE belge uygulamaları ve düzgün şekilde yerinde etkinleştirme görsel düzenleme işlemek gerekli adımları ayrıntılı olarak açıklanmaktadır. Yerinde etkinleştirme (Bileşen) uygulamalarının kapsayıcı hem sunucusu için bir sınama oluşturur. Kullanıcı (kapsayıcı belge bağlamında) aynı çerçeve penceresi içinde kalır, ancak başka bir uygulama (sunucu) gerçekte çalışıyor. Bu, kapsayıcı hem de sunucu uygulamalarına kaynaklar arasında koordinasyon gereksinimini olabildiğince gerektirir.

Bu makalede ele alınan konular:

- [Menü düzenlerini](#_core_menu_layouts)

- [Araç çubuklarını ve durum çubukları](#_core_toolbars_and_status_bars)

##  <a name="_core_menu_layouts"></a> Menü düzenlerini

Menü düzenlerini koordine etmek için ilk adımdır bakın. Daha fazla bilgi için **menü oluşturma** konusundaki [menü programlama konuları](https://msdn.microsoft.com/library/ms647557.aspx) Windows SDK.

Kapsayıcı uygulamaları, yalnızca katıştırılmış öğeler yerinde etkinleştirildiğinde kullanılacak yeni bir menü oluşturmanız gerekir. En azından aşağıdaki listelendikleri sırada bu menü oluşmalıdır:

1. Dosya menüsü dosyası açıkken kullanılan işlem için aynıdır. (Genellikle diğer bir menü öğeleri sonraki öğeye önce yerleştirilir.)

1. İki ardışık ayırıcı.

1. Pencere menüsü dosyası açıkken kullanılan bir özdeş (yalnızca bir MDI uygulamasında kapsayıcı uygulaması). Yerinde gömülü bir öğe etkinleştirildiğinde, menüsünde kalır, bu gruba ait diğer menüler, bir Seçenekler menüsü gibi bazı uygulamalar olabilir.

    > [!NOTE]
    >  Yakınlaştırma gibi kapsayıcı belgenin görünümünü etkileyen başka menüler olabilir. Bu menü kaynağında iki ayırıcıları arasında bu kapsayıcı menü görünür.

Sunucu (Bileşen) uygulamalarını da özellikle yerinde etkinleştirme için yeni menü oluşturmanız gerekir. Bu dosyalar açıkken kullanılan menü gibi ancak menü öğeleri, dosya ve veri yerine sunucu belgesinin düzenleme penceresi gibi olmalıdır. Genellikle, bu menüyü aşağıdakilerden oluşur:

1. Düzen menüsü dosyası açıkken kullanılan işlem için aynıdır.

1. Ayırıcı.

1. Menüleri, karalama örnek uygulamasını kalem menüde gibi düzenleme nesne.

1. Ayırıcı.

1. Yardım menüsü.

Örneğin, bir kapsayıcı ve bir sunucu için bazı örnek yerinde menüleri düzenini bakın. Her bir menü öğesi ayrıntılarını örneği daha anlaşılır hale getirmek için kaldırılmıştır. Kapsayıcının yerinde menüsünde aşağıdaki girişler vardır:

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

Art arda ayırıcılar sunucunun menü ilk bölümünü nereye gösterir. Artık server'ın yerinde menüsüne bakın:

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

İkinci grup kapsayıcı menü öğelerinin nereye gideceğine ayırıcılar burada belirtin. Bu sunucudan bir nesnesi bu kapsayıcının içinde yerinde etkinleştirildiğinde, sonuçta elde edilen menüsü yapısı şu şekilde görünür:

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

Gördüğünüz gibi Ayırıcılar her uygulamanın menüsüne farklı gruplarıyla değiştirilmiştir.

Hızlandırıcı tablolarını yerinde menüsü ile ilişkili sunucu uygulaması tarafından da sağlanmalıdır. Kapsayıcı bunları kendi Hızlandırıcı tablolarına birleştirecektir.

Gömülü bir öğe yerinde etkinleştirildiğinde framework yerinde menü yükler. Ardından, menüsünü sunucu uygulaması için yerinde etkinleştirme ister ve ayırıcılar nerede ekler. Menülerde nasıl birleştirmek budur. Dosya ve Pencere yerleştirme işletim için kapsayıcıdan menüleri alın ve menüler öğede yürütülmesi için sunucudan alın.

##  <a name="_core_toolbars_and_status_bars"></a> Araç çubuklarını ve durum çubukları

Sunucu uygulamaları, yeni bir araç çubuğu oluşturma ve kendi bit eşlem ayrı bir dosyada depolar. Uygulama Sihirbazı tarafından oluşturulan uygulamalar, bu bit eşlem ITOOLBAR adlı bir dosyada depolar. BMP. Yeni araç çubuğu sunucunuzun öğesi yerinde etkinleştirilir ve, normal bir araç olarak aynı öğeleri içeriyor, ancak dosya ve pencere menü öğeleri temsil eden simgeler kaldırmanız kapsayıcı uygulamasının araç değiştirir.

Bu araç çubuğu yüklü olduğu, `COleIPFrameWnd`-türetilmiş sınıf, sizin için Uygulama Sihirbazı tarafından oluşturuldu. Durum çubuğu kapsayıcı uygulama tarafından gerçekleştirilir. Yerinde çerçeve pencereleri uygulama hakkında daha fazla bilgi için bkz. [sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Etkinleştirme](../mfc/activation-cpp.md)<br/>
[Sunucular](../mfc/servers.md)<br/>
[Kapsayıcılar](../mfc/containers.md)

