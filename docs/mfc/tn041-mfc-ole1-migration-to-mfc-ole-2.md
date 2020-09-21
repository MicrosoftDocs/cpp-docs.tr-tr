---
title: "TN041: MFC-OLE1-OLE 2 ' ye geçiş"
ms.date: 10/18/2018
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
ms.openlocfilehash: 7d0381983481278b1410ae0ff11463519d4cbb34
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743158"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041: MFC/OLE 2'ye MFC/OLE1 Geçişi

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

## <a name="general-issues-relating-to-migration"></a>Geçişle Ilgili genel sorunlar

MFC 2,5 (ve üzeri) içindeki OLE 2 sınıfları için tasarım hedeflerinden biri, OLE 1,0 desteği için MFC 2,0 ' de aynı mimarinin büyük bir kısmını korumıştı. Sonuç olarak, MFC 2,0 ' de aynı OLE sınıflarının çoğu MFC 'nin bu sürümünde (,, `COleDocument` `COleServerDoc` `COleClientItem` ,) hala bulunur `COleServerItem` . Ayrıca, bu sınıflardaki API 'lerin birçoğu tamamen aynıdır. Ancak, OLE 2 büyük ölçüde OLE 1,0 ' den farklıdır, bu sayede bazı ayrıntıların değiştiğini bekleyebilir. MFC 2.0 'ın OLE1 desteği hakkında bilgi sahibiyseniz, MFC 'nin 2,0 desteğiyle evle karşılaşırsınız.

Var olan bir MFC/OLE1 uygulaması çekiyorsunuz ve buna OLE 2 işlevselliği ekliyorsanız, önce bu notu okumanız gerekir. Bu notta OLE1 işlevlerinden MFC/OLE 2 ' ye taşıma sırasında karşılaşabileceğiniz bazı genel sorunlar ele alınmaktadır ve MFC 2,0: MFC OLE örnekleri [Oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md)'e dahil olmak üzere iki uygulama taşıma sırasında kapsanmamış sorunları ele alınmaktadır.

## <a name="mfc-documentview-architecture-is-important"></a>MFC belge/görünüm mimarisi önemlidir

Uygulamanız MFC 'nin belge/görünüm mimarisini kullanmıyorsa ve uygulamanıza OLE 2 desteği eklemek istiyorsanız, şimdi belge/görünüm 'e geçiş süresi. MFC 'nin OLE 2 sınıflarının avantajlarından birçoğu yalnızca uygulamanız yerleşik mimari ve MFC bileşenlerini kullanırken gerçekleştirilir.

MFC mimarisini kullanmadan bir sunucu veya kapsayıcı uygulamak mümkündür, ancak önerilmez.

## <a name="use-mfc-implementation-instead-of-your-own"></a>Kendi kendinize değil MFC uygulamasını kullanın

MFC "uygulama" sınıfları,, ve gibi `CToolBar` , `CStatusBar` `CScrollView` OLE 2 desteği için yerleşik özel durum koduna sahiptir. Bu nedenle, uygulamanızda bu sınıfları kullanacaksanız, OLE 'nin farkında olması için bu sınıfları bir araya getirme çabadan faydalanabilirsiniz. Yine, bu amaçlar için burada "kendi kendine al" sınıfları olabilir, ancak önerilmez. Benzer işlevselliği uygulamanız gerekiyorsa, MFC kaynak kodu, daha ayrıntılı OLE noktalarıyla (özellikle yerinde etkinleştirmeye geldiğinde) ilgilenmek için mükemmel bir başvurudur.

## <a name="examine-the-mfc-sample-code"></a>MFC örnek kodunu inceleme

OLE işlevselliği içeren bir dizi MFC örneği vardır. Bu uygulamaların her biri farklı bir açıda OLE uygular:

- [Hiersvr](../overview/visual-cpp-samples.md) Çoğunlukla sunucu uygulaması olarak kullanım içindir. MFC 2,0 ' ye MFC/OLE1 uygulaması olarak eklenmiştir ve MFC/OLE 2 ' ye ve OLE 2 ' de bulunan birçok OLE özelliğini uygulayan şekilde genişletilir.

- [Oclient](../overview/visual-cpp-samples.md) Bu tek başına kapsayıcı uygulamasıdır ve bir kapsayıcı açısından birçok OLE özelliğini göstermek anlamına gelir. Bu, MFC 2,0 ' den çok fazla yer aldığı ve özel Pano biçimleri ve katıştırılmış öğelerin bağlantıları gibi daha gelişmiş OLE özelliklerinin çoğunu destekleyecek şekilde genişletildi.

- [DRAWCLI](../overview/visual-cpp-samples.md) Bu uygulama, var olan nesne odaklı bir çizim programının çerçevesinde olması dışında, OCLIENT gibi OLE kapsayıcı desteğini uygular. OLE kapsayıcı desteğini nasıl uygulayabileceğinizi ve bunu mevcut uygulamanızla nasıl tümleştirileceğini gösterir.

