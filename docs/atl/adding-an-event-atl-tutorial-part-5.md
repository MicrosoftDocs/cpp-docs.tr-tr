---
title: Olay Ekleme (ATL Eğitmeni, Bölüm 5)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: c9a7c6f38a2f47ec808081e440a200737ad1928a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127580"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Olay Ekleme (ATL Eğitmeni, Bölüm 5)

Bu adımda, ATL denetimine bir `ClickIn` ve `ClickOut` olayı ekleyeceksiniz. Kullanıcı çokgen içinde tıkladıysa ve Kullanıcı dışarıdan tıklarsa `ClickOut` harekete `ClickIn` olayını harekete geçirsiniz. Olay ekleme görevleri aşağıdaki gibidir:

- `ClickIn` ve `ClickOut` yöntemleri ekleme

- Tür kitaplığı oluşturuluyor

- Bağlantı noktası arabirimlerini uygulama

## <a name="adding-the-clickin-and-clickout-methods"></a>Click ve Click yöntemlerini ekleme

2\. adımda ATL denetimini oluştururken **bağlantı noktaları** onay kutusunu seçmiş olursunuz. Bu, Çokgen. IDL dosyasında `_IPolyCtlEvents` arabirimini oluşturdu. Arabirim adının bir alt çizgiyle başlayacağını unutmayın. Bu, arabirimin bir iç arabirim olduğunu gösteren bir kuraldır. Bu nedenle, COM nesnelerine gözatmanıza izin veren programlar kullanıcı arabirimini görüntülememe seçeneğini belirleyebilir. Ayrıca, `_IPolyCtlEvents` varsayılan kaynak arabirim olduğunu göstermek için, **bağlantı noktalarını** seçme, Çokgen. IDL dosyasına aşağıdaki satırı eklediğini unutmayın:

`[default, source] dispinterface _IPolyCtlEvents;`

Kaynak öznitelik, denetimin bildirimlerin kaynağı olduğunu, bu nedenle kapsayıcıda bu arabirimi çağıracağını belirtir.

Artık `ClickIn` ve `ClickOut` yöntemlerini `_IPolyCtlEvents` arabirimine ekleyin.

### <a name="to-add-the-clickin-and-clickout-methods"></a>Click ve Click yöntemlerini eklemek için

1. **Çözüm Gezgini**, Çokgen. IDL açın ve PolygonLib kitaplığının `dispInterface_IPolyCtlEvents` bildiriminde `methods:` altına aşağıdaki kodu ekleyin:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

`ClickIn` ve `ClickOut` yöntemleri, tıklanan noktanın x ve y koordinatlarını parametre olarak alır.

## <a name="generating-the-type-library"></a>Tür kitaplığı oluşturuluyor

Bu noktada tür kitaplığını oluşturun, çünkü proje onu bir bağlantı noktası arabirimi oluşturmak için gereken bilgileri ve denetiminiz için bir bağlantı noktası kapsayıcı arabirimini kullanacak şekilde kullanacaktır.

### <a name="to-generate-the-type-library"></a>Tür kitaplığını oluşturmak için

1. Projenizi yeniden derleyin.

     veya

1. **Çözüm Gezgini** içindeki Çokgen. IDL dosyasına sağ tıklayın ve kısayol menüsünde **Derle** ' ye tıklayın.

Bu işlem, tür kitaplığınız olan Çokgen. tlb dosyasını oluşturur. Çokgen. tlb dosyası, bir ikili dosya olduğundan ve doğrudan görüntülenemediğinden veya düzenlenemediği için **Çözüm Gezgini**görünmüyor.

## <a name="implementing-the-connection-point-interfaces"></a>Bağlantı noktası arabirimlerini uygulama

Denetiminiz için bir bağlantı noktası arabirimi ve bağlantı noktası kapsayıcı arabirimi uygulayın. COM ' da olaylar bağlantı noktaları mekanizmasıyla uygulanır. Bir COM nesnesinden olayları almak için kapsayıcı, COM nesnesinin uyguladığı bağlantı noktasına bir danışmanlık bağlantısı kurar. Bir COM nesnesi birden fazla bağlantı noktasına sahip olabileceğinden, COM nesnesi bir bağlantı noktası kapsayıcı arabirimi de uygular. Bu arabirim aracılığıyla kapsayıcı hangi bağlantı noktalarının desteklendiğini belirleyebilir.

Bir bağlantı noktası uygulayan arabirimine `IConnectionPoint`denir ve bir bağlantı noktası kapsayıcısı uygulayan arabirim `IConnectionPointContainer`olarak adlandırılır.

`IConnectionPoint`uygulamasına yardımcı olmak için bağlantı noktası uygulama Sihirbazı 'Nı kullanacaksınız. Bu sihirbaz, tür kitaplığınızı okuyarak ve tetiklenebilir her olay için bir işlev uygulayarak `IConnectionPoint` arabirimini oluşturur.

