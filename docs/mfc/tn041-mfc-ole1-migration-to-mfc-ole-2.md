---
title: 'TN041: MFC-OLE 2 MFC-OLE1 geçişi'
ms.date: 10/18/2018
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- OLE1 [MFC]
- migrating OLE1 to OLE2
- migration [MFC], OLE1 to OLE2
- OLE2 [MFC]
- porting OLE1 to OLE2
- converting OLE1 to OLE2
- upgrading Visual C++ applications [MFC], OLE1 to OLE2
- TN041
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
ms.openlocfilehash: b398a1adbf2f47343eed076f32ade5bb2564cd52
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767983"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041: MFC/OLE 2 MFC/OLE1 geçişi

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

## <a name="general-issues-relating-to-migration"></a>Geçiş ile ilgili genel sorunları giderme

Tasarım hedefleri OLE 2 sınıflar, MFC 2.5 (ve üzeri) için MFC 2.0 OLE 1.0 desteği yararlanılmasını aynı mimariye çoğunu korumak için biriydi. Sonuç olarak, birçok MFC 2.0 aynı OLE sınıfları MFC'nin bu sürümünü mevcut (`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`). Ayrıca, bu sınıflar API'leri birçoğu tam olarak aynıdır. Ancak, bazı ayrıntılar değişmiş beklediğiniz şekilde OLE 2 OLE 1.0 önemli ölçüde farklılık gösterir. MFC 2.0'ın OLE1 desteğiyle biliyorsanız, evde MFC'nin 2.0 desteğiyle rahattır.

Varolan bir MFC/OLE1 uygulama alma ve OLE 2 işlevselliğini eklemeden önce bu not okumalısınız. Bu Not OLE1 işlevinizi MFC/OLE 2'ye taşıma sırasında karşılaşabileceğiniz ve ardından MFC 2.0 dahil iki uygulama taşıma sırasında ortaya çıkardı sorunlar ele alınmaktadır bazı genel sorunları ele alır: MFC OLE örnekleri [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR](../overview/visual-cpp-samples.md).

## <a name="mfc-documentview-architecture-is-important"></a>MFC belge/görünüm mimarisi önemlidir

Uygulamanızı MFC'nin belge/görünüm mimarisi kullanmaz ve OLE 2 desteği uygulamanıza eklemek istediğiniz, belge/görünüm taşıma zamanı sunulmuştur. Uygulamanızı yerleşik mimarisi ve MFC bileşenlerini kullanarak sonra MFC'nin OLE 2 sınıflarının avantajlarının birçoğundan faydalanılmasını yalnızca alırlar.

MFC mimarisi kullanmadan bir sunucu veya kapsayıcı uygulama, olası, ancak önerilmez.

## <a name="use-mfc-implementation-instead-of-your-own"></a>MFC uygulaması kendi yerine kullanın

MFC canned"uygulama" sınıflar gibi `CToolBar`, `CStatusBar`, ve `CScrollView` OLE 2 desteği için yerleşik özel durum koduna sahip. Bu nedenle, uygulamanızda bu sınıfların kullanabiliyorsa OLE uyumlu olacak şekilde bunlara put emeğinin yararlı olur. Yeniden bu amaçlar için "TOP kendi" sınıflarına burada mümkündür, ancak değil önerilir. Benzer işlevselliği uygulamak gerekiyorsa (özellikle, yerinde etkinleştirme söz konusu olduğunda) MFC kaynak kodu OLE hassas noktalarının bazıları başa çıkmak için mükemmel bir başvuru verilmiştir.

## <a name="examine-the-mfc-sample-code"></a>MFC örnek kodu incelemeden

OLE işlevselliği eklemek MFC örnekleri vardır. Bu uygulamaların her biri farklı bir açıdan OLE uygular:

- [HIERSVR](../overview/visual-cpp-samples.md) çoğunlukla bir sunucu uygulaması olarak kullanmak için. MFC/OLE1 uygulama olarak MFC 2.0 dahil MFC/OLE 2'ye unity'nin ve OLE 2'de kullanılabilen birçok OLE özellikler uygular, ardından genişletilmiş.

- [OCLIENT](../overview/visual-cpp-samples.md) OLE özelliklerin çoğu kapsayıcı açısından göstermek için gereken bir tek başına kapsayıcı uygulaması budur. MFC 2.0 ' çok alındığını ve ardından özel Pano biçimleri ve katıştırılmış öğelerine bağlantılar gibi daha gelişmiş OLE özelliklerin çoğunu destekleyecek şekilde genişletilmiş.

- [DRAWCLI](../overview/visual-cpp-samples.md) OCLIENT gibi bunu var olan bir nesne yönelimli çizim programında Framework'te yapar dışında bu uygulama OLE kapsayıcı desteği çok uygular. Size nasıl olabileceğiniz OLE kapsayıcı desteği uygulamak ve var olan uygulamanızla tümleştirme gösterir.

- [SUPERPAD](../overview/visual-cpp-samples.md) bu uygulama, hem de ince bir tek başına uygulama olduğunu da OLE sunucusu. Bunu uygulayan sunucu desteği oldukça minimal bir kullanım sağlar ' dir. İlginizi çeken nasıl verileri panoya kopyalamak için OLE Pano hizmetlerini kullandığını olmakla birlikte Pano Yapıştır işlevselliği uygulamak için yerleşik Windows "düzenleme" denetimine işlevselliğini kullanır. Bu yeni OLE API'leri ile tümleştirme yanı sıra geleneksel Windows API kullanımı ilgi çekici bir karışımını gösterir.

Örnek uygulamalar hakkında daha fazla bilgi için "MFC örnek Yardım" konusuna bakın.

