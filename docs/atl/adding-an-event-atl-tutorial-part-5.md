---
title: Bir olay ekleme (ATL Eğitmeni, bölüm 5) | Microsoft Docs
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
ms.openlocfilehash: 1bb72babcc4bf425e4ea588e4e2a155b077c47cc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754884"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Olay Ekleme (ATL Eğitmeni, Bölüm 5)

Bu adımda, ekleyeceksiniz bir `ClickIn` ve `ClickOut` ATL Denetim Olayı. Ateşlenir `ClickIn` kullanıcı Çokgen ve yangın içinde tıklarsa olay `ClickOut` dışında tıklarsa. Görevleri bir olay eklemek için aşağıdaki gibidir:

- Ekleme `ClickIn` ve `ClickOut` yöntemleri

- Tür kitaplığı oluşturma

- Bağlantı noktası arabirimleri uygulama

## <a name="adding-the-clickin-and-clickout-methods"></a>Clickın ve ClickOut yöntemler ekleme

ATL denetimi 2. adımda oluşturduğunuz zaman seçtiğiniz **bağlantı noktaları** onay kutusu. Bu oluşturulan `_IPolyCtlEvents` Polygon.idl dosyasındaki arabirimi. Arabirim adı alt çizgi ile başlatır. Bu bir iç arabiriminde arabirimi olduğunu belirtmek için bir kuraldır. Bu nedenle, COM nesneleri göz atmanıza izin programlar arabirimi kullanıcıya göstermek seçebilirsiniz. Ayrıca bu seçerek unutmayın **bağlantı noktaları** göstermek için Polygon.idl dosyasında aşağıdaki satırı eklenen `_IPolyCtlEvents` varsayılan kaynak arabirimi:

`[default, source] dispinterface _IPolyCtlEvents;`

Kaynak özniteliği, bu arabirim kapsayıcıdaki çağıracak şekilde denetim bildirimleri kaynağını olduğunu gösterir.

Şimdi ekleyin `ClickIn` ve `ClickOut` yöntemlere `_IPolyCtlEvents` arabirimi.

#### <a name="to-add-the-clickin-and-clickout-methods"></a>Clickın ve ClickOut yöntemi eklemek için

1. Sınıf Görünümü'nde, Çokgen ve PolygonLib _IPolyCtlEvents görüntülemek için genişletin.

2. _IPolyCtlEvents sağ tıklayın. Kısayol menüsünde **Ekle**ve ardından **Ekle yöntemi**.

3. Seçin bir **dönüş türü** , `void`.

4. Girin *Clickın* içinde **yöntem adı** kutusu.

5. Altında **parametre öznitelikleri**seçin **içinde** kutusu.

6. Seçin bir **parametre türü** , `LONG`.

7. Tür *x* olarak **parametre adı**, tıklatıp **Ekle**.

8. 5. adım-7, bu süre için yineleyin bir **parametre adı** , *y*.

9. **İleri**'ye tıklayın.

10. Tür `method ClickIn` olarak **helpstring**.

11. **Son**'a tıklayın.

12. Tanımlamak için yukarıdaki adımları yineleyin bir `ClickOut` aynı yöntemle `LONG` parametreleri *x* ve *y*, aynı **parametre öznitelikleri** ve aynı `void` dönüş türü.

Kod için eklendiğini görmeyi Polygon.idl dosyayı `_IPolyCtlEvents` dispinterface.

`_IPolyCtlEvents` Polygon.idl dosyanızdaki dispinterface artık şu şekilde görünmelidir:

[!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]

`ClickIn` Ve `ClickOut` yöntemleri Al x ve y koordinatları tıklatılan noktadan parametre olarak.

## <a name="generating-the-type-library"></a>Tür kitaplığı oluşturma

Tür kitaplığı, bağlantı noktası Sihirbazı'nı bir bağlantı noktası arabirimi ve denetim için bir bağlantı noktası kapsayıcı arabirimi oluşturmak gereken bilgileri elde etmek için kullanacağınız için bu noktada, oluşturun.

#### <a name="to-generate-the-type-library"></a>Tür kitaplığı oluşturmak için

1. Projenizi yeniden derleyin.

     veya

2. Çözüm Gezgini'nde Polygon.idl dosyaya sağ tıklatıp **derleme** kısayol menüsünde.

Bu, tür kitaplığı Polygon.tlb dosyasını oluşturur. Bunu bir ikili dosyadır ve görüntülenemez veya doğrudan düzenlenebilir olmadığından Polygon.tlb dosya Çözüm Gezgini'nde görünür değil.

## <a name="implementing-the-connection-point-interfaces"></a>Bağlantı noktası arabirimleri uygulama

Bir bağlantı noktası arabirimi ve denetim için bir bağlantı noktası kapsayıcı arabirimi uygular. COM olayları bağlantı noktaları bir mekanizma aracılığıyla uygulanır. Bir COM nesneden olayları almak için bir kapsayıcı COM nesnesi uygulayan bağlantı noktasına danışmanlık bir bağlantı kurar. Bir COM nesnesi birden çok bağlantı noktaları olduğundan COM nesnesi bir bağlantı noktası kapsayıcı arabirimini de uygular. Bu arabirimi aracılığıyla, hangi bağlantı noktalarının desteklenen kapsayıcı belirleyebilirsiniz.