### <a name="to-implement-the-connection-points"></a>Bağlantı noktalarını uygulamak için

1. **Çözüm Gezgini**' de, _IPolyCtlEvents_CP. h ' yi açın ve `CProxy_IPolyCtlEvents` sınıfında `public:` deyimin altına aşağıdaki kodu ekleyin:

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

Bu dosyanın `IConnectionPointImpl`türetilen `CProxy_IPolyCtlEvents` adlı bir sınıfa sahip olduğunu görürsünüz. _IPolyCtlEvents_CP. h artık iki yöntemi `Fire_ClickIn` ve `Fire_ClickOut`iki koordinat parametresini alacak olan tanımlıyor. Denetiinizden bir olay tetiklemesi istediğinizde bu yöntemleri çağırın.

Denetim **bağlantı noktalarıyla** seçildiğinde, _IPolyCtlEvents_CP. h dosyası sizin için oluşturulmuştur. Ayrıca, denetimin birden fazla devralma listesine `CProxy_PolyEvents` ve `IConnectionPointContainerImpl` ekler ve COM eşlemesine uygun girdileri ekleyerek `IConnectionPointContainer` açık olarak sunulur.

Olayları desteklemek için kodu uygulamayı tamamladınız. Şimdi, uygun zamanda olayları tetiklemesi için bazı kodlar ekleyin. Kullanıcı denetimdeki sol fare düğmesine tıkladığında bir `ClickIn` veya `ClickOut` olayı tetikleyeceğini unutmayın. Kullanıcının düğmeyi ne zaman tıkladığı hakkında bilgi edinmek için `WM_LBUTTONDOWN` ileti için bir işleyici ekleyin.

### <a name="to-add-a-handler-for-the-wm_lbuttondown-message"></a>WM_LBUTTONDOWN ileti için bir işleyici eklemek için

1. **Sınıf görünümü**' de, `CPolyCtl` sınıfına sağ tıklayıp kısayol menüsünde **Özellikler** ' e tıklayın.

1. **Özellikler** penceresinde **iletiler** simgesine tıklayın ve ardından sol taraftaki listeden `WM_LBUTTONDOWN` ' ye tıklayın.

1. Görüntülenen aşağı açılan listeden, **\<> Onlbuttonaşağı Ekle**' ye tıklayın. `OnLButtonDown` Handler bildirimi PolyCtl. h öğesine eklenecektir ve işleyici uygulama PolyCtl. cpp öğesine eklenecektir.

Sonra, işleyiciyi değiştirin.

### <a name="to-modify-the-onlbuttondown-method"></a>Onlbuttonazaltma yöntemini değiştirmek için

1. PolyCtl. cpp içinde `OnLButtonDown` yöntemi içeren kodu değiştirin (sihirbaz tarafından verilen tüm kodları silme), böylece şöyle görünür:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

Bu kod, `PtInRegion`çağrısıyla kullanıcının fare tıklamasını algılayan bir bölge oluşturmak için `OnDraw` işlevinde hesaplanan noktaların kullanımını sağlar.

*UMsg* parametresi, Işlenmekte olan WINDOWS iletisinin kimliğidir. Bu, bir dizi iletiyi işleyen bir işlevinizin olmasını sağlar. *WParam* ve *lParam* parametreleri, işlenen ileti için standart değerlerdir. *Bişlenmiş* parametresi, işlevin iletiyi işlemediğini belirtmenize izin verir. Varsayılan olarak, işlevin iletiyi işlendiğini göstermek için değeri TRUE olarak ayarlanır, ancak FALSE olarak ayarlayabilirsiniz. Bu, ATL 'nin iletiyi göndermek için başka bir ileti işleyici işlevi aramaya devam etmesine neden olur.

## <a name="building-and-testing-the-control"></a>Denetim oluşturma ve test etme

Şimdi olaylarınızı deneyin. Denetimi derleyin ve ActiveX denetimi test kapsayıcısını yeniden başlatın. Bu kez, olay günlüğü penceresini görüntüleyin. Olayları çıkış penceresine yönlendirmek için, **Seçenekler** menüsünde **günlüğe** Kaydet ' e tıklayın ve **Çıkış penceresinde günlüğe kaydet**' i seçin. Denetimi ekleyin ve pencereyi tıklatmayı deneyin. Doldurulmuş çokgen içinde tıkladıysanız `ClickIn` harekete geçirilir ve dışına tıkladığınızda `ClickOut` tetiklenir.

Sonra bir özellik sayfası ekleyeceksiniz.

Adım &#124; [6 ' da](../atl/adding-a-property-page-atl-tutorial-part-6.md) [Adım 4 ' e dön](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