## <a name="case-study-oclient-from-mfc-20"></a>Örnek Olay İncelemesi: MFC 2.0 OCLIENT

Yukarıda açıklandığı gibi [OCLIENT](../overview/visual-cpp-samples.md) MFC 2.0 sürümünde eklenmiştir ve OLE MFC/OLE1 ile uygulanır. Bu uygulamanın başlangıçta MFC/OLE 2 sınıflarını kullanmak için dönüştürüldü adımlar aşağıda açıklanmıştır. MFC/OLE sınıfları daha iyi anlamak için başlangıç bağlantı noktası tamamlandıktan sonra birçok özellik eklendi. Bu özellikler burada ele alınacak değil; Bu gelişmiş özellikleri hakkında daha fazla bilgi için örnek kendisini bakın.

> [!NOTE]
> Derleyici hataları ve adım adım işlemi Visual C++ 2.0 ile oluşturuldu. Visual C++ 4.0 ile belirli hata iletileri ve konumlar değişmiş olabilir, ancak kavramsal bilgileri geçerli kalır.

## <a name="getting-it-up-and-running"></a>Kullanmaya başlamak ve çalıştırmak

MFC/OLE OCLIENT örnek bağlantı noktası için uygulanan yaklaşıma, onu oluşturmak ve neden olabilecek belirgin derleyici hataları düzelttikten başlamaktır. MFC 2. 0 OCLIENT örnek alın ve MFC'nin bu sürümünü altında derlemek, çözmek için çok sayıda hata olmadığını bulabilirsiniz. Sırada gerçekleşen hataları aşağıda açıklanmıştır.

## <a name="compile-and-fix-errors"></a>Derleme ve düzeltme hataları

```Output
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters
```

İlk hata endişelere yer bırakmadan `COleClientItem::Draw`. MFC/OLE1 MFC/OLE sürüm alır çok daha fazla parametre sürdü. Ek parametreleri, gerekli ve genellikle NULL (Bu örnekte) olduğu gibi değildir. İçin çizilmiş CDC meta dosyası DC olduğunda MFC'nin bu sürümünü lpWBounds için değerleri otomatik olarak belirleyebilirsiniz. Framework "özniteliğini DC" geçirilen pDC birinden oluşturacaksınız olduğundan buna pFormatDC parametresi artık gerekli değildir. Bu sorunu gidermek için yalnızca iki kaldırmak için ek, çizim çağrısı parametreleri NULL.

```Output
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier
\oclient\mainview.cpp(273) : error C2057: expected constant expression
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
```

Olgu sonuçtan yukarıdaki hataları, tüm `COleClientItem::CreateXXXX` MFC/OLE1 işlevlerde gerekli öğeyi temsil etmek için benzersiz bir ad geçirilmesi. Bu gereksinim temel alınan OLE API değildi. OLE 2 (DDE konuşmalardaki adı kullanılır) temel iletişim mekanizması olarak DDE kullanmadığından bu MFC/OLE 2'de gerekli değildir. Bu sorunu gidermek için kaldırabilirsiniz `CreateNewName` tüm başvuruları yanı sıra işlev. Hangi her MFC/OLE işlevi bu sürümde yalnızca çağrıda imleci yerleştirerek ve F1 tuşuna basarak bekliyor bulmak daha kolaydır.

Önemli ölçüde farklı olduğu başka bir OLE 2 Pano işleme alanıdır. OLE1 ile Pano Windows panoyla etkileşim API'leri kullanılır. OLE 2 ile bu farklı bir mekanizma ile gerçekleştirilir. MFC/OLE1 API'leri kopyalamadan önce panonun açık olduğu varsayıldı bir `COleClientItem` panoya nesne. Bu, artık gerekli değildir ve tüm MFC/OLE Panosu işlemlerinin başarısız olmasına neden olur. Bağımlılıkları kaldırmak için kodu düzenlerken `CreateNewName`, ayrıca açılır ve Windows Pano kapatır kodu kaldırmanız gerekir.

```Output
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function
\oclient\mainview.cpp(344) : error C2057: expected constant expression
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'
```

Bu hataların sonucunda `CMainView::OnInsertObject` işleyici. "Yeni Nesne Ekle" komutu işlenirken burada bir bit yapılan değişiklikler başka bir alandır. Bu durumda, yalnızca özgün uygulaması için yeni bir OLE kapsayıcı uygulaması AppWizard tarafından sağlanan birleştirmek en kolay yoldur. Aslında, bu diğer uygulamaları taşıma için uygulayabileceğiniz bir tekniktir. MFC/OLE1 ', "Nesne Ekle" iletişim kutusu çağrılarak görüntülenen `AfxOleInsertDialog` işlevi. Bu sürümde, oluşturun bir `COleInsertObject` iletişim nesnesi ve çağrı `DoModal`. Ayrıca, yeni OLE öğeleri ile oluşturulan bir **CLSID** classname dize yerine. Sonuç aşağıdakine benzer görünmelidir

```cpp
COleInsertDialog dlg;
if (dlg.DoModal() != IDOK)
    return;

BeginWaitCursor();

CRectItem* pItem = NULL;
TRY
{
    // First create the C++ object
    pItem = GetDocument()->CreateItem();
    ASSERT_VALID(pItem);

    // Initialize the item from the dialog data.
    if (!dlg.CreateItem(pItem))
        AfxThrowMemoryException();
            // any exception will do
    ASSERT_VALID(pItem);

    // run the object if appropriate
    if (dlg.GetSelectionType() == COleInsertDialog::createNewItem)
        pItem->DoVerb(OLEIVERB_SHOW, this);

    // update right away
    pItem->UpdateLink();
    pItem->UpdateItemRectFromServer();

    // set selection to newly inserted item
    SetSelection(pItem);
    pItem->Invalidate();
}
CATCH (CException, e)
{
    // clean up item
    if (pItem != NULL)
        GetDocument()->DeleteItem(pItem);

    AfxMessageBox(IDP_FAILED_TO_CREATE);
}
END_CATCH

EndWaitCursor();
```

