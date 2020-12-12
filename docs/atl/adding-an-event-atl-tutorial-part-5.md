---
description: 'Daha fazla bilgi edinin: olay ekleme (ATL öğreticisi, Bölüm 5)'
title: Olay Ekleme (ATL Eğitmeni, Bölüm 5)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: 70c3b570eefa274d2cab9e31420729949d4c7974
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166258"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Olay Ekleme (ATL Eğitmeni, Bölüm 5)

Bu adımda, `ClickIn` ATL denetimine bir ve bir olay ekleyeceksiniz `ClickOut` . `ClickIn`Kullanıcı çokgen içinde tıklarsa ve `ClickOut` Kullanıcı dışarıdan tıkladıysa harekete geçirme olayını harekete geçirsiniz. Olay ekleme görevleri aşağıdaki gibidir:

- `ClickIn`Ve yöntemlerini ekleme `ClickOut`

- Tür kitaplığı oluşturuluyor

- Bağlantı noktası arabirimlerini uygulama

## <a name="adding-the-clickin-and-clickout-methods"></a>Click ve Click yöntemlerini ekleme

2. adımda ATL denetimini oluştururken **bağlantı noktaları** onay kutusunu seçmiş olursunuz. Bu, `_IPolyCtlEvents` arabirimini Çokgen. IDL dosyasında oluşturdu. Arabirim adının bir alt çizgiyle başlayacağını unutmayın. Bu, arabirimin bir iç arabirim olduğunu gösteren bir kuraldır. Bu nedenle, COM nesnelerine gözatmanıza izin veren programlar kullanıcı arabirimini görüntülememe seçeneğini belirleyebilir. Ayrıca, varsayılan kaynak arabirimi olduğunu göstermek için, **bağlantı noktalarını** seçmek için Çokgen. IDL dosyasına aşağıdaki satırı eklendiğini unutmayın `_IPolyCtlEvents` :

`[default, source] dispinterface _IPolyCtlEvents;`

Kaynak öznitelik, denetimin bildirimlerin kaynağı olduğunu, bu nedenle kapsayıcıda bu arabirimi çağıracağını belirtir.

Şimdi `ClickIn` ve `ClickOut` yöntemlerini `_IPolyCtlEvents` arabirimine ekleyin.

### <a name="to-add-the-clickin-and-clickout-methods"></a>Click ve Click yöntemlerini eklemek için

1. **Çözüm Gezgini**, Çokgen. IDL ' yi açın ve aşağıdaki kodu `methods:` `dispInterface_IPolyCtlEvents` PolygonLib kitaplığının bildiriminde altına ekleyin:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

`ClickIn`Ve `ClickOut` yöntemleri, tıklanan noktanın x ve y koordinatlarını parametre olarak alır.

## <a name="generating-the-type-library"></a>Tür kitaplığı oluşturuluyor

Bu noktada tür kitaplığını oluşturun, çünkü proje onu bir bağlantı noktası arabirimi oluşturmak için gereken bilgileri ve denetiminiz için bir bağlantı noktası kapsayıcı arabirimini kullanacak şekilde kullanacaktır.

### <a name="to-generate-the-type-library"></a>Tür kitaplığını oluşturmak için

1. Projenizi yeniden derleyin.

     -veya-

1. **Çözüm Gezgini** içindeki Çokgen. IDL dosyasına sağ tıklayın ve kısayol menüsünde **Derle** ' ye tıklayın.

Bu işlem, tür kitaplığınız olan Çokgen. tlb dosyasını oluşturur. Çokgen. tlb dosyası, bir ikili dosya olduğundan ve doğrudan görüntülenemediğinden veya düzenlenemediği için **Çözüm Gezgini** görünmüyor.

## <a name="implementing-the-connection-point-interfaces"></a>Bağlantı noktası arabirimlerini uygulama

Denetiminiz için bir bağlantı noktası arabirimi ve bağlantı noktası kapsayıcı arabirimi uygulayın. COM ' da olaylar bağlantı noktaları mekanizmasıyla uygulanır. Bir COM nesnesinden olayları almak için kapsayıcı, COM nesnesinin uyguladığı bağlantı noktasına bir danışmanlık bağlantısı kurar. Bir COM nesnesi birden fazla bağlantı noktasına sahip olabileceğinden, COM nesnesi bir bağlantı noktası kapsayıcı arabirimi de uygular. Bu arabirim aracılığıyla kapsayıcı hangi bağlantı noktalarının desteklendiğini belirleyebilir.

Bir bağlantı noktası uygulayan arabirim çağrılır `IConnectionPoint` ve bir bağlantı noktası kapsayıcısı uygulayan arabirim çağrılır `IConnectionPointContainer` .

Uygulamasına yardımcı olmak için `IConnectionPoint` bağlantı noktası uygulama Sihirbazı 'nı kullanacaksınız. Bu sihirbaz, `IConnectionPoint` tür kitaplığınızı okuyarak ve tetiklenebilir her olay için bir işlev uygulayarak arabirimi oluşturur.

