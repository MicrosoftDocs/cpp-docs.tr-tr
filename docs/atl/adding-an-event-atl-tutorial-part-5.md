---
title: Olay Ekleme (ATL Eğitmeni, Bölüm 5)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: 57fc2adaadcca52cfc25736b5f9010fcb65a2ff0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278645"
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

### <a name="to-add-the-clickin-and-clickout-methods"></a>Clickın ve ClickOut yöntemi eklemek için

1. İçinde **Çözüm Gezgini**Polygon.idl açın ve aşağıdaki kodu ekleyin `methods:` içinde `dispInterface_IPolyCtlEvents` bildirimi PolygonLib kitaplığı:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

`ClickIn` Ve `ClickOut` yöntemleri Al x ve y koordinatları tıklatılan noktadan parametre olarak.

## <a name="generating-the-type-library"></a>Tür kitaplığı oluşturma

Tür kitaplığı, proje, bir bağlantı noktası arabirimi ve denetim için bir bağlantı noktası kapsayıcı arabirimi oluşturmak gereken bilgileri elde etmek için kullanacağınız için bu noktada, oluşturur.

### <a name="to-generate-the-type-library"></a>Tür kitaplığı oluşturmak için

1. Projenizi yeniden derleyin.

     -veya-

1. Polygon.idl dosyaya sağ **Çözüm Gezgini** tıklatıp **derleme** kısayol menüsünde.

Bu, tür kitaplığı Polygon.tlb dosyasını oluşturur. Polygon.tlb dosyanın görülemediğinden, **Çözüm Gezgini**, çünkü bu bir ikili dosyadır ve görüntülenemez veya doğrudan düzenlenemez.

## <a name="implementing-the-connection-point-interfaces"></a>Bağlantı noktası arabirimleri uygulama

Bir bağlantı noktası arabirimi ve denetim için bir bağlantı noktası kapsayıcı arabirimi uygular. COM olayları bağlantı noktaları bir mekanizma aracılığıyla uygulanır. Bir COM nesneden olayları almak için bir kapsayıcı COM nesnesi uygulayan bağlantı noktasına danışmanlık bir bağlantı kurar. Bir COM nesnesi birden çok bağlantı noktaları olduğundan COM nesnesi bir bağlantı noktası kapsayıcı arabirimini de uygular. Bu arabirimi aracılığıyla, hangi bağlantı noktalarının desteklenen kapsayıcı belirleyebilirsiniz.

Arabirimi uygulayan bir bağlantı noktası olarak adlandırılan `IConnectionPoint`, ve bir bağlantı noktası kapsayıcı uygulayan arabirimi çağrılır `IConnectionPointContainer`.

Uygulamak için `IConnectionPoint`, bağlantı noktası Uygulama Sihirbazı'nı kullanın. Bu sihirbaz oluşturur `IConnectionPoint` , tür kitaplığı okuma ve harekete her bir olay için bir işlevi uygulayarak arabirimi.

### <a name="to-implement-the-connection-points"></a>Bağlantı noktalarını uygulamak için

1. İçinde **Çözüm Gezgini**_IPolyCtlEvents_CP.h açın ve aşağıdaki kodu ekleyin `public:` deyiminde `CProxy_IPolyCtlEvents` sınıfı:

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

Bu dosya adında bir sınıf olduğunu görürsünüz `CProxy_IPolyCtlEvents` türetilen `IConnectionPointImpl`. _IPolyCtlEvents_CP.h artık iki yöntemi tanımlar `Fire_ClickIn` ve `Fire_ClickOut`, iki koordinat parametre yararlanın. Denetim bir olay harekete istediğinizde bu yöntemi çağırın.

Denetimle oluşturarak **bağlantı noktaları** seçeneği _IPolyCtlEvents_CP.h dosyanın, oluşturulduğu. Ayrıca eklenen BT `CProxy_PolyEvents` ve `IConnectionPointContainerImpl` denetiminizin birden çok devralma listesine ve kullanıma `IConnectionPointContainer` COM eşlemesine uygun girdileri ekleniyor aktarılarak sizin için.

Olayları desteklemek için kod uygulama tamamlanmış demektir. Şimdi, uygun şu anda olaylarını başlatmak için kod ekleyin. Unutmayın, ateşlenmesine seçeceğiz bir `ClickIn` veya `ClickOut` kullanıcının sol fare düğmesine denetimde tıkladığında bir olay. Kullanıcı düğmeye tıkladığında öğrenmek için bir işleyici eklemek `WM_LBUTTONDOWN` ileti.

### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>WM_LBUTTONDOWN iletisi için bir işleyici eklemek için

1. İçinde **sınıf görünümü**, sağ `CPolyCtl` sınıfı ve tıklayın **özellikleri** kısayol menüsünde.

1. İçinde **özellikleri** penceresinde tıklayın **iletileri** simgesine ve ardından `WM_LBUTTONDOWN` sol taraftaki listeden.

1. Görünen açılan listeden tıklayın  **\<Ekle > OnLButtonDown**. `OnLButtonDown` İşleyici bildirimi için PolyCtl.h eklenir ve işleyici uygulama için PolyCtl.cpp eklenir.

Ardından, işleyici değiştirin.

### <a name="to-modify-the-onlbuttondown-method"></a>OnLButtonDown yöntemi değiştirmek için

1. Oluşur kodunu değiştirmek `OnLButtonDown` (Sihirbaz tarafından yerleştirilen herhangi bir kod silme) PolyCtl.cpp yönteminde böylece şöyle görünür:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

Bu kod yapar noktalarının kullanımını hesaplanır `OnDraw` Kullanıcı fareye tıklayana çağrısıyla algılayan bir bölge oluşturmak için işlevi `PtInRegion`.

*UMsg* parametredir işlenen Windows iletinin kimliği. Bu, bir dizi iletileri işleyen bir işlev olmasını sağlar. *WParam* ve *lParam* parametreleri işlenmekte olan ileti için standart değerlerdir. Parametre *bHandled* işlevi veya iletiyi işleyip işlemediğini belirtmenizi sağlar. Varsayılan olarak, değer, iletinin işlevi işlenmiş, ancak FALSE olarak ayarlayabilirsiniz olduğunu belirtmek için TRUE olarak ayarlanır. Bu, ATL ileti göndermek başka bir ileti işleyici işlevi mi arıyorsunuz devam etmesine neden olur.

## <a name="building-and-testing-the-control"></a>Derleme ve denetimini test etme

Olaylarınızı ' ı şimdi deneyin. Denetimi oluşturun ve ActiveX denetimi Test kapsayıcısını yeniden başlatın. Bu kez, Olay Günlüğü penceresini görüntüleyin. Çıkış penceresinde olaylarını yönlendirme için tıklayın **günlüğü** gelen **seçenekleri** menü ve select **çıkış penceresinde günlük**. Denetim ekleme ve penceresinde tıklamayı deneyin. Unutmayın `ClickIn` dolu bir Çokgen içinde tıklarsanız tetiklenir ve `ClickOut` dışında tıklattığınızda tetiklenir.

Ardından, bir özellik sayfası ekleyeceksiniz.

[4. adım dön](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [6. adım açın](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