> [!NOTE]
> Yeni nesne eklemeyi, uygulamanız için farklı olabilir):

Eklenecek gereklidir \<afxodlgs.h >, bildirimi içeren `COleInsertObject` iletişim kutusu sınıfı ve bunun yanı sıra MFC tarafından sağlanan diğer standart iletişim kutuları.

```Output
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters
```

Kavram, bunlar aynı olsa da bu hataları olarak bazı OLE1 sabitleri OLE 2'de, değişen kaynaklanır. Bu durumda `OLEVERB_PRIMARY` değiştirildi `OLEIVERB_PRIMARY`. Kullanıcı bir öğeyi tıklattığında OLE1 ve OLE 2'de birincil fiil genellikle bir kapsayıcı tarafından yürütülür.

Ayrıca, `DoVerb` artık ek bir parametre alır; bir görünüm için bir işaretçi (`CView`*). Bu parametre, yalnızca "Görsel düzenleme" (veya yerinde etkinleştirme) uygulamak için kullanılır. Bu özellik şu anda uyguladığınız değil çünkü şu an için bu parametre NULL olarak ayarlayın.

Framework hiçbir zaman girişimleri yerinde etkinleştirme emin olmak için ' ı geçersiz kılmalıdır `COleClientItem::CanActivate` gibi:

```cpp
BOOL CRectItem::CanActivate()
{
    return FALSE;
}
```

```Output
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function
```

MFC/OLE1 içinde `COleClientItem::GetBounds` ve `SetBounds` sorgulamak ve bir öğenin kapsamını işlemek için kullanılan ( `left` ve `top` üyeleri olan her zaman sıfır). MFC/OLE 2'de bu daha doğrudan tarafından desteklenen `COleClientItem::GetExtent` ve `SetExtent`, ile ilgili bir **BOYUTU** veya `CSize` yerine.

Yeni, SetItemRectToServer kodunu ve UpdateItemRectFromServer çağrıları şuna benzeyebilir:

```cpp
BOOL CRectItem::UpdateItemRectFromServer()
{
    ASSERT(m_bTrackServerSize);
    CSize size;
    if (!GetExtent(&size))
        return FALSE;    // blank

    // map from HIMETRIC to screen coordinates
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.LPtoDP(&size);
    }
    // just set the item size
    if (m_rect.Size() != size)
    {
        // invalidate the old size/position
        Invalidate();
        m_rect.right = m_rect.left + size.cx;
        m_rect.bottom = m_rect.top + size.cy;
        // as well as the new size/position
        Invalidate();
    }
    return TRUE;
}

BOOL CRectItem::SetItemRectToServer()
{
    // set the official bounds for the embedded item
    CSize size = m_rect.Size();
    {
        CClientDC screenDC(NULL);
        screenDC.SetMapMode(MM_HIMETRIC);
        screenDC.DPtoLP(&size);
    }
    TRY
    {
        SetExtent(size);    // may do a wait
    }
    CATCH(CException, e)
    {
        return FALSE;  // links will not allow SetBounds
    }
    END_CATCH
    return TRUE;
}
```

```Output
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function
```

MFC/OLE1 zaman uyumlu API çağrıları bir sunucu kapsayıcı olan *sanal*, OLE1 çoğu durumda zaman uyumsuz nitelikte. Kullanıcı komutları işlenmeden önce devam eden zaman uyumsuz bir bekleyen çağrı denetlemek gerekliydi. MFC/OLE1 sağlanan `COleClientItem::InWaitForRelease` Bunu yapmak için işlevi. Tümünü bir araya CMainFrame içinde geçersiz kılmasını OnCommand kaldırılacak şekilde MFC/OLE 2'de bu gerekli değildir.

Bu noktada OCLIENT derleme bağlama ve.

## <a name="other-necessary-changes"></a>Diğer gerekli değişiklikleri

OCLIENT çalışmasını, ancak saklanacak değil yapılan bazı noktalar vardır. Artık yerine daha sonra bu sorunları gidermek daha iyidir.

İlk olarak, OLE kitaplıklarını Başlat gereklidir. Bu çağrılarak gerçekleştirilir `AfxOleInit` gelen `InitInstance`:

```cpp
if (!AfxOleInit())
{
    AfxMessageBox("Failed to initialize OLE libraries");
    return FALSE;
}
```

Sanal işlevler için parametre listesi değişiklikleri denetlemek için de iyi bir fikirdir. Bir işlev, `COleClientItem::OnChange`, her MFC/OLE kapsayıcı uygulamasında geçersiz kılınmış. Çevrimiçi Yardım'a bakarak bir ek 'DWORD dwParam' eklendiğini görürsünüz. Yeni CRectItem::OnChange şu şekilde görünür:

```cpp
void
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)
{
    if (m_bTrackServerSize && !UpdateItemRectFromServer())
    {
        // Blank object
        if (wNotification == OLE_CLOSED)
        {
            // no data received for the object - destroy it
            ASSERT(!IsVisible());
            GetDocument()->DeleteItem(this);
            return; // no update (item is gone now)
        }
    }
    if (wNotification != OLE_CLOSED)
        Dirty();
    Invalidate();
    // any change will cause a redraw
}
```

