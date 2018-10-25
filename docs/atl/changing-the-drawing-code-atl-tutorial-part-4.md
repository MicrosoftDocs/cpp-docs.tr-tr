---
title: (ATL Eğitmeni, Bölüm 4) çizim kodunu değiştirme | Microsoft Docs
ms.custom: get-started-article
ms.date: 09/26/2018
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f86574dc1d2b996b66b29d2db6d45afc6b81ff7f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065232"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>Çizim Kodunu değiştirme (ATL Eğitmeni, Bölüm 4)

Varsayılan olarak, kare ve metin denetiminin çizim kodu görüntüler **PolyCtl**. Bu adımda, daha çok ilginizi çeken bir şey görüntülemek için kodunu değiştirir. Aşağıdaki görevleri ilgilidir:

- Üstbilgi dosyasını değiştirme

- Değiştirme `OnDraw` işlevi

- Çokgen noktalarının hesaplamak için yöntem ekleme

- Dolgu rengi başlatılıyor

## <a name="modifying-the-header-file"></a>Üstbilgi dosyasını değiştirme

Matematik işlevleri için destek ekleyerek başlangıç `sin` ve `cos`, hangi kullanılacak Çokgen noktalarının hesaplamak ve depolamak için bir dizi oluşturarak yerleştirir.

### <a name="to-modify-the-header-file"></a>Üst bilgi dosyasını değiştirmek için

