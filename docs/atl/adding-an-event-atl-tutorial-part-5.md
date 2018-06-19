---
title: Bir olay (ATL Eğitmeni, bölüm 5) ekleme | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a118cf29546ac8dae2e882d5658b07e3b5e085f6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361271"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Olay Ekleme (ATL Eğitmeni, Bölüm 5)
Bu adımda, ekleyeceksiniz bir `ClickIn` ve `ClickOut` ATL Denetim Olayı. Ateşlenir `ClickIn` kullanıcı Çokgen ve yangın içinde tıklarsa olay `ClickOut` kullanıcı dışında tıklarsa. Bir olay eklemek için görevleri aşağıdaki gibidir:  
  
-   Ekleme `ClickIn` ve `ClickOut` yöntemleri  
  
-   Tür kitaplığı oluşturma  
  
-   Bağlantı noktası arabirimler uygulama  
  
## <a name="adding-the-clickin-and-clickout-methods"></a>Clickın ve ClickOut yöntemleri ekleme  
 ATL Denetim 2. adımda oluşturduğunuz zaman, seçtiğiniz **bağlantı noktaları** onay kutusu. Bu oluşturulan `_IPolyCtlEvents` Polygon.idl dosyasında arabirimi. Arabirim adı alt çizgi ile başlayan unutmayın. Bu arabirim dahili bir arabirimi olduğunu belirtmek için bir kuraldır. Bu nedenle, için kullanıcı arabirimi görüntülememeyi, COM nesneleri göz atmanıza izin programları seçebilirsiniz. Ayrıca bu seçerek unutmayın **bağlantı noktaları** belirtmek için Polygon.idl dosyasında aşağıdaki satırı eklenen `_IPolyCtlEvents` varsayılan kaynak arabirimidir:  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 Kaynak özniteliği kapsayıcıda bu arabirim çağıracak şekilde denetim bildirimleri kaynağı olduğunu gösterir.  
  
 Şimdi ekleyin `ClickIn` ve `ClickOut` yöntemlere `_IPolyCtlEvents` arabirimi.  
  
#### <a name="to-add-the-clickin-and-clickout-methods"></a>Clickın ve ClickOut yöntemleri eklemek için  
  
1.  Sınıf Görünümü'nde Çokgen ve PolygonLib _IPolyCtlEvents görüntülemek için'ı genişletin.  
  
2.  _IPolyCtlEvents sağ tıklayın. Kısayol menüsünde **Ekle**ve ardından **ekleme yöntemi**.  
  
3.  Seçin bir **dönüş türü** , `void`.  
  
4.  Girin `ClickIn` içinde **yöntem adı** kutusu.  
  
5.  Altında **parametre öznitelikleri**seçin **içinde** kutusu.  
  
6.  Seçin bir **parametre türü** , `LONG`.  
  
7.  Tür `x` olarak **parametre adı**, tıklatıp **Ekle**.  
  
8.  Adım 5'ten 7'de, bu süre için yineleyin bir **parametre adı** , `y`.  
  
9. **İleri**'ye tıklayın.  
  
10. Tür `method ClickIn` olarak **helpstring**.  
  
11. **Son**'a tıklayın.  
  
12. Tanımlamak için yukarıdaki adımları yineleyin bir `ClickOut` aynı yöntemiyle `LONG` parametreleri `x` ve `y`, aynı **parametre öznitelikleri** ve aynı `void` dönüş türü.  
  
 Kod eklendi görmek için Polygon.idl dosyasını kontrol `_IPolyCtlEvents` görüntüleme arabirimi.  
  
 `_IPolyCtlEvents` Polygon.idl dosyanızdaki görüntüleme arabirimi şimdi şöyle görünmelidir:  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 `ClickIn` Ve `ClickOut` yöntemleri Al x ve parametre olarak tıklatılan noktasının y koordinatları.  
  
## <a name="generating-the-type-library"></a>Tür kitaplığı oluşturma  
 Bağlantı noktası Sihirbazı'nı bir bağlantı noktası arabirimi ve denetim için bir bağlantı noktası kapsayıcı arabirimi oluşturmak için gereken bilgileri elde etmek için kullanacağınız için tür kitaplığı bu noktada, oluşturun.  
  
#### <a name="to-generate-the-type-library"></a>Tür kitaplığı oluşturmak için  
  
1.  Projenizi yeniden derleyin.  
  
     -veya-  
  
2.  Çözüm Gezgini'nde Polygon.idl dosyasını sağ tıklatın ve **derleme** kısayol menüsünde.  
  
 Bu tür kitaplığınızda Polygon.tlb dosyası oluşturur. Onu ikili dosyadır ve görüntülenemez veya doğrudan düzenlenmesine çünkü Polygon.tlb dosya Çözüm Gezgini'nden görünür değil.  
  