MFC/OLE1, kapsayıcılı uygulamaları belge sınıfından türetilmiş `COleClientDoc`. MFC/OLE 2'de bu sınıf olduğundan kaldırılmış ve yerine `COleDocument` (Bu yeni bir kuruluş, kapsayıcı/sunucu uygulamaları oluşturma kolaylaştırır). Var olan bir **#define** eşleyen `COleClientDoc` için `COleDocument` MFC/OLE1 uygulamaların OCLIENT gibi MFC/OLE 2'ye taşıma basitleştirmek için. Tarafından sağlanmayan özelliklerinden birini `COleDocument` tarafından sağlandı `COleClientDoc` eşleme girişleri standart bir komut iletisiyse. Bunu yapıldığını de, sunucu uygulamaları, `COleDocument` kapsayıcı/sunucu uygulaması olmadıkları sürece (dolaylı olarak), bunları bu komut işleyicileri yükü taşımaz. CMainDoc ileti eşlemesi için aşağıdaki girişleri ekleyin yapmanız gerekir:

```cpp
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)
```

Bu komutların tümü uygulamasının bulunduğu `COleDocument`, belgeniz için temel sınıf.

Bu noktada, OCLIENT işlevsel bir OLE kapsayıcı uygulaması değil. Herhangi bir türde (OLE1 veya OLE 2) öğeleri eklemek mümkündür. Yerinde etkinleştirmesi için gereken kodu uygulanmamış olduğundan, öğeleri ile OLE1 çok gibi ayrı bir pencerede düzenlenmiştir. Sonraki bölümde (bazen "Görsel düzenleme" olarak adlandırılır) yerinde düzenlemeyi etkinleştirmek için gerekli değişiklikleri açıklar.

## <a name="adding-visual-editing"></a>"Görsel düzenleme" ekleme

OLE en ilginç özelliklerinin yerinde etkinleştirme (veya "Görsel düzenleme") biridir. Bu özellik, kapsayıcının kullanıcı arabirimi bölümlerini sağlanan için daha sorunsuz bir düzenleme arabirimi kullanıcıya almak sunucu uygulaması sağlar. Yerinde etkinleştirme OCLIENT uygulamak için bazı özel kaynakların yanı sıra bazı ek kod eklenmesi gerekir. Bu kaynaklar ve kod normalde AppWizard tarafından sağlanan — aslında, kodu buraya çoğunu doğrudan bir uygulamadan yeni AppWizard "Container" desteğiyle ödünç.

Öncelikle, yerinde etkin olan bir öğe olduğunda kullanılacak bir menü kaynağı eklemek gereklidir. IDR_OCLITYPE kaynak kopyalama ve tüm dosya ve pencere pencereleri kaldırarak, bu ek menü kaynağı Visual C++'da oluşturabilirsiniz. İki ayırıcı çubukları grupları ayrımı belirtmek için dosya ve pencere pencereleri arasında eklenir (gibi görünmelidir: Dosya &#124; &#124; pencere). Bu ayırıcılar anlamı ve nasıl sunucusu ve menüler birleştirilir hakkında daha fazla bilgi için bkz [menüler ve kaynaklar: Menü birleştirme](../mfc/menus-and-resources-menu-merging.md).

Oluşturulan bu menüleri oluşturduktan sonra bunları hakkında bilmeniz framework izin gerekir. Bu çağrılarak gerçekleştirilir `CDocTemplate::SetContainerInfo` belge şablonu listesine, Initınstance'a eklemeden önce belge şablonu için. Belge şablonu kaydetmek için yeni kod şöyle görünür:

```cpp
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE,
    RUNTIME_CLASS(CMainDoc),
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```

Visual c++'ta oluşturulan özel yerinde kaynak IDR_OLECLITYPE_INPLACE kaynaktır.

Yerinde etkinleştirme etkinleştirmek için her ikisini birden değiştirmek için gereken bazı şeyler vardır `CView` (CMainView) türetilmiş sınıf yanı sıra `COleClientItem` türetilmiş bir sınıf (CRectItem). Tüm bu geçersiz kılmaları AppWizard tarafından sağlanır ve uygulamalarının çoğu, doğrudan bir varsayılan AppWizard uygulamasından gelir.

Bu bağlantı noktasının ilk adımda tamamen geçersiz kılarak yerinde etkinleştirmeyi devre dışı `COleClientItem::CanActivate`. Yerinde etkinleştirme izin vermek için bu geçersiz kılma kaldırılması gerekir. Ayrıca, tüm çağrıları için NULL geçirildi `DoVerb` (vardır iki tanesi) bir görünüm yalnızca yerinde etkinleştirme için gerekli olduğundan. Yerinde etkinleştirme tam olarak uygulamak için doğru görünümünde geçirmek için gerekli olduğu `DoVerb` çağırın. Bu çağrılar biri de `CMainView::OnInsertObject`:

```cpp
pItem->DoVerb(OLEIVERB_SHOW, this);
```

Başka bir yer `CMainView::OnLButtonDblClk`:

```cpp
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```

Geçersiz kılmak gerekli olan `COleClientItem::OnGetItemPosition`. Bu sunucu öğesi yerinde etkin olduğunda, kendi penceresini kapsayıcının penceresiyle ilişkili yerleştirmek istediğiniz yeri bildirir. OCLIENT için uygulama kısmı oldukça kolaydır:

```cpp
void CRectItem::OnGetItemPosition(CRect& rPosition)
{
    rPosition = m_rect;
}
```

Çoğu sunucuları da "yeniden boyutlandırma yerinde." olarak adlandırılan uygulama Bu sunucu boyutlandırılmış ve kullanıcı, öğeyi düzenleme sırasında taşınan pencereye sağlar. Taşıma veya bir pencere genellikle yeniden boyutlandırma konumunu ve boyutunu kapsayıcı belge içinde etkilediği kapsayıcı içinde bu eylemi, katılım göstermesi gerekir. Logrequest olayını OCLIENT yeni konumu ve boyutu ile m_rect tarafından tutulan iç dikdörtgen eşitler.