1. Satır Ekle `#include <math.h>` PolyCtl.h üstüne. Dosyanın en üstüne şu şekilde görünmelidir:

    [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

1. Uygulama `IProvideClassInfo` PolyCtl.h için aşağıdaki kodu ekleyerek denetimi için yöntem bilgilerini sağlamak için arabirim. İçinde `CPolyCtl` sınıfı, satırı değiştirin:

    ```cpp
    public CComControl<CPolyCtl>
    ```

    örneklerini şununla değiştirin:

    ```cpp
    public CComControl<CPolyCtl>,
    public IProvideClassInfo2Impl<&CLSID_PolyCtl, &DIID__IPolyCtlEvents, &LIBID_PolygonLib>
    ```

    ve `BEGIN_COM_MAP(CPolyCtl)`, satırları ekleyin:

    ```cpp
    COM_INTERFACE_ENTRY(IProvideClassInfo)
    COM_INTERFACE_ENTRY(IProvideClassInfo2)
    ```

1. Çokgen noktalarının hesaplanır sonra türünde bir dizi içinde depolanacak `POINT`, bu nedenle dizi tanımı deyiminden sonra ekleyin `short m_nSides;` PolyCtl.h içindeki:

    [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>OnDraw yöntemini değiştirme

Değiştirmeniz artık `OnDraw` PolyCtl.h içindeki yöntemi. Kod ekleyeceğiniz yeni Kalem ve hangi, çokgen çizmek fırça oluşturur ve ardından çağırır `Ellipse` ve `Polygon` gerçek çizim gerçekleştirmek için Win32 API işlevleri.

### <a name="to-modify-the-ondraw-function"></a>OnDraw işlevi değiştirmek için

1. Varolan `OnDraw` PolyCtl.h içindeki yöntemini aşağıdaki kod ile:

    [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>Çokgen noktalarının hesaplamak için yöntem ekleme

Adlı bir yöntem ekleyin `CalcPoints`, çevre çokgenin noktalar koordinatlarını hesaplar. Bu hesaplamalar işleve geçirilen RECT değişkeni hesaplanır.

### <a name="to-add-the-calcpoints-method"></a>CalcPoints yöntemi eklemek için

1. Bildirimi ekleme `CalcPoints` için `IPolyCtl` ortak bölümünü `CPolyCtl` PolyCtl.h içindeki sınıfı:

    [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

    Ortak bölümünü son kısmını `CPolyCtl` sınıfı şu şekilde görünür:

    [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

1. Bu uygulaması Ekle `CalcPoints` PolyCtl.cpp sonuna işlevi:

    [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>Dolgu rengi başlatılıyor

Başlatma `m_clrFillColor` varsayılan renk ile.

### <a name="to-initialize-the-fill-color"></a>Dolgu rengi başlatmak için

1. Kullanma yeşil kullanılan varsayılan rengi için bu satırı ekleyerek `CPolyCtl` PolyCtl.h içindeki Oluşturucu:

    [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

Oluşturucusu şimdi şöyle görünür:

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>Derleme ve denetimini test etme

Denetimi yeniden oluşturun. Hala açık değilse PolyCtl.htm dosyasını kapalı emin olun ve ardından **yapı çokgeni** üzerinde **derleme** menüsü. Polyctl.htm dosyasını sayfasından bir kez daha kontrol görüntüleyebilir, ancak bu kez ActiveX denetimi Test kapsayıcısını kullanın.

### <a name="to-use-the-activex-control-test-container"></a>ActiveX denetimi Test kapsayıcısı kullanmak için

1. Oluşturun ve ActiveX denetimi Test kapsayıcısı başlatın. [TSTCON örnek: ActiveX denetimi Test kapsayıcısını](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/ole/TstCon) Github'da bulunabilir.

    > [!NOTE]
    > İlgili hatalara `ATL::CW2AEX`, Script.Cpp içinde satırı değiştirin `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT );` ile `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT.m_psz );`ve satır `TRACE( "Source Text: %s\n", COLE2CT( bstrSourceLineText ) );` ile `TRACE( "Source Text: %s\n", bstrSourceLineText );`.<br/>
    > İlgili hatalara `HMONITOR`, Stdafx.h'de açın `TCProps` proje ve değiştirin:
    > ```
    > #ifndef WINVER
    > #define WINVER 0x0400
    > #endif
    > ```
    > örneklerini şununla değiştirin:
    > ```
    > #ifndef WINVER
    > #define WINVER 0x0500
    > #define _WIN32_WINNT 0x0500
    > #endif
    > ```

1. İçinde **Test kapsayıcısı**, **Düzenle** menüsünde tıklatın **yeni denetimi Ekle**.

1. Çağrılacak denetiminiz bulun `PolyCtl class`, tıklatıp **Tamam**. Yeşil bir üçgen içindeki bir daire görürsünüz.

Sonraki yordamı izleyerek kenar sayısını değiştirmeyi deneyin. Çift arabirim içinden özelliklerini değiştirmek için **Test kapsayıcısı**, kullanın **çağırma yöntemleri**.

### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>Test kapsayıcı içindeki bir denetimin özelliğini değiştirmek için

1. İçinde **Test kapsayıcısı**, tıklayın **çağırma yöntemleri** üzerinde **denetimi** menüsü.

    **Yöntemi Çağır** iletişim kutusu görüntülenir.

1. Seçin **PropPut** sürümünü **yüz** özelliğinden **yöntem adı** aşağı açılan liste kutusu.

1. Tür `5` içinde **parametre değeri** kutusunun **değer kümesi**, tıklatıp **Invoke**.

Denetim değişmez unutmayın. Kenar sayısını dahili olarak ayarlayarak değiştirdiğiniz rağmen `m_nSides` değişken, bu denetimin repaint neden olmadı. Başka bir uygulamaya geçiş yapın ve ardından geri dönmek **Test kapsayıcısı**, denetimi yeniden çizilmesini ve kenar sayısını doğru olduğunu bulabilirsiniz.

Bu sorunu düzeltmek için bir çağrı ekleyin `FireViewChange` işlevi, tanımlanan `IViewObjectExImpl`, kenar sayısını ayarladıktan sonra. Denetimin kendi penceresinde çalışıyorsa `FireViewChange` çağıracak `InvalidateRect` doğrudan yöntemi. Denetim penceresiz, çalışıyorsa `InvalidateRect` kapsayıcının sitesi arabirimi yöntemi çağrılır. Bu denetim kendisini çizilecek zorlar.

### <a name="to-add-a-call-to-fireviewchange"></a>Bir çağrı FireViewChange eklemek için

1. Çağrı ekleyerek PolyCtl.cpp güncelleştirme `FireViewChange` için `put_Sides` yöntemi. İşiniz bittiğinde `put_Sides` yöntemi şu şekilde görünmelidir:

    [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

Ekledikten sonra `FireViewChange`yeniden oluşturun ve denetim ActiveX denetimi Test kapsayıcısı içinde yeniden deneyin. Bu zaman zaman kenar sayısını değiştirmek ve tıklayın `Invoke`, hemen değiştirmeniz denetim görmeniz gerekir.

Sonraki adımda, bir olay ekler.

[3. adım dön](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [5. adım açın](../atl/adding-an-event-atl-tutorial-part-5.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)<br/>
[Test Kapsayıcısı ile Özellikleri ve Olayları Test Etme](../mfc/testing-properties-and-events-with-test-container.md)