Arabirimi uygulayan bir bağlantı noktası olarak adlandırılan `IConnectionPoint`, ve bir bağlantı noktası kapsayıcı uygulayan arabirimi çağrılır `IConnectionPointContainer`.

Uygulamak için `IConnectionPoint`, bağlantı noktası Uygulama Sihirbazı'nı kullanın. Bu sihirbaz oluşturur `IConnectionPoint` , tür kitaplığı okuma ve harekete her bir olay için bir işlevi uygulayarak arabirimi.

#### <a name="to-use-the-implement-connection-point-wizard"></a>Bağlantı noktası Uygulama Sihirbazı'nı kullanmak için

1. Sınıf Görünümü'nde sağ tıklayın, denetimin uygulama sınıfı `CPolyCtl`.

2. Kısayol menüsünde **Ekle**ve ardından **bağlantı noktası Ekle**.

3. Seçin `_IPolyCtlEvents` gelen **kaynak arabirimleri** listelemek ve eklemek için çift tıklayın **uygulamak bağlantı noktaları** sütun. **Son**'a tıklayın. Bağlantı noktası için bir proxy sınıfı, bu durumda, oluşturulacak `CProxy_IPolyCtlEvents`.

Çözüm Gezgini içinde oluşturulan _IPolyCtlEvents_CP.h dosya bakarsanız, adında bir sınıf olduğunu görürsünüz `CProxy_IPolyCtlEvents` türetilen `IConnectionPointImpl`. _IPolyCtlEvents_CP.h iki yöntem de tanımlar `Fire_ClickIn` ve `Fire_ClickOut`, iki koordinat parametre yararlanın. Denetim bir olay harekete istediğinizde bu yöntemi çağırın.

Ayrıca eklenen Sihirbazı `CProxy_PolyEvents` ve `IConnectionPointContainerImpl` denetiminizin birden çok devralma listesi. Sihirbazın de kullanıma sunulan `IConnectionPointContainer` için size COM eşlemesine uygun girdileri ekleniyor.

Olayları desteklemek için kod uygulama tamamlanmış demektir. Şimdi, uygun şu anda olaylarını başlatmak için kod ekleyin. Unutmayın, ateşlenmesine seçeceğiz bir `ClickIn` veya `ClickOut` kullanıcının sol fare düğmesine denetimde tıkladığında bir olay. Kullanıcı düğmeye tıkladığında öğrenmek için bir işleyici eklemek `WM_LBUTTONDOWN` ileti.

#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>WM_LBUTTONDOWN iletisi için bir işleyici eklemek için

1. Sınıf Görünümü'nde CPolyCtl sınıfı sağ tıklatıp **özellikleri** kısayol menüsünde.

2. İçinde **özellikleri** penceresinde tıklayın **iletileri** simgesine ve ardından `WM_LBUTTONDOWN` sol taraftaki listeden.

3. Görünen açılan listeden tıklayın  **\<Ekle > OnLButtonDown**. `OnLButtonDown` İşleyici bildirimi için PolyCtl.h eklenir ve işleyici uygulama için PolyCtl.cpp eklenir.

Ardından, işleyici değiştirin.

#### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown yöntemi değiştirmek için

1. Oluşur kodunu değiştirmek `OnLButtonDown` (Sihirbaz tarafından yerleştirilen herhangi bir kod silme) PolyCtl.cpp yönteminde böylece şöyle görünür:

     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

Bu kod yapar noktalarının kullanımını hesaplanır `OnDraw` Kullanıcı fareye tıklayana çağrısıyla algılayan bir bölge oluşturmak için işlevi `PtInRegion`.

*UMsg* parametredir işlenen Windows iletinin kimliği. Bu, bir dizi iletileri işleyen bir işlev olmasını sağlar. *WParam* ve *lParam* parametreleri işlenmekte olan ileti için standart değerlerdir. Parametre bHandled işlevi veya iletiyi işleyip işlemediğini belirtmenizi sağlar. Varsayılan olarak, değer, iletinin işlevi işlenmiş, ancak FALSE olarak ayarlayabilirsiniz olduğunu belirtmek için TRUE olarak ayarlanır. Bu, ATL ileti göndermek başka bir ileti işleyici işlevi mi arıyorsunuz devam etmesine neden olur.

## <a name="building-and-testing-the-control"></a>Derleme ve denetimini test etme

Olaylarınızı ' ı şimdi deneyin. Denetimi oluşturun ve ActiveX denetimi Test kapsayıcısını yeniden başlatın. Bu kez, Olay Günlüğü penceresini görüntüleyin. Çıkış penceresinde olaylarını yönlendirme için tıklayın **günlüğü** gelen **seçenekleri** menü ve select **çıkış penceresinde günlük**. Denetim ekleme ve penceresinde tıklamayı deneyin. Unutmayın `ClickIn` dolu bir Çokgen içinde tıklarsanız tetiklenir ve `ClickOut` dışında tıklattığınızda tetiklenir.

Ardından, bir özellik sayfası ekleyeceksiniz.

[4. adım dön](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [6. adım açın](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)