```cpp
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)
{
    ASSERT_VALID(this);

    if (!COleClientItem::OnChangeItemPosition(rectPos))
        return FALSE;

    Invalidate();
    m_rect = rectPos;
    Invalidate();
    GetDocument()->SetModifiedFlag();

    return TRUE;
}
```

Bu noktada, yerinde etkin ve etkin olduğunda, öğeyi taşıma ve boyutlandırma ile dağıtılacak öğeyi izin vermek için yeterli kod yoktur, ancak hiçbir kod düzenleme oturumu çıkmak kullanıcı izin verir. Bazı sunucular bu işlevselliği kendilerini escape tuşu işleyerek sağlayacak olsa da, kapsayıcıları öğeyi devre dışı bırakmak için iki yol sağladığını önerilir: (1) öğe dışında ve (2) ESCAPE tuşuna basarak tıklayarak.

Çıkış anahtarı için bir komuta VK_ESCAPE tuşu eşleştiren Visual C++ ile bir Hızlandırıcı ekleyin, ID_CANCEL_EDIT kaynaklarına eklenir. Bu komutun işleyicisi aşağıdaki gibidir:

```cpp
// The following command handler provides the standard
// keyboard user interface to cancel an in-place
// editing session.void CMainView::OnCancelEdit()
{
    // Close any in-place active item on this view.
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->Close();
    ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);
}
```

Burada kullanıcı dışındaki bir öğeye tıkladığında durumu işlemek için aşağıdaki kodu başlangıcına kadar eklemeniz `CMainView::SetSelection`:

```cpp
if (pNewSel != m_pSelection || pNewSel == NULL)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL&& pActiveItem != pNewSel)
        pActiveItem->Close();
}
```

Bir öğenin yerinde etkin olduğunda, odağı olması gerekir. Bu durumda olduğundan emin olmak için görünümünüzü odağı aldığında odağı her zaman etkin öğesine aktarılır, böylece OnSetFocus işler:

```cpp
// Special handling of OnSetFocus and OnSize are required
// when an object is being edited in-place.
void CMainView::OnSetFocus(CWnd* pOldWnd)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);

    if (pActiveItem != NULL &&
        pActiveItem->GetItemState() == COleClientItem::activeUIState)
    {
        // need to set focus to this item if it is same view
        CWnd* pWnd = pActiveItem->GetInPlaceWindow();
        if (pWnd != NULL)
        {
            pWnd->SetFocus();   // don't call the base class
            return;
        }
    }

    CView::OnSetFocus(pOldWnd);
}
```

Görünümü yeniden boyutlandırıldığında dikdörtgen kırpımını değişti etkin öğeyi bildirmek gerekir. Bunu sağlamak için bir işleyici yapmak için `OnSize`:

```cpp
void CMainView::OnSize(UINT nType, int cx, int cy)
{
    CView::OnSize(nType, cx, cy);
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL)
        pActiveItem->SetItemRects();
}
```

## <a name="case-study-hiersvr-from-mfc-20"></a>Örnek Olay İncelemesi: MFC 2.0 HIERSVR

[HIERSVR](../overview/visual-cpp-samples.md) OLE MFC/OLE1 ile uygulanan ve MFC 2. 0'da eklenmiştir. Bu Not, bu uygulamanın başlangıçta MFC/OLE 2 sınıflarını kullanmak için dönüştürüldü adımları kısaca açıklanmaktadır. MFC/OLE 2 sınıfları daha iyi anlamak için başlangıç bağlantı noktası tamamlandıktan sonra birçok özellik eklendi. Bu özellikler burada ele alınacak değil; Bu gelişmiş özellikleri hakkında daha fazla bilgi için örnek kendisini bakın.

> [!NOTE]
> Derleyici hataları ve adım adım işlemi Visual C++ 2.0 ile oluşturuldu. Visual C++ 4.0 ile belirli hata iletileri ve konumlar değişmiş olabilir, ancak kavramsal bilgileri geçerli kalır.

## <a name="getting-it-up-and-running"></a>Kullanmaya başlamak ve çalıştırmak

MFC/OLE HIERSVR örnek bağlantı noktası için uygulanan yaklaşıma, onu oluşturmak ve neden olabilecek belirgin derleyici hataları düzelttikten başlamaktır. MFC 2. 0 HIERSVR örnek alın ve MFC'nin bu sürümünü altında derlemek, (olsa da birden fazla OCLIENT örnekle) çözümlemek için birçok hata olmadığını bulabilirsiniz. Hataları, genellikle gerçekleştikleri sırada aşağıda açıklanmıştır.

## <a name="compile-and-fix-errors"></a>Derleme ve düzeltme hataları

```Output
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'
```

Bu ilk hata kadar büyük sorun kullanıma işaret `InitInstance` sunucuları için işlevi. OLE sunucusu için gerekli başlatma çalışmasını almak için MFC/OLE1 uygulamanız için yapmanız gereken en büyük değişikliklerin olabilir. Yapılacak en iyi şey ne AppWizard bir OLE sunucusu oluşturur arayın ve uygun şekilde kodunuzu değiştirmeniz ' dir. Aklınızda tutmanız gereken bazı noktalar şunlardır:

OLE kitaplıklarının çağırarak başlatmak gereklidir `AfxOleInit`

Belge şablonu nesne ile ayarlanamıyor çalışma zamanı sınıf bilgileri ve sunucu kaynak işler ayarlayın SetServerInfo çağırmak `CDocTemplate` Oluşturucusu.