- [Süper panel](../overview/visual-cpp-samples.md) Bu uygulamanın yanı sıra, iyi bir tek başına uygulama da bir OLE sunucusudur. Tarafından desteklenen sunucu, en az düzeyde bir değer kullanır. Bunun belirli bir ilgisi, verileri panoya kopyalamak için OLE panosu Hizmetleri 'ni kullanır, ancak Pano yapıştırma işlevselliği uygulamak için Windows "düzenleme" denetiminde yerleşik olarak bulunan işlevleri kullanır. Bu, geleneksel Windows API kullanımının ilginç bir karışımını ve yeni OLE API 'Leri ile tümleştirmeyi gösterir.

Örnek uygulamalar hakkında daha fazla bilgi için bkz. "MFC örnek yardımı".

## <a name="case-study-oclient-from-mfc-20"></a>Örnek olay Incelemesi: MFC 2,0 'den OCLIENT

Yukarıda açıklandığı gibi, [Oclient](../overview/visual-cpp-samples.md) MFC 2,0 ' ye EKLENMIŞTIR ve MFC/OLE1 Ile uygulanmış OLE. Bu uygulamanın başlangıçta MFC/OLE 2 sınıflarını kullanacak şekilde dönüştürüldüğü adımlar aşağıda açıklanmıştır. MFC/OLE sınıflarını daha iyi göstermek için ilk bağlantı noktası tamamlandıktan sonra bir dizi özellik eklenmiştir. Bu özellikler burada ele alınmayacak; Bu gelişmiş özellikler hakkında daha fazla bilgi için örneğe bakın.

> [!NOTE]
> Derleyici hataları ve adım adım işlem Visual C++ 2,0 ile oluşturulmuştur. Belirli hata iletileri ve konumlar Visual C++ 4,0 ile değişmiş olabilir, ancak kavramsal bilgiler geçerli kalır.

### <a name="getting-it-up-and-running"></a>Çalışmaya başlayın

OCLIENT örneği ile MFC/OLE arasında bağlantı kurmak için yapılan yaklaşım, onu oluşturup sonuçta ortaya kalacak açık derleyici hatalarını düzelterek başlamamalıdır. OCLIENT örneğini MFC 2,0 ' den alıp bu MFC 'nin bu sürümünde derlerseniz, çözülmesi gereken birçok hata olduğunu fark edeceksiniz. Oluşan sırada hatalar aşağıda açıklanmıştır.

### <a name="compile-and-fix-errors"></a>Hataları derleyin ve düzeltir

```Output
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters
```

İlk hata kaygılarıyla ilgilidir `COleClientItem::Draw` . MFC/OLE1 içinde, MFC/OLE sürümünden daha fazla parametre alır. Ek parametreler genellikle gerekli değildir ve genellikle NULL (Bu örnekte olduğu gibi). Bu MFC sürümü, çizmekte olan CDC bir meta dosya DC 'si olduğunda, Lpwlimitlerinizin değerlerini otomatik olarak belirleyebilir. Ayrıca, çerçeve geçirilen pDC 'nin "Attribute DC" öğesinden bir tane oluşturacak olduğundan pFormatDC parametresi artık gerekli değildir. Bu sorunu gidermek için, çizim çağrısına iki ek NULL parametre kaldırmanız yeterlidir.

```Output
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier
\oclient\mainview.cpp(273) : error C2057: expected constant expression
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '
```

Yukarıdaki hatalar, `COleClientItem::CreateXXXX` MFC/OLE1 'deki tüm işlevlerin öğeyi göstermek için benzersiz bir ad geçirilmesini gerektirmesinden kaynaklanır. Bu, temel alınan OLE API 'SI gereksinimiydi. Bu, MFC/OLE 2 ' de gerekli değildir, çünkü OLE 2 temel iletişim mekanizması olarak DDE 'yi kullanmaz (ad, DDE konuşmalarında kullanılmıştır). Bu sorunu gidermek için, `CreateNewName` işlevin tüm başvurularını da kaldırabilirsiniz. Her MFC/OLE işlevinin bu sürümde ne kadar beklenmekte olduğunu kolayca bulmak için imlecinizi çağrıya yerleştirip F1 tuşuna basın.

Önemli ölçüde farklı olan başka bir alan OLE 2 Pano işleme ' dir. OLE1 ile Windows Pano API 'Leri, pano ile etkileşime geçin. OLE 2 ile bu işlem farklı bir mekanizmasıyla yapılır. MFC/OLE1 API 'Leri Pano 'ya bir nesne kopyalamadan önce panonun açık olduğunu varsaymıştı `COleClientItem` . Bu artık gerekli değildir ve tüm MFC/OLE panosu işlemlerinin başarısız olmasına neden olur. Bağımlılıkları kaldırmak için kodu düzenlerken `CreateNewName` , açılan kodu da kaldırmanız ve Windows panosunu kapatmalısınız.

```Output
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function
\oclient\mainview.cpp(344) : error C2057: expected constant expression
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'
```