## <a name="implementing-the-connection-point-interfaces"></a>Bağlantı noktası arabirimler uygulama  
 Bir bağlantı noktası arabirimi ve denetlemek için bir bağlantı noktası kapsayıcı arabirimini uygular. COM'da, olayları bağlantı noktaları bir mekanizma aracılığıyla uygulanır. Bir COM nesneden olaylarını almak için bir kapsayıcı COM nesnesi uygulayan bağlantı noktası danışma bir bağlantı kurar. Bir COM nesnesi birden çok bağlantı noktaları olduğundan COM nesnesi de bağlantı noktası kapsayıcı arabirimini uygular. Bu arabirimi aracılığıyla kapsayıcı hangi bağlantı noktalarının desteklenen belirleyebilirsiniz.  
  
 Bir bağlantı noktası uygulayan arabirimi adlı `IConnectionPoint`, ve bir bağlantı noktası kapsayıcı uygulayan arabirimi adlı `IConnectionPointContainer`.  
  
 Uygulama yardımcı olmak için `IConnectionPoint`, bağlantı noktası Uygulama Sihirbazı'nı kullanır. Bu sihirbaz oluşturur `IConnectionPoint` tür kitaplığı okuyarak ve puanlı her olay için bir işlev uygulama arabirimi.  
  
#### <a name="to-use-the-implement-connection-point-wizard"></a>Bağlantı noktası Uygulama Sihirbazı kullanmak için  
  
1.  Sınıf Görünümü'nde denetiminizin uygulama sınıfı sağ `CPolyCtl`.  
  
2.  Kısayol menüsünde **Ekle**ve ardından **bağlantı noktası ekleme**.  
  
3.  Seçin `_IPolyCtlEvents` gelen **kaynak arabirimleri** eklemek için çift tıklayın ve liste **uygulamak bağlantı noktaları** sütun. **Son**'a tıklayın. Bağlantı noktası için bir proxy sınıfı, bu durumda, oluşturulmaması `CProxy_IPolyCtlEvents`.  
  
 Çözüm Gezgini'nde oluşturulan _IPolyCtlEvents_CP.h dosyayı bakarsanız adlı bir sınıf olduğunu görürsünüz `CProxy_IPolyCtlEvents` , türetilen `IConnectionPointImpl`. _IPolyCtlEvents_CP.h iki yöntem de tanımlar `Fire_ClickIn` ve `Fire_ClickOut`, iki koordinat parametre alın. Bir olay, denetiminden tetikleyin istediğinizde bu yöntemlerini çağırın.  
  
 Ayrıca eklendi Sihirbazı'nı `CProxy_PolyEvents` ve `IConnectionPointContainerImpl` denetiminizin birden çok devralma listesi. Sihirbazın de kullanıma sunulan `IConnectionPointContainer` , COM eşlemesi için uygun girişleri ekleyerek.  
  
 Olayları desteklemek için kod uygulama tamamlanmış demektir. Şimdi, uygun şu anda olayları tetiklenecek bazı kodlar ekleyin. Unutmayın, bulacağınızı tetiklenecek bir `ClickIn` veya `ClickOut` kullanıcı denetimi sol fare düğmesini tıklattığında olay. Kullanıcı düğmesini tıklattığında öğrenmek için bir işleyici ekleyin `WM_LBUTTONDOWN` ileti.  
  
#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>WM_LBUTTONDOWN ileti işleyicisi eklemek için  
  
1.  Sınıf Görünümü'nde CPolyCtl sınıfı sağ tıklatın ve **özellikleri** kısayol menüsünde.  
  
2.  İçinde **özellikleri** penceresinde tıklatın **iletileri** simgesine tıklayın ve sonra `WM_LBUTTONDOWN` sol taraftaki listeden.  
  
3.  Görüntülenen açılan listesinden tıklatın  **\<Ekle > OnLButtonDown**. `OnLButtonDown` İşleyici bildirimi için PolyCtl.h eklenir ve işleyici uygulaması için PolyCtl.cpp eklenir.  
  
 Ardından, işleyici değiştirin.  
  
#### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown yöntemi değiştirmek için  
  
1.  Oluşur kodunda değişiklik `OnLButtonDown` (Sihirbaz tarafından yerleştirilen herhangi bir kod silme) PolyCtl.cpp yönteminde böylece şöyle görünür:  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 Bu kod yapar noktalarının kullanımını hesaplanır `OnDraw` kullanıcının fare tıklamaları çağrısıyla algılar bir bölge oluşturmak için işlevi `PtInRegion`.  
  
 `uMsg` Parametredir işlenen Windows iletinin kimliği. Bu, bir dizi iletileri işleyen bir işlev olmasını sağlar. `wParam` Ve `lParam` parametreleri işlenen ileti için standart değerlerdir. Parametre bHandled işlevi iletinin olup olmadığını işlenmiş belirtmenize olanak tanır. Varsayılan değer ayarlamak `TRUE` işlevi iletinin işlenmiş, ancak ayarlayabilirsiniz göstermek için `FALSE`. Bu ileti göndermek başka bir ileti işleyicisi işlevi arayan devam etmek ATL neden olur.  
  
## <a name="building-and-testing-the-control"></a>Derleme ve denetim test etme  
 Şimdi, olaylarını deneyin. Denetimi oluşturun ve ActiveX denetimi Test kapsayıcısı yeniden başlatın. Bu süre, Olay Günlüğü penceresini görüntüleyin. Çıktı penceresi olayları yönlendirmek için tıklatın **günlüğü** gelen **seçenekleri** menü ve seçin **çıktı penceresi günlüğe**. Penceresinde tıklatmayı deneyin ve denetim ekleyin. Unutmayın `ClickIn` dolu Çokgen içinde tıklatırsanız tetiklenir ve `ClickOut` dışında tıklattığınızda tetiklenir.  
  
 Sonra bir özellik sayfası ekleyeceksiniz.  
  
 [Adım 4 dön](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [adıma 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)