Komut satırında/Embedding varsa, uygulamanızın ana pencereyi gösterme.

İhtiyacınız olacak bir **GUID** belgeniz için. Bu, belgenizin türü (128 bit) için benzersiz bir tanımlayıcıdır. AppWizard sizin için oluşturur — bunu burada açıklanan tekniği kullanırsanız, yeni kodu yeni oluşturulan AppWizard sunucu uygulamasından kopyalama, yalnızca "uygulama GUID'ini çalınacak". Aksi durumda, GUIDgen kullanabilirsiniz. BIN dizinindeki EXE yardımcı programı.

"Bağlanmak" gereklidir, `COleTemplateServer` çağırarak belge şablon nesnesine `COleTemplateServer::ConnectTemplate`.

Uygulamanızı bağımsız olarak çalıştırıldığında sistem kayıt defterini güncelleştirin. Kullanıcı taşınırsa bu şekilde. EXE uygulamanız için yeni konumundan çalıştıran Windows Sistem kayıt defteri veritabanında yeni konuma işaret edecek şekilde güncelleştirir.

Tüm bu değişiklikler ne AppWizard oluşturduğu üzerinde temel uyguladıktan sonra `InitInstance`, `InitInstance` (ve GUID ilgili) HIERSVR gibi okumalıdır için:

```cpp
// this is the GUID for HIERSVR documents
static const GUID BASED_CODE clsid =
{ 0xA0A16360L, 0xC19B, 0x101A, { 0x8C, 0xE5, 0x00, 0xDD, 0x01, 0x11, 0x3F, 0x12 } };

/////////////////////////////////////////////////////////////////////////////
// COLEServerApp initialization

BOOL COLEServerApp::InitInstance()
{
    // OLE 2 initialization
    if (!AfxOleInit())
    {
        AfxMessageBox("Initialization of the OLE failed!");
        return FALSE;
    }

    // Standard initialization
    LoadStdProfileSettings();   // Load standard INI file options

    // Register document templates
    CDocTemplate* pDocTemplate;
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,
        RUNTIME_CLASS(CServerDoc),
        RUNTIME_CLASS(CMDIChildWnd),
        RUNTIME_CLASS(CServerView));
    pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);
    AddDocTemplate(pDocTemplate);

    // create main MDI Frame window
    CMainFrame* pMainFrame = new CMainFrame;
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))
        return FALSE;
    m_pMainWnd = pMainFrame;

    SetDialogBkColor(); // gray look

    // enable file manager drag/drop and DDE Execute open
    m_pMainWnd->DragAcceptFiles();
    EnableShellOpen();

    m_server.ConnectTemplate(clsid, pDocTemplate, FALSE);
    COleTemplateServer::RegisterAll();

    // try to launch as an OLE server
    if (RunEmbedded())
    {
        // "short-circuit" initialization -- run as server!
        return TRUE;
    }
    m_server.UpdateRegistry();
    RegisterShellFileTypes();

    // not run as OLE server, so show the main window
    if (m_lpCmdLine[0] == '\0')
    {
        // create a new (empty) document
        OnFileNew();
    }
    else
    {
        // open an existing document
        OpenDocumentFile(m_lpCmdLine);
    }

    pMainFrame->ShowWindow(m_nCmdShow);
    pMainFrame->UpdateWindow();

    return TRUE;
}
```

Yukarıdaki kod yeni bir kaynak kimliği için IDR_HIERSVRTYPE_SRVR_EMB anlamına geldiğini göreceksiniz. Başka bir kapsayıcı içinde gömülü bir belge düzenlendiğinde kullanılacak menü kaynağı budur. MFC/OLE1 gömülü bir öğe düzenlemek için belirli menü öğelerinin çalışma sırasında değiştirildi. Bir dosya tabanlı belge düzenleme yerine gömülü bir öğe düzenlenirken bir tamamen farklı menüsü yapısı kullanarak bu iki ayrı modları için farklı kullanıcı arabirimleri sağlamak üzere kolaylaşır. Daha sonra göreceğiniz gibi bir katıştırılmış nesne yerinde düzenlenirken bir tamamen ayrı bir menü kaynağı kullanılır.

Bu kaynak oluşturmak için Visual C++'ta kaynak betiği yüklemeye ve mevcut IDR_HIERSVRTYPE menü kaynağı kopyalayın. Yeni kaynak için (Bu, AppWizard kullandığı aynı adlandırma kuralı) IDR_HIERSVRTYPE_SRVR_EMB yeniden adlandırın. "Dosya Kaydet" için "dosyayı güncelleştir"; Sonraki değişiklik Bu kimliği ıd_fıle_update komutu verin. Ayrıca "Dosyayı farklı kaydet" "Dosya kopyayı Farklı Kaydet için"; değiştirme Bu kimliği ıd_fıle_save_copy_as komutu verin. Framework uygulamasını bu komutların ikisi de sağlar.

```Output
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers
```

Geçersiz kılmasını kaynaklanan hataların birçok `OnSetData`, başvuran beri **OLESTATUS** türü. **OLESTATUS** OLE1 döndürülen hatalar vermiştir. Bu şekilde değiştirilmiştir **HRESULT** OLE 2'deki MFC genellikle dönüştürür ancak bir **HRESULT** içine bir `COleException` hata içeren. Bu örnekte, geçersiz kılmasını `OnSetData` kaldırmak için kolay bir şey yapmak için bu nedenle artık gerekli değildir.

```Output
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters
```