Bu hatalar `CMainView::OnInsertObject` işleyicinin sonucu. "Yeni nesne Ekle" komutunun işlenmesi, nesnelerin oldukça bir bit olarak değiştiği başka bir alandır. Bu durumda, yeni bir OLE kapsayıcı uygulaması için AppWizard tarafından sağlanarak özgün uygulamayı birleştirmek basit bir yoldur. Aslında bu, diğer uygulamaların taşıma için uygulayabileceğiniz bir tekniktir. MFC/OLE1 'de, işlevi çağırarak "nesne Ekle" iletişim kutusunu görüntülen `AfxOleInsertDialog` . Bu sürümde bir `COleInsertObject` iletişim kutusu nesnesi ve çağrısı oluşturursunuz `DoModal` . Ayrıca, yeni OLE öğeleri ClassName dizesi yerine bir **CLSID** ile oluşturulur. Nihai sonuç şuna benzer görünmelidir

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
> Yeni nesne ekleme uygulamanız için farklı olabilir):

Ayrıca \<afxodlgs.h> , `COleInsertObject` iletişim kutusu SıNıFıNıN ve MFC tarafından sunulan diğer standart iletişim kutularının bildirimini içeren dahil etmek de gereklidir.

```Output
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters
```

Bu hatalar, bazı OLE1 sabitlerinin OLE 2 ' de değiştiği, ancak aynı olsa da kavram nedeniyle oluşur. Bu durumda `OLEVERB_PRIMARY` olarak değiştirilmiştir `OLEIVERB_PRIMARY` . Hem OLE1 hem de OLE 2 ' de, birincil fiil genellikle Kullanıcı bir öğeye çift tıkladığında bir kapsayıcı tarafından yürütülür.

Ayrıca, bir `DoVerb` görünümün işaretçisi (*) için de ek bir parametre alır `CView` . Bu parametre yalnızca "görsel düzenlemeler" (veya yerinde etkinleştirme) uygulamak için kullanılır. Şimdilik bu özelliği şu anda uygulamadığınıza göre bu parametreyi NULL olarak ayarlarsınız.

Framework 'ün hiç yerinde etkinleştirmeye hiçbir şekilde Denemeyeceğinden emin olmak için aşağıdaki gibi geçersiz kılmanız gerekir `COleClientItem::CanActivate` :

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

MFC/OLE1 içinde `COleClientItem::GetBounds` ve `SetBounds` bir öğenin kapsamını sorgulamak ve işlemek için kullanılmıştı ( `left` ve `top` üyeleri her zaman sıfırdır). MFC/OLE 2 ' de, ve tarafından daha doğrudan desteklenerek `COleClientItem::GetExtent` `SetExtent` bir **Boyut** veya `CSize` bunun yerine.

Yeni SetItemRectToServer ve UpdateItemRectFromServer çağrılarınızın kodu şöyle görünür:

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

MFC/OLE1 zaman uyumlu API çağrıları, bir kapsayıcıdan sunucuya yönelik olarak zaman uyumsuz olduğundan, çoğu durumda OLE1 *doğal olarak zaman*uyumsuzdur. Kullanıcıdan komutları işlemeden önce, bekleyen bir zaman uyumsuz çağrının denetlenmesi gerekir. MFC/OLE1 bunu `COleClientItem::InWaitForRelease` yapmak için işlevi sağladı. MFC/OLE 2 ' de gerekli değildir, bu nedenle Canabilgisayar 'teki OnCommand 'in hepsini birlikte geçersiz kılmayı kaldırabilirsiniz.

Bu noktada OCLIENT, derlenir ve bağlanır.

### <a name="other-necessary-changes"></a>Diğer gerekli değişiklikler

Ancak, OCLIENT 'ın çalışmasını engelleyen çok sayıda şey vardır. Bu sorunların daha sonra yerine daha sonra düzeltilmesi daha iyidir.

İlk olarak, OLE kitaplıklarının başlatılması gerekir. Bu, öğesinden çağırarak yapılır `AfxOleInit` `InitInstance` :

```cpp
if (!AfxOleInit())
{
    AfxMessageBox("Failed to initialize OLE libraries");
    return FALSE;
}
```

Ayrıca, parametre listesi değişikliklerine yönelik sanal işlevleri denetlemek de iyi bir fikirdir. Bu tür bir işlev `COleClientItem::OnChange` , her MFC/OLE kapsayıcı uygulamasında geçersiz kılınır. Çevrimiçi yardım 'a bakarak fazladan bir ' DWORD dwParam ' eklendiğini görürsünüz. Yeni CRectItem:: OnChange şöyle görünür:

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

