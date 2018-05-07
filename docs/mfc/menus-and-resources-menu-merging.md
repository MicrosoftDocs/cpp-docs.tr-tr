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
ms.openlocfilehash: 252619872fc53e06629a4cbded7e3640131dc94a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="menus-and-resources-menu-merging"></a>Menüler ve Kaynaklar: Menü Birleştirme
Bu makalede görsel düzenleme işlemek ve düzgün şekilde yerinde etkinleştirme OLE belge uygulamaları için gerekli adımları ayrıntılarını verir. Yerinde etkinleştirme (Bileşen) uygulamaları kapsayıcı ve sunucu için bir zorluk oluşturur. Kullanıcı (kapsayıcı belge bağlamında) aynı çerçeve penceresindeki kalır, ancak gerçekte başka bir uygulama (sunucu) çalışıyor. Bu kapsayıcı ve sunucu uygulamaları kaynaklarına arasında düzenlemesi gerektirir.  
  
 Bu makalede ele alınan konular şunlardır:  
  
- [Menü düzenlerini](#_core_menu_layouts)  
  
- [Araç çubukları ve durum çubukları](#_core_toolbars_and_status_bars)  
  
##  <a name="_core_menu_layouts"></a> Menü düzenlerini  
 Menü düzenlerini koordine etmek için ilk adımdır bakın. Daha fazla bilgi için bkz: **menü oluşturma** bölümüne [menü programlama konuları](https://msdn.microsoft.com/library/ms647557.aspx) Windows SDK'sındaki.  
  
 Kapsayıcı uygulamaları yalnızca katıştırılmış öğeleri yerinde etkinleştirildiğinde kullanılacak yeni bir menü oluşturmanız gerekir. En azından, listelenen sırayla aşağıdaki bu menü oluşmalıdır:  
  
1.  Dosya menüsü dosyaları açık olduğunda kullanılan bir aynı. (Genellikle diğer bir menü öğelerinin sonraki öğe önce yerleştirilir.)  
  
2.  Birbirini izleyen iki ayırıcı.  
  
3.  Pencere menüsü dosyaları açık olduğunda kullanılan bir özdeş (yalnızca bir MDI uygulamada kapsayıcı uygulama). Katıştırılmış öğeyi yerinde etkinleştirildiğinde, menüsünde kalır bu grubun ait diğer menüleri, seçenekleri menüsü gibi bazı uygulamalar olabilir.  
  
    > [!NOTE]
    >  Yakınlaştırma gibi kapsayıcı belge görünümünü etkileyen diğer menüleri olabilir. Bu kapsayıcı menüleri arasında iki ayırıcı bu menü kaynağı olarak görünür.  
  
 Sunucu (Bileşen) uygulamaları da özellikle yerinde etkinleştirme için yeni bir menü oluşturmanız gerekir. Dosyaları açık olduğunda kullanılan menü gibi ancak menü öğeleri, dosya ve veri yerine sunucu belge işlemek pencere gibi olmalıdır. Genellikle, bu menü aşağıdakilerden oluşur:  
  
1.  Düzen menüsü dosyaları açık olduğunda kullanılan bir aynı.  
  
2.  Ayırıcı.  
  
3.  Karalama örnek uygulama kalem menüde gibi menüleri düzenleme nesne.  
  
4.  Ayırıcı.  
  
5.  Yardım menüsü.  
  
 Örneğin, bir kapsayıcı ve bir sunucu için bazı örnek yerinde menüler düzenini bakın. Her bir menü öğesi ayrıntılarını örneği daha anlaşılır yapmak için kaldırıldı. Kapsayıcının yerinde menüsünde aşağıdaki girdileri vardır:  
  
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
  
 Ardışık ayırıcıları sunucunun menü ilk bölümü nereye gösterir. Şimdi sunucunun yerinde menüsüne bakın:  
  
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
  
 Ayırıcılar burada kapsayıcı menü öğelerinin ikinci grup nereye gösterir. Bu kapsayıcı içinde yerinde bir nesne bu sunucudan etkinleştirildiğinde elde edilen menü yapısı şuna benzer:  
  
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
  
 Gördüğünüz gibi ayırıcıları her uygulamanın menü farklı gruplarıyla değiştirilmiştir.  
  
 Hızlandırıcı tabloları yerinde menüsüyle ilişkili Ayrıca sunucu uygulaması tarafından sağlanmalıdır. Kapsayıcı bunları kendi Hızlandırıcı tablolara dahil.  
  
 Katıştırılmış öğeyi yerinde etkinleştirildiğinde framework yerinde menü yükler. Yerinde etkinleştirme için sunucu uygulaması için menü ister ve bunu ayırıcıları nerede ekler. Menüleri nasıl birleştirmek budur. Dosya ve Pencere yerleştirme işletim kapsayıcıdan menüleri alın ve öğede işletim menüleri sunucudan alma.  
  
##  <a name="_core_toolbars_and_status_bars"></a> Araç çubukları ve durum çubukları  
 Sunucu uygulamaları, yeni bir araç çubuğu oluşturma ve kendi bit eşlem ayrı bir dosyada saklayabilir. Uygulama Sihirbazı tarafından oluşturulan uygulamalar bu bit eşlemi ITOOLBAR adlı dosyada depolar. BMP. Yeni araç çubuğu sunucunuzun öğesi yerinde etkinleştirilir ve normal araç olarak aynı öğeleri içerir, ancak dosya ve pencere menü öğelerini temsil eden simgeleri kaldırma kapsayıcı uygulamanın araç yerini alır.  
  
 Bu araç yüklü olduğu, `COleIPFrameWnd`-türetilmiş sınıf, sizin için Uygulama Sihirbazı tarafından oluşturulan. Durum çubuğu kapsayıcı uygulama tarafından işlenir. Yerinde çerçeve pencereleri uygulama hakkında daha fazla bilgi için bkz: [sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)   
 [Etkinleştirme](../mfc/activation-cpp.md)   
 [Sunucuları](../mfc/servers.md)   
 [Kapsayıcılar](../mfc/containers.md)