`COleServerItem` Oluşturucusu fazladan bir 'BOOL' parametresi alır. Bellek yönetimi üzerinde nasıl yapıldığını bu bayrağı belirler `COleServerItem` nesneleri. Bunu TRUE olarak ayarlandığında, bellek yönetimi, bu nesnelerin framework işler — bunlar artık gerekli olduğunda bunları siliniyor. HIERSVR kullanan `CServerItem` (türetilen `COleServerItem`) nesneler bu bayrağı FALSE olarak ayarlamanız, yerel veri parçası olarak. Bu, her bir sunucu öğesi silindiğinde belirlemek HIERSVR olanak tanır.

```Output
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
```

Bu hatalar da ifade ettiği şekilde CServerItem içinde geçersiz olmayan bazı 'saf sanal' işlevleri vardır. Büyük olasılıkla buna OnDraw'ın parametre listesi değişti olgusu neden olur. Bu hatayı düzeltmek için değiştirme `CServerItem::OnDraw` gibi (yanı sıra svritem.h bildiriminde):

```cpp
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)
{
    // request from OLE to draw node
    pDC->SetMapMode(MM_TEXT); // always in pixels
    return DoDraw(pDC, CPoint(0, 0), FALSE);
}
```

Yeni 'rSize' parametresidir. Bu, çizim boyutundaki doldurmak uygun değilse sağlar. Bu boyut olmalıdır **HIMETRIC**. Framework çağıran bu durumda, bu değer, doldurmak uygun değil, bu nedenle `OnGetExtent` uzantı alınamıyor. Uygulama, çalışması sahip olacaksınız `OnGetExtent`:

```cpp
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect, CSize& rSize)
{
    if (dwDrawAspect != DVASPECT_CONTENT)
        return COleServerItem::OnGetExtent(dwDrawAspect, rSize);

    rSize = CalcNodeSize();
    return TRUE;
}
```

```Output
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'
```