MFC/OLE1 içinde, kapsayıcı uygulamaları belge sınıfının öğesinden türetilir `COleClientDoc` . MFC/OLE 2 ' de bu sınıf tarafından kaldırılmıştır ve değiştirilmiştir `COleDocument` (Bu yeni kuruluş, kapsayıcı/sunucu uygulamaları oluşturmayı kolaylaştırır). **#define** `COleClientDoc` `COleDocument` MFC/OLE1 UYGULAMALARıNıN OCLIENT gibi MFC/OLE 2 ' ye taşıma işlemini basitleştirmek için ile eşleyen bir #define vardır. Tarafından sağlanan özelliklerden biri `COleDocument` `COleClientDoc` , standart komut ileti eşleme girişlarıdır. Bu işlem, `COleDocument` bir kapsayıcı/sunucu uygulaması olmadıkları müddetçe, (dolaylı olarak) da kullanan sunucu uygulamalarının bu komut işleyicilerinin ek yükü ile birlikte kalmaması için yapılır. CMainDoc ileti eşlemesine aşağıdaki girdileri eklemeniz gerekir:

```cpp
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)
```

Bu komutların tümü `COleDocument` , belgeniz için temel sınıf olan ' de bulunur.

Bu noktada, OCLIENT, işlevsel bir OLE kapsayıcı uygulamasıdır. Herhangi bir türde öğe eklemek mümkündür (OLE1 veya OLE 2). Yerinde etkinleştirmeyi etkinleştirmek için gerekli kod uygulanmadığından, öğeler OLE1 ile benzer şekilde ayrı bir pencerede düzenlenir. Sonraki bölümde, yerinde düzenlemenin (bazen "görsel düzenlemeler" olarak adlandırılır) etkinleştirilmesi için gerekli değişiklikler açıklanmaktadır.

### <a name="adding-visual-editing"></a>"Görsel düzenlemesi" ekleniyor

OLE 'nin en ilginç özelliklerinden biri yerinde etkinleştirme (veya "görsel düzenlemeler") ' dir. Bu özellik, sunucu uygulamasının Kullanıcı için daha sorunsuz bir düzen arabirimi sağlamak üzere kapsayıcının Kullanıcı arabiriminin bölümlerini almasına izin verir. OCLIENT 'a yerinde etkinleştirme uygulamak için bazı özel kaynakların yanı sıra bazı ek kodlar eklenmesi gerekir. Bu kaynaklar ve kod normalde AppWizard tarafından sağlanır. Aslında, buradaki kodun çoğu, doğrudan "kapsayıcı" desteği olan yeni bir AppWizard uygulamasından kullanıma sunulmuştur.