### <a name="to-implement-the-connection-points"></a>Bağlantı noktalarını uygulamak için

1. **Çözüm Gezgini**' de, _IPolyCtlEvents_CP. h ' yi açın ve sınıfındaki deyimin altına aşağıdaki kodu ekleyin `public:` `CProxy_IPolyCtlEvents` :

    ```cpp
    VOID Fire_ClickIn(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x1, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    VOID Fire_ClickOut(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x2, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    ```

Bu dosyanın öğesinden türetilen bir sınıfı olduğunu görürsünüz `CProxy_IPolyCtlEvents` `IConnectionPointImpl` . _IPolyCtlEvents_CP. h artık iki yöntemi tanımlar `Fire_ClickIn` ve `Fire_ClickOut` iki koordinat parametresini alır. Denetiinizden bir olay tetiklemesi istediğinizde bu yöntemleri çağırın.

Denetim **bağlantı noktalarıyla** seçildiğinde, _IPolyCtlEvents_CP. h dosyası sizin için oluşturulmuştur. Ayrıca, `CProxy_PolyEvents` `IConnectionPointContainerImpl` denetimin birden fazla devralma listesine EKLENIR ve `IConnectionPointContainer` com eşlemesine uygun girdileri ekleyerek size açık hale gelir.

Olayları desteklemek için kodu uygulamayı tamamladınız. Şimdi, uygun zamanda olayları tetiklemesi için bazı kodlar ekleyin. `ClickIn` `ClickOut` Kullanıcı denetimdeki sol fare düğmesine tıkladığında bir veya olayı tetikleyeceğiz. Kullanıcının düğmeyi ne zaman tıkladığı hakkında bilgi edinmek için ileti için bir işleyici ekleyin `WM_LBUTTONDOWN` .

### <a name="to-add-a-handler-for-the-wm_lbuttondown-message"></a>WM_LBUTTONDOWN ileti için bir işleyici eklemek için

1. **Sınıf görünümü**' de, sınıfa sağ tıklayıp `CPolyCtl` kısayol menüsünde **Özellikler** ' e tıklayın.

1. **Özellikler** penceresinde **iletiler** simgesine tıklayın ve ardından `WM_LBUTTONDOWN` sol taraftaki listeden öğesine tıklayın.

1. Görüntülenen aşağı açılan listeden **\<Add> onlbuttonlist**' e tıklayın. `OnLButtonDown`İşleyici bildirimi PolyCtl. h öğesine eklenir ve işleyici uygulama PolyCtl. cpp öğesine eklenir.

Sonra, işleyiciyi değiştirin.

### <a name="to-modify-the-onlbuttondown-method"></a>Onlbuttonazaltma yöntemini değiştirmek için

1. `OnLButtonDown`PolyCtl. cpp içindeki yöntemi içeren kodu değiştirin (sihirbazın verdiği kodu silme), böylece şöyle görünür:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

Bu kod, üzerinde yapılan `OnDraw` çağrısıyla kullanıcının fare tıklamasını algılayan bir bölge oluşturmak için işlevinde hesaplanan noktaların kullanımını sağlar `PtInRegion` .

*UMsg* parametresi, Işlenmekte olan WINDOWS iletisinin kimliğidir. Bu, bir dizi iletiyi işleyen bir işlevinizin olmasını sağlar. *WParam* ve *lParam* parametreleri, işlenen ileti için standart değerlerdir. *Bişlenmiş* parametresi, işlevin iletiyi işlemediğini belirtmenize izin verir. Varsayılan olarak, işlevin iletiyi işlendiğini göstermek için değeri TRUE olarak ayarlanır, ancak FALSE olarak ayarlayabilirsiniz. Bu, ATL 'nin iletiyi göndermek için başka bir ileti işleyici işlevi aramaya devam etmesine neden olur.

## <a name="building-and-testing-the-control"></a>Denetim oluşturma ve test etme

Şimdi olaylarınızı deneyin. Denetimi derleyin ve ActiveX denetimi test kapsayıcısını yeniden başlatın. Bu kez, olay günlüğü penceresini görüntüleyin. Olayları çıkış penceresine yönlendirmek için, **Seçenekler** menüsünde **günlüğe** Kaydet ' e tıklayın ve **Çıkış penceresinde günlüğe kaydet**' i seçin. Denetimi ekleyin ve pencereyi tıklatmayı deneyin. `ClickIn`Doldurulmuş çokgen içinde tıkladıysanız harekete geçirilir ve `ClickOut` dışını tıkladığınızda tetiklenir.

Sonra bir özellik sayfası ekleyeceksiniz.

Adım 4 ' e [geri döndüğünüzde](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) [6. adım](../atl/adding-a-property-page-atl-tutorial-part-6.md) &#124;

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