Öğe boyutunun dönüştürülür CServerItem::CalcNodeSize işlevinde **HIMETRIC** depolanan *m_rectBounds*. Belgelenmemiş '*m_rectBounds*' üyesi `COleServerItem` yok (ile kısmen değiştirilmiştir *m_sizeExtent*, ancak OLE 2'de bu üye değerindenbirazdahafarklıbirkullanım*m_rectBounds* OLE1 içinde yaptığınız). Ayar yerine **HIMETRIC** boyutu bu üye değişkeni, onu döneceksiniz. Bu dönüş değeri kullanılır `OnGetExtent`, daha önce uygulanmış.

```cpp
CSize CServerItem::CalcNodeSize()
{
    CClientDC dcScreen(NULL);

    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,
        m_strDescription.GetLength());
    m_sizeNode += CSize(CX_INSET * 2, CY_INSET * 2);

    // set suggested HIMETRIC size
    CSize size(m_sizeNode.cx, m_sizeNode.cy);
    dcScreen.SetMapMode(MM_HIMETRIC);
    dcScreen.DPtoLP(&size);
    return size;
}
```

Ayrıca CServerItem geçersiz kılar `COleServerItem::OnGetTextData`. Bu işlev, MFC/OLE kullanımdan kalkmıştır ve farklı bir mekanizma tarafından değiştirilir. MFC OLE örnek MFC 3.0 sürümünü [HIERSVR](../overview/visual-cpp-samples.md) geçersiz kılarak bu işlevselliğini uygular `COleServerItem::OnRenderFileData`. Bu işlev OnGetTextData geçersiz kılma kaldırabilmeniz için bu temel bağlantı noktası için önemli değil.

Ele alınmayan çok daha fazla hata svritem.cpp de vardır. Bunlar "gerçek" hatalar değildir — önceki hatalarının neden yalnızca hataları.

```Output
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters
```

`COleServerItem::CopyToClipboard` artık `bIncludeNative` bayrağı. İlk parametre kaldırmak için yerel veri (sunucu öğenin serileştirme işlevi tarafından yazılan veriler) her zaman kopyalanır. Ayrıca, `CopyToClipboard` FALSE döndürmek yerine bir hata meydana geldiğinde bir özel durum oluşturur. Kod için CServerView::OnEditCopy aşağıdaki gibi değiştirin:

```cpp
void CServerView::OnEditCopy()
{
    if (m_pSelectedNode == NULL)
        AfxThrowNotSupportedException();

    TRY
    {
        m_pSelectedNode->CopyToClipboard(TRUE);
    }
    CATCH_ALL(e)
    {
        AfxMessageBox("Copy to clipboard failed");
    }
    END_CATCH_ALL
}
```

Daha fazla hata oluştu daha OCLIENT aynı sürümü için HIERSVR MFC 2.0 sürümünü derlemeden kaynaklanan rağmen vardı gerçekten daha az değişiklik.

Bu noktada HIERSVR derleme ve bağlama ve OLE sunucusu olarak, ancak sonraki uygulanacak yerinde düzenleme özelliği işlev.

## <a name="adding-visual-editing"></a>"Görsel düzenleme" ekleme

Bu sunucu uygulaması için "Görsel düzenleme" (veya yerinde etkinleştirme) eklemek için ölçeklendirilmesini gereken yalnızca birkaç şey vardır:

- Öğesi yerinde etkin olduğunda kullanılacak bir özel menü kaynağı ihtiyacınız vardır.

- Bu nedenle yalnızca bir alt kümesi ile (yukarıda belirtilen menü kaynağı ile eşleşen) menü komutlarını sunucudan kullanılabilir eşleştirmek için normal araç çubuğu araç gerekir bu uygulama bir araç vardır.

- Türetilen bir yeni sınıf ihtiyacınız `COleIPFrameWnd` yerinde kullanıcı arabirimi sağlayan (benzer şekilde; CMainFrame, türetilen `CMDIFrameWnd`, MDI kullanıcı arabirimini sağlar).

- Bu özel kaynak ve sınıflarını hakkında framework söylemeniz gerekir.

Menü kaynağı oluşturmak kolaydır. Visual C++ çalıştırın, menü kaynağı IDR_HIERSVRTYPE IDR_HIERSVRTYPE_SRVR_IP adlı bir menü kaynağı kopyalayın. Yalnızca düzenleme ve Yardım menüsü açılır sol menü değiştirin. Düzenle ve Yardım menüler arasında menü iki ayırıcılar ekleyin (gibi görünmelidir: Düzen &#124; &#124; yardımcı). Bu ayırıcılar anlamı ve nasıl sunucusu ve menüler birleştirilir hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: Menü birleştirme](../mfc/menus-and-resources-menu-merging.md).

Alt araç çubuğu için bit eşlem işaretli bir "Sunucu" seçeneği ile yeni bir AppWizard tarafından oluşturulan uygulama adresinden kopyalayarak kolayca oluşturulabilir. Bu bit eşlem ardından Visual C++'ta içeri aktarılabilir. Bit eşlem, bir kimliği IDR_HIERSVRTYPE_SRVR_IP verdiğinizden emin olun.

Türetilen sınıfın `COleIPFrameWnd` sunucu desteği ile oluşturulan AppWizard uygulamadan kopyalanabilir. Her iki dosya IPFRAME kopyalayın. CPP ve IPFRAME. H ve bunları projeye ekleyin. Emin olun `LoadBitmap` IDR_HIERSVRTYPE_SRVR_IP, önceki adımda oluşturduğunuz bit eşlem çağrı başvurur.

Tüm sınıfları ve yeni kaynaklar oluşturulur, framework bunlar hakkında bilir (ve bu uygulama artık yerinde düzenleme desteklediğini biliyor) gerekli kodu ekleyin. Bu için bazı daha fazla parametre ekleyerek yapılır `SetServerInfo` Çağır `InitInstance` işlevi:

```cpp
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```

Şimdi, yerinde çalışmaya hazır tüm kapsayıcıdaki yerinde etkinleştirmeyi de destekler. Ancak, yine de kodda gizlenen bir küçük hata yoktur. Kullanıcının sağ fare düğmesine bastığında görüntülenen bir bağlam menüsü HIERSVR destekler. Bu menü HIERSVR tamamen açık, ancak bir gömme yerinde düzenlenirken çalışmaz çalışır. Nedeni bu tek satıra CServerView::OnRButtonDown kod sabitlenebilir:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```

Başvuru fark `AfxGetApp()->m_pMainWnd`. Sunucu yerinde etkin olduğunda, ana pencere vardır ve m_pMainWnd ayarlanır, ancak genellikle görünmez durumdadır. Bu pencereyi ayrıca başvuruyor *ana* uygulama penceresinin sunucu tam olarak olduğunda görüntülenen MDI çerçeve penceresinin açın veya tek başına çalıştırın. Etkin pencereyi başvurmuyor — yerinde zaman etkin olduğu bir çerçeve penceresi türetilen `COleIPFrameWnd`. Bile, düzenleme, yerinde MFC'nin bu sürümünü yeni bir işlev eklerse doğru etkin pencereyi almaya `AfxGetMainWnd`. Genellikle, bu işlevi yerine kullanması gerekir `AfxGetApp()->m_pMainWnd`. Bu kod şu şekilde değiştirmesi gerekir:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetMainWnd());
```

Artık işlevsel yerinde etkinleştirme için en düşük düzeyde etkin bir OLE sunucusu var. Ancak yine de birçok özellik MFC/OLE1 kullanılamayan MFC/OLE 2 ile kullanılabilir. HIERSVR örnek hakkında daha fazla fikir için uygulamak istediğiniz özelliklere bakın. HIERSVR uygulayan özelliklerinden bazıları aşağıda listelenmiştir:

- Kapsayıcıya göre doğru WYSIWYG davranışı için yakınlaştırma.

- Sürükle / bırak ve özel Pano biçimi.

- Kapsayıcı penceresi seçim olarak kaydırma değiştirilir.

MFC 3.0 HIERSVR örnek, biraz farklı bir tasarım, sunucu öğeleri için de kullanır. Bu işlem, bellek korunmasına yardımcı olur ve bağlantılarınızı daha esnek hale getirir. HIERSVR 2.0 sürümü ile ağacında her bir düğümü *olduğu bir* `COleServerItem`. `COleServerItem` kesinlikle gerekli her bu düğümler için olandan biraz daha fazla ek yük taşıyan ancak `COleServerItem` etkin her bağlantı için gereklidir. Ancak çoğunlukla, çok az sayıda etkin bağlantıların belirli bir zamanda. Bu daha verimli hale getirmek için MFC'nin bu sürümünü, HIERSVR düğümden ayıran `COleServerItem`. Hem bir CServerNode sahiptir ve `CServerItem` sınıfı. `CServerItem` (Türetilen `COleServerItem`) yalnızca gerektiğinde oluşturulur. Bu belirli düğüm, belirli bağlantı kullanarak kapsayıcı (veya kapsayıcıları) durdurduktan sonra CServerNode ile ilişkili CServerItem nesnesi silindi. Bu, daha verimli ve daha esnek tasarımdır. Esnek birden fazla seçim bağlantıları ile ilgilenirken halinde sunulur. Bu iki HIERSVR sürümleri hiçbiri birden fazla seçimi destekler, ancak çok daha kolay eklemek için (ve bu seçimleri bağlantılarını desteklemek için) HIERSVR, MFC 3.0 sürümü ile bu yana `COleServerItem` yerel verileri ayrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