Birincisi, yerinde etkin olan bir öğe olduğunda kullanılacak bir menü kaynağı eklemek gereklidir. Bu ek menü kaynağını, IDR_OCLITYPE kaynağını kopyalayarak ve dosya ve pencere açılır pencereleri hariç tüm dosyaları kaldırarak Visual C++ oluşturabilirsiniz. Grupların ayrılmasını göstermek için dosya ve pencere açılır pencereleri arasına iki ayırıcı çubuk eklenir (şuna benzemelidir: dosya &#124;&#124; penceresi). Bu ayırıcıların ne anlama geldiğini ve sunucu ve kapsayıcı menülerinin nasıl birleştirildiği hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: menü birleştirme](../mfc/menus-and-resources-menu-merging.md).

Bu menüler oluşturulduktan sonra Framework 'ün bunlarla ilgili bilgi sahibi olmanız gerekir. Bu, `CDocTemplate::SetContainerInfo` InitInstance 'inizdeki belge şablonu listesine eklemeden önce belge şablonu için çağrı yaparak yapılır. Belge şablonunu kaydetmek için yeni kod şöyle görünür:

```cpp
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE,
    RUNTIME_CLASS(CMainDoc),
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```

IDR_OLECLITYPE_INPLACE kaynak, Visual C++ oluşturulan özel yerinde kaynaktır.

Yerinde etkinleştirmeyi etkinleştirmek için, hem `CView` (CMainView) türetilmiş sınıfta hem de `COleClientItem` türetilmiş sınıfın (CRectItem) değiştirilmesi gereken bazı şeyler vardır. Bu geçersiz kılmaların tümü AppWizard tarafından sağlanır ve uygulamanın çoğu doğrudan varsayılan bir AppWizard uygulamasından gelir.

Bu bağlantı noktasının ilk adımında yerinde etkinleştirme tamamen geçersiz kılınarak devre dışı bırakıldı `COleClientItem::CanActivate` . Yerinde etkinleştirmeye izin vermek için bu geçersiz kılma kaldırılmalıdır. Buna ek olarak, `DoVerb` yalnızca yerinde etkinleştirme için gerekli olan tüm çağrılara (bunların ikisi de vardır) null geçildi. Yerinde etkinleştirmeyi tam olarak uygulamak için, çağrıda doğru görünümün iletilmesi gerekir `DoVerb` . Bu çağrılardan biri `CMainView::OnInsertObject` :

```cpp
pItem->DoVerb(OLEIVERB_SHOW, this);
```

Diğeri `CMainView::OnLButtonDblClk` :

```cpp
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```

Geçersiz kılınması gerekir `COleClientItem::OnGetItemPosition` . Bu, sunucuya, öğenin yerinde etkinleştirildiğinde, kapsayıcının penceresine göre ne zaman yerleştirileceğini belirtir. OCLIENT için uygulama, önemsiz:

```cpp
void CRectItem::OnGetItemPosition(CRect& rPosition)
{
    rPosition = m_rect;
}
```

Çoğu sunucu Ayrıca "yerinde yeniden boyutlandırma" olarak adlandırılan öğeleri de uygular. Bu, kullanıcı öğeyi düzenlenirken sunucu penceresinin boyutlandırılıp taşınmasını sağlar. Kapsayıcı bu eyleme katılmalıdır, çünkü pencereyi taşımak veya yeniden boyutlandırmak genellikle kapsayıcı belgesinin içindeki konumu ve boyutu etkiler. OCLIENT için uygulama, m_rect tarafından tutulan iç dikdörtgeni yeni konum ve boyutla eşitler.

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

Bu noktada, bir öğenin yerinde etkinleştirilmesi ve etkin olduğunda boyutlandırılması ve öğenin taşınması ile uğraşmak için yeterli kod vardır, ancak hiçbir kod kullanıcının düzenleyen oturumundan çıkmasına izin vermez. Bazı sunucular, kaçış anahtarını işleyerek bu işlevselliği kendi kendilerine sağlayabilse de, kapsayıcıların bir öğeyi devre dışı bırakmak için iki yol sağlaması önerilir: (1) öğenin dışına tıklayarak ve (2) KAÇıŞ tuşuna basarak.

KAÇıŞ anahtarı için VK_ESCAPE anahtarını bir komuta eşleyen Visual C++ bir Hızlandırıcı ekleyin ID_CANCEL_EDIT kaynaklara eklenir. Bu komutun işleyicisi şöyledir:

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

Kullanıcının öğenin dışına tıkladığı durumu işlemek için aşağıdaki kodu öğesinin başlangıcına ekleyin `CMainView::SetSelection` :

```cpp
if (pNewSel != m_pSelection || pNewSel == NULL)
{
    COleClientItem* pActiveItem =
        GetDocument()->GetInPlaceActiveItem(this);
    if (pActiveItem != NULL&& pActiveItem != pNewSel)
        pActiveItem->Close();
}
```

Bir öğe yerinde etkin olduğunda, odağa sahip olmalıdır. Bu durumda, görünümün odağı aldığında odağın her zaman etkin öğeye aktarılması için OnSetFocus 'yi işlediğinizden emin olun:

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

Görünüm yeniden boyutlandırılırken, kırpma dikdörtgeninin değiştiği etkin öğeyi bilgilendirmeli. Bunu yapmak için, için bir işleyici sağlarsınız `OnSize` :

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

## <a name="case-study-hiersvr-from-mfc-20"></a>Örnek olay Incelemesi: MFC 2,0 ile HIERSVR

[Hiersvr](../overview/visual-cpp-samples.md) , MFC 2,0 ' ye de EKLENMIŞTIR ve MFC/OLE1 Ile uygulanmış OLE. Bu notta, bu uygulamanın başlangıçta MFC/OLE 2 sınıflarını kullanacak şekilde dönüştürüldüğü adımlar kısaca açıklanmaktadır. MFC/OLE 2 sınıflarını daha iyi göstermek için ilk bağlantı noktası tamamlandıktan sonra bir dizi özellik eklenmiştir. Bu özellikler burada ele alınmayacak; Bu gelişmiş özellikler hakkında daha fazla bilgi için örneğe bakın.

> [!NOTE]
> Derleyici hataları ve adım adım işlem Visual C++ 2,0 ile oluşturulmuştur. Belirli hata iletileri ve konumlar Visual C++ 4,0 ile değişmiş olabilir, ancak kavramsal bilgiler geçerli kalır.

### <a name="getting-it-up-and-running"></a>Çalışmaya başlayın

HIERSVR örneğine yönelik bağlantı noktasına yapılan yaklaşım, MFC/OLE ile başlatılır ve sonuç olarak ortaya geçen belirgin Derleyici hatalarını düzelterek işe başlar. MFC 2,0 ' den HIERSVR örneğini alıp onu MFC 'nin bu sürümünde derlerseniz, çözmeniz gereken çok hata olmadığını (OCLIENT örneğiyle daha fazla olmasına rağmen) fark edersiniz. Hatalar, genellikle oluşma sırasına göre aşağıda açıklanmıştır.

### <a name="compile-and-fix-errors"></a>Hataları derleyin ve düzeltir

```Output
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'
```

Bu ilk hata, sunucular için işlevle çok daha büyük bir sorun olduğunu gösterir `InitInstance` . OLE sunucusu için gereken başlatma büyük olasılıkla MFC/OLE1 uygulamanızda yapmanız gereken en büyük değişikliklerden biridir. Yapmanız gereken en iyi şey, bir OLE sunucusu için AppWizard 'ın ne oluşturduğunu ve kodunuzun uygun şekilde nasıl değiştirileceğini göz atabilmenizdir. Aşağıda aklınızda bulundurmanız gereken bazı noktaları bulabilirsiniz:

Şunu çağırarak OLE kitaplıklarını başlatmak gereklidir `AfxOleInit`

Oluşturucu ile ayarlayamayacağı sunucu kaynak tutamaçlarını ve çalışma zamanı sınıfı bilgilerini ayarlamak için, belge şablonu nesnesinde SetServerInfo öğesini çağırın `CDocTemplate` .

Komut satırında/gömme varsa, uygulamanızın ana penceresini gösterme.

Belgeniz için bir **GUID** gereklidir. Bu, belgenizin türü (128 bit) için benzersiz bir tanımlayıcıdır. AppWizard sizin için bir tane oluşturur. bu nedenle, yeni kodu yeni bir AppWizard tarafından oluşturulan sunucu uygulamasından kopyalamak için burada açıklanan tekniği kullanırsanız, GUID 'yi yalnızca bu uygulamadan "çalmaya" ekleyebilirsiniz. Aksi takdirde, BIN dizinindeki GUIDGEN.EXE yardımcı programını kullanabilirsiniz.

' İ `COleTemplateServer` çağırarak nesnenizin belge şablonuna "bağlanması" gerekir `COleTemplateServer::ConnectTemplate` .

Uygulamanız tek başına çalıştırıldığında sistem kayıt defterini güncelleştirin. Bu şekilde, Kullanıcı öğesini taşıdıysanız. Uygulamanızı yeni konumundan çalıştırmak, uygulamanız için EXE Windows sistem kayıt veritabanını yeni konuma işaret edecek şekilde güncelleştirecek.

Tüm bu değişiklikler için AppWizard 'ın ne oluşturduğuna göre uygulandıktan sonra `InitInstance` , `InitInstance` HIERSVR için (ve ilgili GUID) aşağıdaki gibi okumalı:

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

Yukarıdaki kodun yeni bir kaynak KIMLIĞINE IDR_HIERSVRTYPE_SRVR_EMB olduğunu fark edeceksiniz. Bu, başka bir kapsayıcıya eklenmiş bir belge düzenlendiğinde kullanılacak olan menü kaynağıdır. MFC/OLE1 içinde katıştırılmış bir öğeyi düzenlemeyle ilgili menü öğeleri anında değiştirilmiştir. Dosya tabanlı bir belgeyi düzenlemeniz yerine gömülü bir öğe düzenlenirken tamamen farklı bir menü yapısını kullanmak, bu iki ayrı mod için farklı kullanıcı arabirimleri sağlamayı çok daha kolay hale getirir. Daha sonra göreceğiniz gibi, yerleşik bir nesne yerinde düzenlenirken tamamen ayrı bir menü kaynağı kullanılır.

Bu kaynağı oluşturmak için, kaynak betiğini Visual C++ yükleyin ve var olan IDR_HIERSVRTYPE Menu kaynağını kopyalayın. Yeni kaynağı IDR_HIERSVRTYPE_SRVR_EMB olarak yeniden adlandırın (Bu, AppWizard 'ın kullandığı adlandırma kuralıdır). Sonraki "Dosya Kaydet" i "dosya güncelleştirmesi" olarak değiştir; BT komut KIMLIĞI ID_FILE_UPDATE verin. Ayrıca "dosya farklı kaydet" i "dosya kopyasını farklı kaydet" olarak değiştirin; BT komut KIMLIĞI ID_FILE_SAVE_COPY_AS verin. Framework, bu komutların her ikisinin de uygulanmasını sağlar.

```Output
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers
```

`OnSetData` **OleStatus** türüne başvurduğundan, geçersiz kılmasından kaynaklanan birçok hata vardır. **OleStatus** , OLE1 'nin hata döndürdüğü yoldur. Bu, OLE 2 ' de **HRESULT** olarak değiştirilmiştir, ancak MFC genellikle bir **HRESULT** 'yi hata içeren bir öğesine dönüştürür `COleException` . Bu durumda, geçersiz kılma `OnSetData` artık gerekli değildir, bu nedenle en kolay şey bunu kaldırmalıdır.

```Output
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters
```

`COleServerItem`Oluşturucu fazladan bir ' bool ' parametresi alır. Bu bayrak, nesnelerde bellek yönetiminin nasıl yapıldığını belirler `COleServerItem` . Bunu TRUE olarak ayarlayarak, çerçeve bu nesnelerin bellek yönetimini işler; artık gerekli olmadığında bunları silin. HIERSVR `CServerItem` `COleServerItem` kendi yerel verilerinin bir parçası olarak nesneleri kullanır, bu nedenle bu bayrağı false olarak ayarlayacaksınız. Bu, her bir sunucu öğesinin silinme sırasında HIERSVR 'nin belirlenmesini sağlar.

```Output
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class
```

Bu hatalar söz konusu olduğunda, Cserveröğesinde geçersiz kılınamayan bazı ' saf-sanal ' işlevler vardır. Büyük olasılıkla bunun nedeni, OnDraw 'in parametre listesinin değiştiği gerçedir. Bu hatayı onarmak için `CServerItem::OnDraw` aşağıdaki gibi değiştirin (Ayrıca svridıtem. h içindeki bildirim):

```cpp
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)
{
    // request from OLE to draw node
    pDC->SetMapMode(MM_TEXT); // always in pixels
    return DoDraw(pDC, CPoint(0, 0), FALSE);
}
```

Yeni parametre ' rSize '. Bu, uygun durumlarda çizimin boyutunu doldurmanıza olanak sağlar. Bu boyut, **Himetrik**içinde olmalıdır. Bu durumda, bu değerin ' de doldurulması uygun değildir, bu nedenle Framework `OnGetExtent` kapsamı almak için çağırır. Bunun çalışması için şunları uygulamanız gerekir `OnGetExtent` :

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

CServerItem:: CalcNodeSize işlevinde, öğe boyutu **Himetrik** 'e dönüştürülüp *m_rectBounds*depolanır. Belgelenmemiş '*m_rectBounds*' üyesi `COleServerItem` yok ( *m_sizeExtent*kısmen değiştirilmiştir, ancak OLE 2 ' de bu üyenin OLE1 içinde *m_rectBounds* çok farklı bir kullanımı vardır). **Himetrik** boyutunu bu üye değişkenine ayarlamak yerine, geri döneceksiniz. Bu dönüş değeri `OnGetExtent` , daha önce uygulanan ' de kullanılır.

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

CServerItem ayrıca geçersiz kılar `COleServerItem::OnGetTextData` . Bu işlev MFC/OLE 'de kullanımdan kalkmıştır ve farklı bir mekanizmaya göre değiştirilmiştir. MFC OLE örnek [Hiersvr](../overview/visual-cpp-samples.md) 'ın MFC 3,0 sürümü bu işlevselliği geçersiz kılarak uygular `COleServerItem::OnRenderFileData` . Bu temel bağlantı noktası için bu işlevsellik önemli değildir, bu nedenle OnGetTextData geçersiz kılmayı kaldırabilirsiniz.

Svridıtem. cpp içinde açıklanmayan birçok hata daha vardır. Bunlar "gerçek" hatalar değildir; yalnızca önceki hatalardan kaynaklanan hatalar oluşur.

```Output
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters
```

`COleServerItem::CopyToClipboard` Artık `bIncludeNative` bayrağı desteklememektedir. Yerel veriler (sunucu öğesinin serileştirme işlevi tarafından yazılan veriler) her zaman kopyalanır, bu nedenle ilk parametreyi kaldırırsınız. Ayrıca, `CopyToClipboard` false döndürmek yerine bir hata oluştuğunda bir özel durum oluşturur. CServerView:: OnEditCopy kodunu aşağıdaki gibi değiştirin:

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

HIERSVR 'ın aynı OCLIENT sürümüne ait olan MFC 2,0 sürümünün derlenmesi sonucu daha fazla hata olsa da, aslında daha az değişiklik yapılmıştır.

Bu noktada, HIERSVR bir OLE sunucusu olarak derleyip, sonra da uygulanacak yerinde Düzenle özelliği olmadan bir OLE sunucusu olarak işlev görür.

### <a name="adding-visual-editing"></a>"Görsel düzenlemesi" ekleniyor

Bu sunucu uygulamasına "görsel düzen" (veya yerinde etkinleştirme) eklemek için, şunları yapmanız gereken birkaç nokta vardır:

- Öğe yerinde etkin olduğunda kullanılacak özel bir menü kaynağına ihtiyacınız vardır.

- Bu uygulamada bir araç çubuğu bulunur, bu nedenle sunucudan kullanılabilen menü komutlarıyla eşleştirmek için normal araç çubuğunun yalnızca bir alt kümesine sahip bir araç çubuğu gerekir (yukarıda belirtilen menü kaynağıyla eşleşir).

- Noktadan türetilmiş yeni bir sınıfa ihtiyacınız vardır `COleIPFrameWnd` (diğer bir deyişle, ' den türetilen cana bilgisayar, `CMDIFrameWnd` MDI Kullanıcı arabirimini sağlar).

- Çerçeveye bu özel kaynaklar ve sınıflar hakkında söylemeniz gerekir.

Menü kaynağı kolayca oluşturulur. Visual C++ çalıştırın, menü kaynak IDR_HIERSVRTYPE IDR_HIERSVRTYPE_SRVR_IP adlı bir menü kaynağına kopyalayın. Menüyü yalnızca Düzenle ve yardım menüsü açılan pencereleri sol olacak şekilde değiştirin. Düzenleme ve yardım menüleri arasındaki menüye iki ayırıcı ekleyin (şöyle görünmelidir: Düzenle &#124;&#124; yardım). Bu ayırıcıların anlamı ve sunucu ve kapsayıcı menülerinin nasıl birleştirileceği hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: menü birleştirme](../mfc/menus-and-resources-menu-merging.md).

Alt küme araç çubuğunun bit eşlemi, bir "sunucu" seçeneği işaretli olan yeni bir AppWizard tarafından oluşturulan uygulamadan kopyalayarak kolayca oluşturulabilir. Bu bit eşlem daha sonra Visual C++ içine aktarılabilir. Bit eşlemde IDR_HIERSVRTYPE_SRVR_IP bir KIMLIK vermediğinizden emin olun.

Öğesinden türetilen sınıf, `COleIPFrameWnd` sunucu desteğiyle birlikte bir AppWizard tarafından oluşturulan uygulamadan kopyalanabilir. Her iki dosyayı da Kopyala, IPFRAME. CPP ve IPFRAME. Ve bunları projeye ekleyin. `LoadBitmap`Çağrının, önceki adımda oluşturulan bit eşlem IDR_HIERSVRTYPE_SRVR_IP başvurduğundan emin olun.

Tüm yeni kaynaklar ve sınıflar oluşturuldığına göre, Framework 'ün bu bilgileri bilmesi için gerekli kodu ekleyin (ve bu uygulamanın artık yerinde düzenlemeleri desteklediğini bilir). Bu, işlevdeki çağrıya daha fazla parametre eklenerek yapılır `SetServerInfo` `InitInstance` :

```cpp
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```

Artık yerinde etkinleştirmeyi destekleyen hiçbir kapsayıcıda yerinde çalışmaya hazırdır. Ancak, kodda hala küçük bir hata var. HIERSVR, Kullanıcı farenin sağ düğmesine bastığında görünen bir bağlam menüsünü destekler. Bu menü, HIERSVR tamamen açık olduğunda çalışır, ancak bir ekleme yerinde düzenlenirken çalışmaz. Nedeni, CServerView:: Onrbuttonazaltma içindeki bu tek kod satırına sabitlenebilir:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```

Başvuruya dikkat edin `AfxGetApp()->m_pMainWnd` . Sunucu yerinde etkinleştirildiğinde, bir ana pencere olur ve m_pMainWnd ayarlanır, ancak genellikle görünmez. Ayrıca, bu pencere uygulamanın *ana* penceresine, sunucu tamamen açık olduğunda veya tek başına ÇALıŞTıRıLDıĞıNDA görünen MDI çerçevesi penceresi anlamına gelir. Yerinde etkinleştirilen bir çerçeve penceresi olduğunda, etkin çerçeve penceresine başvurmaz `COleIPFrameWnd` . Yerinde düzenlemede bile doğru etkin pencereyi almak için, MFC 'nin bu sürümü yeni bir işlev ekler `AfxGetMainWnd` . Genellikle, yerine bu işlevi kullanmanız gerekir `AfxGetApp()->m_pMainWnd` . Bu kodun aşağıdaki gibi değişmesi gerekir:

```cpp
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,
    point.x,
    point.y,
    AfxGetMainWnd());
```

Artık işlevsel bir yerinde etkinleştirme için en düşük düzeyde etkin bir OLE sunucunuz var. Ancak MFC/OLE1 'de kullanılamayan MFC/OLE 2 ' de kullanılabilen çok sayıda özellik vardır. Uygulamak isteyebileceğiniz özelliklerle ilgili daha fazla fikir için HIERSVR örneğine bakın. HIERSVR 'nin uyguladığı özelliklerden bazıları aşağıda listelenmiştir:

- Yakınlaştırma, kapsayıcıya göre gerçek WYSıWYG davranışı için.

- Sürükle/bırak ve özel bir Pano biçimi.

- Seçim değiştiği için kapsayıcı penceresini kaydırma.

MFC 3,0 ' de HIERSVR örneği, sunucu öğeleri için biraz farklı bir tasarım kullanır. Bu, belleğin korunmasına yardımcı olur ve bağlantılarınızın daha esnek olmasını sağlar. 2,0 sürümü ile birlikte, ağaçtaki her düğüm *-a olur* `COleServerItem` . `COleServerItem` Bu düğümlerin her biri için kesinlikle gerekli olandan biraz daha fazla yük taşır, ancak `COleServerItem` her etkin bağlantı için bir gereklidir. Ancak çoğu zaman, belirli bir zamanda çok az sayıda etkin bağlantı vardır. Bunu daha verimli hale getirmek için, MFC 'nin bu sürümündeki HIERSVR düğümü öğesinden ayırır `COleServerItem` . Hem CServerNode hem de `CServerItem` sınıfına sahiptir. `CServerItem`(Türetilen `COleServerItem` ) yalnızca gerekli olarak oluşturulur. Kapsayıcı (veya kapsayıcılar) bu belirli bir düğüme yönelik bu bağlantıyı kullanmayı durdurduktan sonra, CServerNode ile ilişkili CServerItem nesnesi silinir. Bu tasarım daha verimli ve daha esnektir. Esnekliği, birden çok seçim bağlantısı ile ilgilenirken ' de gelir. Bu iki iki sürümü de birden çok seçimi desteklemez, ancak yerel verilerden ayrıldığından, HIERSVR 'nin MFC 3,0 sürümü ile birlikte eklemek (ve bu seçimlere yönelik bağlantıları desteklemek) çok daha kolay olacaktır `COleServerItem` .

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
