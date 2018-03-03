---
title: "TN041: MFC OLE1 geçişi MFC OLE 2 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 894c171c025ef125495faad21dba2a98c08e8b88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041: MFC/OLE 2'ye MFC/OLE1 Geçişi
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
## <a name="general-issues-relating-to-migration"></a>Genel geçiş ile ilgili sorunlar  
 MFC 2.5 (ve daha yüksek) OLE 2 sınıfları için tasarım hedefleri MFC 2.0 OLE 1.0 desteği yararlanılmasını aynı mimarisi çoğunu korumak için oluştu. Sonuç olarak, MFC 2.0 aynı OLE sınıfların çoğu MFC bu sürümde mevcut (`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`). Ayrıca, bu sınıfları API'lerinde çoğunu tam olarak aynı değildir. Ancak, bazı ayrıntılar değişmiş beklediğiniz şekilde OLE 2 OLE 1.0 büyük ölçüde farklılık gösterir. MFC 2.0'ın OLE1 desteğiyle bilginiz varsa, evde MFC'nin 2.0 desteği ile eşitleyerek.  
  
 Varolan bir MFC/OLE1 uygulamayı almak ve OLE 2 işlevselliği ekleme, bu not önce okumanız gerekir. Bu notu, OLE1 işlevselliği MFC/OLE 2'ye taşıma sırasında karşılaşabileceğiniz ve MFC 2. 0'dahil iki uygulama taşıma sırasında sınamayla sorunlar ele alınmaktadır bazı genel sorunları ele alır: MFC OLE örnekleri [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md).  
  
## <a name="mfc-documentview-architecture-is-important"></a>MFC belge/görünüm mimarisinin önemlidir  
 Uygulamanızı MFC'nin belge/görünüm mimarisinin kullanmaz ve uygulamanıza OLE 2 desteği eklemek istediğiniz, belge/görünüm taşımak için zaman sunulmuştur. Uygulamanızı MFC bileşenlerini ve yerleşik mimarisini kullanarak sonra birçok avantajı MFC'nin OLE 2 sınıfların yalnızca alırlar.  
  
 MFC mimarisi kullanmadan bir sunucu veya kapsayıcı uygulama olası, ancak önerilmez.  
  
## <a name="use-mfc-implementation-instead-of-your-own"></a>MFC uygulaması kendi yerine kullanın  
 MFC canned"uygulama" sınıflar gibi `CToolBar`, `CStatusBar`, ve `CScrollView` OLE 2 desteği için yerleşik özel örnek koduna sahip. Bu nedenle, bu sınıfları, uygulamanızda kullanıyorsanız, bunları OLE uyumlu hale getirmek için bunlara put çaba yararlı. Yeniden, bu amaçlar için "TOP kendi" sınıflarına burada mümkündür, ancak değil önerilir. Benzer işlevsellik uygulamanız gerekiyorsa, MFC kaynak kodu (özellikle, yerinde etkinleştirme gelince) OLE yüksekse noktalarının bazıları ilgilenmek için mükemmel bir başvuru bulunur.  
  
## <a name="examine-the-mfc-sample-code"></a>MFC örnek kodunu İnceleme  
 OLE işlevselliği MFC örnekleri mevcuttur. Bu uygulamaların her biri farklı açıdan OLE uygular:  
  
- [HIERSVR](../visual-cpp-samples.md) bir sunucu uygulaması olarak kullanmak için çoğunlukla anlamına gelir. Bu, MFC 2.0 MFC/OLE1 uygulama olarak eklenmiştir ve olduğundan MFC/OLE 2'ye bağlantı noktası kurulmuş ve OLE 2'de kullanılabilen birçok OLE özellikleri uygulayan, ardından genişletilmiş.  
  
- [OCLIENT](../visual-cpp-samples.md) OLE özelliklerinin çoğunu bir kapsayıcı açısından göstermek için amacı bir tek başına kapsayıcısı uygulamasına budur. MFC 2.0 ' çok alındığını ve birçok özel Pano biçimleri ve katıştırılmış öğelerine bağlantılar gibi daha gelişmiş OLE özelliği desteklemek için genişletilmiş.  
  
- [DRAWCLI](../visual-cpp-samples.md) OCLIENT yaptığı gibi bunu var olan bir nesne yönelimli çizim programı Framework'te yapar dışında bu uygulama OLE kapsayıcı desteği çok uygular. Size nasıl OLE kapsayıcı desteği uygulamak ve varolan uygulamanıza tümleştirmek gösterir.  
  
- [SUPERPAD](../visual-cpp-samples.md) bu uygulamanın yanı sıra ince bağımsız bir uygulama olan olduğunu da OLE sunucusu. Bunu uygulayan sunucu sessiz minimal bir kullanım sağlar desteğidir. İlginizi çeken nasıl verileri panoya kopyalamak için OLE Pano hizmetleri kullanan olsa da Pano Yapıştır işlevselliğini uygulamak için Windows "Düzenle" denetime yerleşik işlevi kullanır. Bu, geleneksel Windows API kullanımı ve bunun yanı sıra yeni OLE API'leri ile tümleştirme ilginç bir karışımını gösterir.  
  
 Örnek uygulamalar hakkında daha fazla bilgi için "MFC örnek Yardım" konusuna bakın.  
  
## <a name="case-study-oclient-from-mfc-20"></a>Örnek olay incelemesi: MFC 2.0 gelen OCLIENT  
 Yukarıda açıklandığı gibi [OCLIENT](../visual-cpp-samples.md) MFC 2. 0'e eklenmiştir ve OLE MFC/OLE1 ile uygulanmadı. Aşağıda, bu uygulama başlangıçta MFC/OLE 2 sınıflarını kullanmak için dönüştürüldü adımları açıklanmaktadır. MFC/OLE sınıfları daha iyi anlamak için başlangıç bağlantı noktası tamamlandıktan sonra birçok özellik eklenmedi. Bu özellikler aşağıda ele alınacak değil; Bu gelişmiş özellikler hakkında daha fazla bilgi için örnek kendisini bakın.  
  
> [!NOTE]
>  Derleyici hataları ve adım adım işlemi Visual C++ 2.0 ile oluşturuldu. Özel hata iletileri ve konumları ile Visual C++ 4.0 değişmiş olabilir, ancak kavramsal bilgiler geçerli kalır.  
  
## <a name="getting-it-up-and-running"></a>Alma ve çalıştırma  
 MFC/OLE OCLIENT örnek bağlantı noktası için uygulanan yaklaşıma onu oluşturmak ve sonuçlanır belirgin derleyici hataları düzelttikten başlatmaktır. MFC 2. 0 OCLIENT örnek alın ve MFC bu sürümü altında derleme varsa, gidermek için birçok hata olmadığını bulabilirsiniz. Sırada gerçekleşen hataları aşağıda açıklanmıştır.  
  
## <a name="compile-and-fix-errors"></a>Derleme ve düzeltme hataları  
  
```  
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters  
```  
  
 İlk hata endişelere `COleClientItem::Draw`. MFC/OLE1 MFC/OLE sürüm alır olandan daha fazla parametre sürdü. Ek parametreler genelde gerekli ve (Bu örnekte) olduğu gibi genellikle NULL. İçin çizilmiş CDC meta dosyası DC olduğunda bu sürümü MFC lpWBounds için değerleri otomatik olarak belirleyebilirsiniz. Framework 'yı "özniteliği DC" geçirilen PDC birinden oluşturacaksınız beri ek olarak, pFormatDC parametresi artık gerekli değildir. Bu sorunu gidermek için yalnızca iki kaldırmak için fazladan, çizim arama parametreleri NULL.  
  
```  
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier  
\oclient\mainview.cpp(273) : error C2057: expected constant expression  
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
```  
  
 Yukarıdaki olgusu sonucundan hataları, tüm **COleClientItem::CreateXXXX** MFC/OLE1 işlevlerde gerekli benzersiz bir ad öğeyi temsil geçirilmesi. Bu gereksinimi temel OLE API oluştu. OLE 2 (DDE görüşmeleri adı kullanılır) temel alınan iletişim mekanizması olarak DDE kullanmaması nedeniyle bu MFC/OLE 2'de gerekli değildir. Bu sorunu gidermek için kaldırabilirsiniz **CreateNewName** işlev tüm başvuruları yanı sıra. Ne her MFC/OLE işlevi bu sürümde yalnızca imlecinizi aramayı ve F1 tuşuna basarak beklediği bulmak kolaydır.  
  
 Önemli ölçüde farklı olduğu başka bir OLE 2 Pano işleme alanıdır. OLE1'ile API'leri etkileşim Windows panosuna Pano ile kullanılır. OLE 2 ile bu farklı bir mekanizma ile gerçekleştirilir. MFC/OLE1 API'leri kopyalamadan önce Pano açık olduğunu kabul bir `COleClientItem` panoya nesne. Bu, artık gerekli değildir ve tüm MFC/OLE Pano işlemleri başarısız olmasına neden olur. Bağımlılıkları kaldırmak için kodu düzenleme yaparken **CreateNewName**, açar ve Windows panosuna kapatır kodu kaldırmanız gerekir.  
  
```  
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier  
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function  
\oclient\mainview.cpp(344) : error C2057: expected constant expression  
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'  
```  
  
 Bu hatalardan kaynaklanan **CMainView::OnInsertObject** işleyicisi. "Yeni Nesne Ekle" komutunu işleme burada şeyler oldukça biraz değiştirilmiş başka bir alandır. Bu durumda, yalnızca özgün uygulaması için yeni bir OLE kapsayıcı uygulama AppWizard tarafından sağlanan Birleştir en kolayıdır. Aslında, bu diğer uygulamaların taşıma için uygulayabileceğiniz bir tekniktir. MFC/OLE1 ', "Nesne Ekle" iletişim çağrılarak görüntülenen **AfxOleInsertDialog** işlevi. Bu sürümde oluşturmak bir **COleInsertObject** iletişim nesnesi ve çağrı `DoModal`. Ayrıca, yeni OLE öğeleri ile oluşturulan bir **CLSID** classname dize yerine. Sonuç aşağıdakine benzer görünmelidir  
  
```  
COleInsertDialog dlg;  
if (dlg.DoModal() != IDOK)  
    return; 
 
BeginWaitCursor();

 
CRectItem* pItem = NULL;  
TRY  
{ *// First create the C++ object  
    pItem = GetDocument()->CreateItem();
ASSERT_VALID(pItem);

 *// Initialize the item from the dialog data.  
    if (!dlg.CreateItem(pItem))  
    AfxThrowMemoryException();
*// any exception will do  
    ASSERT_VALID(pItem);

 *// run the object if appropriate  
    if (dlg.GetSelectionType() == 
    COleInsertDialog::createNewItem) 
    pItem->DoVerb(OLEIVERB_SHOW,
    this);

 *// update right away  
    pItem->UpdateLink();
pItem->UpdateItemRectFromServer();

 *// set selection to newly inserted item  
    SetSelection(pItem);

 pItem->Invalidate();

}  
CATCH (CException,
    e)  
{ *// clean up item  
    if (pItem != NULL)  
    GetDocument()->DeleteItem(pItem);

 
    AfxMessageBox(IDP_FAILED_TO_CREATE);

} 
END_CATCH  
 
EndWaitCursor();
```  
  
> [!NOTE]
>  Yeni nesne eklemeyi, uygulamanız için farklı olabilir):  
  
 Eklenecek gereklidir \<afxodlgs.h >, bildirimi içeren **COleInsertObject** MFC tarafından sağlanan diğer standart iletişim kutuları yanı sıra iletişim kutusu sınıfı.  
  
```  
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier  
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters  
```  
  
 Kavram olarak bunlar aynı olsa da bu hataları olarak bazı OLE1 sabitleri OLE 2'de, değişen hatalardır. Bu durumda **OLEVERB_PRIMARY** değiştirildi `OLEIVERB_PRIMARY`. Kullanıcı bir öğeyi tıklattığında OLE1 ve OLE 2'de birincil fiil genellikle bir kapsayıcı tarafından yürütülür.  
  
 Ayrıca, `DoVerb` artık ek bir parametre alan — bir görünüm için bir işaretçi (`CView`*). Bu parametre yalnızca "Görsel düzenleme" (veya yerinde etkinleştirme) uygulamak için kullanılır. Bu özellik şu anda uygulanmadığı için şu an için bu parametre NULL olarak ayarlayın.  
  
 Framework hiçbir zaman yerinde girişimleri etkinleştirmenizi emin olmak için geçersiz kılmalıdır `COleClientItem::CanActivate` gibi:  
  
```  
BOOL CRectItem::CanActivate()  
{  
    return FALSE;  
}  
 
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier  
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function  
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier  
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function  
```  
  
 MFC/OLE1 içinde **COleClientItem::GetBounds** ve **SetBounds** sorgulamak ve öğeyi kapsamını işlemek için kullanılan ( **sol** ve **üst**üyeleri olan her zaman sıfır). MFC/OLE 2'de bu daha doğrudan tarafından desteklenen `COleClientItem::GetExtent` ve `SetExtent`, ile ilgili bir **BOYUTU** veya `CSize` yerine.  
  
 Yeni, SetItemRectToServer kodunu ve UpdateItemRectFromServer çağrı şuna benzeyebilir:  
  
```  
BOOL CRectItem::UpdateItemRectFromServer()  
{  
    ASSERT(m_bTrackServerSize);

 CSize size;  
    if (!GetExtent(&size))  
    return FALSE;    // blank  
 *// map from HIMETRIC to screen coordinates  
 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.LPtoDP(&size);

 } *// just set the item size  
    if (m_rect.Size() != size)  
 { *// invalidate the old size/position  
    Invalidate();
m_rect.right = m_rect.left + size.cx;  
    m_rect.bottom = m_rect.top + size.cy; *// as well as the new size/position  
    Invalidate();

 }  
    return TRUE;  
}  
 
BOOL CRectItem::SetItemRectToServer()  
{ *// set the official bounds for the embedded item  
    CSize size = m_rect.Size();

 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.DPtoLP(&size);

 }  
    TRY 
 {  
    SetExtent(size);
*// may do a wait  
 }  
    CATCH(CException, e)  
 {  
    return FALSE;  // links will not allow SetBounds  
 }  
    END_CATCH 
    return TRUE;  
}  
 
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'  
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier  
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function  
```  
  
 Bir sunucu için bir kapsayıcı gelen çağrıları MFC/OLE1 zaman uyumlu API'si olan *benzetimli*, OLE1 birçok durumda kendiliğinden zaman uyumsuz. Kullanıcıdan komutları işlemeden önce devam eden bir bekleyen zaman uyumsuz çağrı denetlemek gerekli. MFC/OLE1 sağlanan **COleClientItem::InWaitForRelease** bunu işlevi. Hepsini bir araya CMainFrame içinde OnCommand geçersiz kılma kaldırılacak şekilde MFC/OLE 2'de bu gerekli değildir.  
  
 Bu noktada OCLIENT derleme ve bağlama.  
  
## <a name="other-necessary-changes"></a>Diğer gerekli değişiklikleri  
 OCLIENT çalışmasını, ancak tutar değil yapılan birkaç nokta vardır. Şimdi yerine daha sonra bu sorunları düzeltmek iyidir.  
  
 İlk olarak, OLE kitaplıklarının başlatmak gereklidir. Bu çağırarak yapılır **Afxoleınit** gelen `InitInstance`:  
  
```  
if (!AfxOleInit())  
{  
    AfxMessageBox("Failed to initialize OLE libraries");

    return FALSE;  
}  
```  
  
 Sanal işlevler parametre listesi değişiklikleri denetlemek için de iyi bir fikirdir. Bu tür bir işlevdir `COleClientItem::OnChange`, her MFC/OLE kapsayıcı uygulamada geçersiz kılınan. Çevrimiçi Yardım'a bakarak bir ek 'DWORD dwParam' eklendiğini görürsünüz. Yeni CRectItem::OnChange şu şekilde görünür:  
  
```  
void   
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)  
{  
    if (m_bTrackServerSize&& 
 !UpdateItemRectFromServer())  
 { *// Blank object  
    if (wNotification == OLE_CLOSED)  
 { *// no data received for the object - destroy it  
    ASSERT(!IsVisible());

 GetDocument()->DeleteItem(this);

    return; // no update (item is gone now)  
 }  
 }  
    if (wNotification != OLE_CLOSED)  
    Dirty();
Invalidate();
*// any change will cause a redraw  
}  
```  
  
 MFC/OLE1, kapsayıcı uygulamaları belge sınıfından türetilen **COleClientDoc**. MFC/OLE 2'de bu sınıf olduğundan kaldırıldı ve yerini `COleDocument` (Bu yeni bir kuruluş, kapsayıcı/sunucu uygulamaları oluşturma kolaylaştırır). Var olan bir `#define` eşleyen **COleClientDoc** için `COleDocument` MFC/OLE1 uygulamaların OCLIENT gibi MFC/OLE 2'ye taşıma basitleştirmek için. Tarafından sağlanmayan özelliklerden birini `COleDocument` tarafından sağlanmadığından **COleClientDoc** eşleme girdilerini standart komut iletisidir. Bu nedenle yapılır de, sunucu uygulamaları `COleDocument` bir kapsayıcı/sunucu uygulaması olmadığı sürece (dolaylı olarak), bunları bu komut işleyicileri yükü taşımaz. Aşağıdaki girişleri için CMainDoc ileti eşlemesi eklemeniz gerekir:  
  
```  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE,
    OnUpdatePasteMenu)  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK,
    OnUpdatePasteLinkMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS,
    OnUpdateEditLinksMenu)  
ON_COMMAND(ID_OLE_EDIT_LINKS,
    COleDocument::OnEditLinks)  
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST,
    OnUpdateObjectVerbMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT,
    OnUpdateObjectVerbMenu)  
ON_COMMAND(ID_OLE_EDIT_CONVERT,
    OnEditConvert)  
```  
  
 Bu komutların tümünü içinde uygulamasıdır `COleDocument`, belgeniz için temel sınıfı olan.  
  
 Bu noktada, OCLIENT bir işlev OLE kapsayıcı uygulamasıdır. Herhangi bir türde (OLE1 veya OLE 2) öğeleri eklemek mümkündür. Yerinde etkinleştirme olanak sağlamak için gerekli kod uygulanmadı olduğundan, öğeleri ile OLE1 çok gibi ayrı bir pencerede düzenlenmiştir. Sonraki bölümde (bazen "Görsel düzenleme" olarak adlandırılır) yerinde düzenlemeyi etkinleştirmek için gerekli değişiklikleri açıklar.  
  
## <a name="adding-visual-editing"></a>"Görsel düzenleme" ekleme  
 OLE en ilginç özelliklerini yerinde etkinleştirme (veya "Görsel düzenleme") biridir. Bu özellik, sağlanan kullanıcıya daha sorunsuz bir düzenleme arabirimi için kapsayıcının kullanıcı arabirimi bölümlerini almak sunucu uygulaması sağlar. Yerinde etkinleştirme OCLIENT uygulamak için bazı özel kaynaklar, bazı ek kod yanı sıra eklenmesi gerekir. Bu kaynaklar ve kod normalde AppWizard tarafından sağlanan — aslında, kodu buraya çoğunu doğrudan bir uygulamadan yeni AppWizard "Kapsayıcı" desteğiyle ödünç.  
  
 Öncelikle, yerinde etkin olan bir öğe olduğunda kullanılacak bir menü kaynak eklemek gereklidir. IDR_OCLITYPE kaynak kopyalama ve tüm dosya ve penceresi açılır pencereleri kaldırarak Visual C++'da bu fazladan menü kaynağı oluşturun. İki ayırıcı çubukları grupları ayrılması belirtmek için dosya ve penceresi açılır pencereleri arasında eklenir (gibi görünmelidir: Dosya &#124; &#124; Pencere). Bu ayırıcılar ne anlama geldiğini ve sunucu ve kapsayıcı menüleri nasıl birleştirilir hakkında daha fazla bilgi için "Menüler ve kaynaklar: menü birleştirme" konusuna bakın *OLE 2 sınıfları*.  
  
 Oluşturulan bu menüler olduktan sonra bunları hakkında bilmeniz framework izin gerekir. Bu çağırarak yapılır `CDocTemplate::SetContainerInfo` belge şablonu, InitInstance belge şablonu listesine ekleyebilmeniz için. Belge şablonu kaydetmek için yeni kod şöyle görünür:  
  
```  
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE, 
    RUNTIME_CLASS(CMainDoc), 
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame  
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```   
  
 Visual C++ içinde oluşturulan özel yerinde kaynak IDR_OLECLITYPE_INPLACE kaynaktır.  
  
 Yerinde etkinleştirme etkinleştirmek için ikisi de değiştirmek için gereken bazı şeyler vardır `CView` (CMainView) türetilmiş sınıf yanı sıra `COleClientItem` türetilmiş sınıf (CRectItem). Bu geçersiz kılmaları tümünün AppWizard tarafından sağlanır ve uygulamalarının çoğu doğrudan bir varsayılan AppWizard uygulamasından gelecektir.  
  
 Bu bağlantı noktası ilk adımda tamamen geçersiz kılarak yerinde etkinleştirme devre dışı `COleClientItem::CanActivate`. Yerinde etkinleştirme izin vermek için bu geçersiz kılma kaldırılması gerekir. Ayrıca, tüm çağrıları NULL geçirilmedi `DoVerb` (var olan iki tanesi) görünüm sağlama yalnızca yerinde etkinleştirme için gerekli olduğundan. Yerinde etkinleştirme tam olarak uygulamak için onu doğru görünümünde geçirmek gerekli olan `DoVerb` çağırın. Bu çağrı, biri de **CMainView::OnInsertObject**:  
  
```  
pItem->DoVerb(OLEIVERB_SHOW, this);
```  
  
 Başka bir yer **CMainView::OnLButtonDblClk**:  
  
```  
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```  
  
 Geçersiz kılmak gerekli olan `COleClientItem::OnGetItemPosition`. Bu sunucunun öğesi yerinde etkin olduğunda kapsayıcının penceresi göre nereye onun penceresi bildirir. OCLIENT için uygulama kısmı oldukça kolaydır:  
  
```  
void CRectItem::OnGetItemPosition(CRect& rPosition)  
{  
    rPosition = m_rect;  
}  
```  
  
 "Yeniden boyutlandırma yerinde." olarak adlandırılan çoğu sunucuları da uygulama Bu sunucu penceresinde boyuta sahip ve kullanıcı öğesi düzenleme sırada taşınmasını sağlar. Taşıma veya pencere genellikle yeniden boyutlandırma konumu ve boyutu kapsayıcı belge içinde etkilediği için kapsayıcı bu eylemde alması gerekir. OCLIENT uygulamasını yeni konumu ve boyutu ile m_rect tarafından tutulan iç dikdörtgen eşitler.  
  
```  
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
  
 Bu noktada, etkinleştirilmiş yerinde ve etkin olduğunda öğeyi taşıma ve boyutlandırma ile mücadele etmek için bir öğe izin vermek için yeterli kod yoktur, ancak hiçbir kod düzenleme oturumu çıkmak kullanıcının izin verir. Bazı sunucular bu işlevselliği kendilerini kaçış anahtar işleyerek sağlar ancak kapsayıcıları öğeyi devre dışı bırakmak için iki yol sağlar önerilir: (1) tıklatarak öğenin dışında ve (2) KAÇIŞ tuşuna basarak.  
  
 KAÇIŞ anahtarı için bir komuta VK_ESCAPE tuşu eşleştiren Visual C++ ile Hızlandırıcı eklemek için ID_CANCEL_EDIT kaynaklara eklenir. Bu komutun işleyicisi aşağıdaki gibidir:  
  
```  
// The following command handler provides the standard  
// keyboard user interface to cancel an in-place  
// editing session.void CMainView::OnCancelEdit()  
{ *// Close any in-place active item on this view.  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->Close();
ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);

}  
```  
  
 Burada, kullanıcı, öğenin dışında durumu işlemek için aşağıdaki kodu başlangıcına ekleyin **CMainView::SetSelection**:  
  
```  
if (pNewSel != m_pSelection || pNewSel == NULL)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& pActiveItem != pNewSel)  
    pActiveItem->Close();

} 
 
```  
  
 Bir öğe yerinde etkin olduğunda, odağı olması gerekir. Bu durumda olduğundan emin olmak için görünümünüzü odağı aldığında odağı her zaman etkin öğesine aktarılan böylece OnSetFocus işler:  
  
```  
// Special handling of OnSetFocus and OnSize are required   
// when an object is being edited in-place.  
void CMainView::OnSetFocus(CWnd* pOldWnd)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& 
    pActiveItem->GetItemState() == COleClientItem::activeUIState)  
 { *// need to set focus to this item if it is same view  
    CWnd* pWnd = pActiveItem->GetInPlaceWindow();
if (pWnd != NULL)  
 {  
    pWnd->SetFocus();
*// don't call the base class  
    return; 
 }  
 }  
 
    CView::OnSetFocus(pOldWnd);

} 
```  
  
 Görünümü yeniden boyutlandırıldığında dikdörtgen kırpma değişti etkin öğeyi bildirmek gerekir. Bunun için bir işleyici sağlar yapmak için `OnSize`:  
  
```  
void CMainView::OnSize(UINT nType,
    int cx,
    int cy)  
{  
    CView::OnSize(nType,
    cx,
    cy);

    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->SetItemRects();

} 
```  
  
## <a name="case-study-hiersvr-from-mfc-20"></a>Örnek olay incelemesi: MFC 2.0 gelen HIERSVR  
 [HIERSVR](../visual-cpp-samples.md) MFC 2. 0'da eklenmiştir ve OLE MFC/OLE1 ile uygulanmadı. Bu Not kısaca tarafından bu uygulamanın başlangıçta MFC/OLE 2 sınıflarını kullanmak için dönüştürüldü adımları açıklanmaktadır. MFC/OLE 2 sınıfları daha iyi anlamak için başlangıç bağlantı noktası tamamlandıktan sonra birçok özellik eklenmedi. Bu özellikler aşağıda ele alınacak değil; Bu gelişmiş özellikler hakkında daha fazla bilgi için örnek kendisini bakın.  
  
> [!NOTE]
>  Derleyici hataları ve adım adım işlemi Visual C++ 2.0 ile oluşturuldu. Özel hata iletileri ve konumları ile Visual C++ 4.0 değişmiş olabilir, ancak kavramsal bilgiler geçerli kalır.  
  
## <a name="getting-it-up-and-running"></a>Alma ve çalıştırma  
 MFC/OLE HIERSVR örnek bağlantı noktası için uygulanan yaklaşıma onu oluşturmak ve sonuçlanır belirgin derleyici hataları düzelttikten başlatmaktır. MFC 2. 0 HIERSVR örnek alın ve MFC bu sürümü altında derleme (vardır, ancak birden fazla OCLIENT örnekle) gidermek için birçok hata olmadığını bulabilirsiniz. Hataları, genellikle oluşma sırasına aşağıda açıklanmıştır.  
  
## <a name="compile-and-fix-errors"></a>Derleme ve düzeltme hataları  
  
```  
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'  
```  
  
 Bu ilk hata kadar büyük sorun çıkışı işaret `InitInstance` işlevi sunucuları için. OLE sunucu için gereken başlatma çalışmasını almak için MFC/OLE1 uygulamanıza yapmanız gereken büyük değişikliklerden biri olabilir. Yapmak için en iyi ne AppWizard için bir OLE sunucusu oluşturur bakın ve uygun şekilde kodunuzu değiştirmek şeydir. Dikkate alınması gereken bazı noktalar şunlardır:  
  
 OLE kitaplıklarının çağırarak başlatmak gerekli olan **Afxoleınit**  
  
 Sunucu kaynak tanıtıcıları ve ile ayarlanamıyor çalışma zamanı sınıf bilgileri ayarlamak için belge şablonu nesnesi üzerinde SetServerInfo çağrısı `CDocTemplate` Oluşturucusu.  
  
 Komut satırında /Embedding varsa, uygulamanızın ana penceresi gösterme.  
  
 Bunun bir **GUID** belgeniz için. Bu, belgenizin türü (128 bit) için benzersiz bir tanımlayıcıdır. AppWizard sizin için bir oluşturur — bunu, burada açıklanan teknikleri kullanıyorsanız, yeni oluşturulan AppWizard sunucu uygulamasından yeni kod kopyalama, yalnızca "uygulaması GUID çalınacak". Aksi durumda, GUIDgen kullanabilirsiniz. BIN dizinindeki EXE yardımcı programı.  
  
 "Bağlanmak" gereklidir, `COleTemplateServer` çağırarak belge şablonu nesnesine `COleTemplateServer::ConnectTemplate`.  
  
 Uygulamanızı bağımsız olarak çalıştırıldığında sistem kayıt defteri güncelleştirilemiyor. Bu şekilde, kullanıcı taşırsa. EXE uygulamanız için yeni konumundan çalıştıran yeni konumunu gösterecek şekilde Windows Sistem kayıt veritabanını güncelleştirir.  
  
 Tüm ne AppWizard için oluşturur üzerinde göre bu değişiklikleri uyguladıktan sonra `InitInstance`, `InitInstance` (ve ilişkili GUID) HIERSVR gibi gözükmelidir için:  
  
```  
// this is the GUID for HIERSVR documents  
static const GUID BASED_CODE clsid = 
 { 0xA0A16360L,
    0xC19B,
    0x101A, { 0x8C,
    0xE5,
    0x00,
    0xDD,
    0x01,
    0x11,
    0x3F,
    0x12 } };  
 
/////////////////////////////////////////////////////////////////////////////  
// COLEServerApp initialization  
 
BOOL COLEServerApp::InitInstance()  
{ *// OLE 2 initialization  
    if (!AfxOleInit())  
 {  
    AfxMessageBox("Initialization of the OLE failed!");

    return FALSE;  
 }  
 *// Standard initialization  
    LoadStdProfileSettings();

// Load standard INI file options   
 *// Register document templates  
    CDocTemplate* pDocTemplate;  
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,  
    RUNTIME_CLASS(CServerDoc), 
    RUNTIME_CLASS(CMDIChildWnd), 
    RUNTIME_CLASS(CServerView));

 pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);

    AddDocTemplate(pDocTemplate);

 *// create main MDI Frame window  
    CMainFrame* pMainFrame = new CMainFrame;  
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))  
    return FALSE;  
    m_pMainWnd = pMainFrame;  
 
    SetDialogBkColor();
*// gray look  
 *// enable file manager drag/drop and DDE Execute open  
    m_pMainWnd->DragAcceptFiles();
EnableShellOpen();

 
    m_server.ConnectTemplate(clsid,
    pDocTemplate,
    FALSE);

    COleTemplateServer::RegisterAll();

 *// try to launch as an OLE server  
    if (RunEmbedded())  
 { *// "short-circuit" initialization -- run as server!  
    return TRUE;  
 }  
    m_server.UpdateRegistry();
RegisterShellFileTypes();

 *// not run as OLE server,
    so show the main window  
    if (m_lpCmdLine[0] == '\0')  
 { *// create a new (empty) document  
    OnFileNew();

 }  
    else 
 { *// open an existing document  
    OpenDocumentFile(m_lpCmdLine);

 }  
 
    pMainFrame->ShowWindow(m_nCmdShow);

 pMainFrame->UpdateWindow();

 
    return TRUE;  
}  
```  
  
 Yukarıdaki kod yeni bir kaynak kimliği için IDR_HIERSVRTYPE_SRVR_EMB başvuruyor fark edeceksiniz. Bu, başka bir kapsayıcıda katıştırılmış bir belge düzenlendiğinde kullanılacak menüsü kaynak değil. MFC/OLE1 katıştırılmış bir öğenin düzenlenebilmesi için belirli menü öğeleri anında değiştirildi. Dosya tabanlı belge düzenlemeyi yerine katıştırılmış bir öğe düzenlerken tamamen farklı menü yapısı kullanarak bu iki ayrı modları için farklı kullanıcı arabirimleri sağlamak üzere kolaylaşır. Daha sonra anlatıldığı gibi tamamen ayrı bir menü kaynak bir katıştırılmış nesne yerinde düzenlerken kullanılır.  
  
 Bu kaynağı oluşturmak için bir kaynak betik Visual C++ yükleme ve varolan IDR_HIERSVRTYPE menüsü kaynak kopyalayın. Yeni kaynak (AppWizard kullandığı aynı adlandırma kuralı budur) IDR_HIERSVRTYPE_SRVR_EMB yeniden adlandırın. "Dosya güncelleştirmesi için"; "Dosyasını kaydedin" Sonraki değişiklik Komut kimliği vermek **ıd_fıle_update**. Ayrıca "Dosyasını farklı kaydet" "Dosya kopyalama Kaydet için"; değiştirme Komut kimliği vermek **ıd_fıle_save_copy_as**. Bu komutların her ikisi de uygulanması çerçevesi sağlar.  
  
```  
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations  
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers  
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'  
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'  
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers  
```  
  
 Bir dizi geçersiz kılma kaynaklanan hataları vardır `OnSetData`, referans veriyor beri **OLESTATUS** türü. **OLESTATUS** OLE1 döndürülen hatalar yolu olmuştur. Bu değiştirildi `HRESULT` OLE 2'deki MFC genellikle dönüştürür rağmen bir `HRESULT` içine bir `COleException` hata içeren. Bu örnekte, geçersiz kılma `OnSetData` kaldırmak için kolay bir şey yapmak için olacak şekilde artık gerekli değildir.  
  
```  
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters  
```  
  
 `COleServerItem` Oluşturucusu fazladan bir 'BOOL' parametre alır. Bu bayrak bellek yönetimi üzerinde nasıl yapıldığını belirler `COleServerItem` nesneleri. TRUE olarak ayarlanmasını Framework'te bellek yönetimi bu nesnelerin işler — bunlar artık gerekli olduğunda bunları silme. HIERSVR kullanan **CServerItem** (türetilmiş `COleServerItem`) nesneleri bu bayrağı FALSE olarak ayarlarsınız şekilde kendi yerel veri parçası olarak. Bu, her bir sunucu öğe silindiğinde belirlemek HIERSVR olanak tanır.  
  
```  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
```  
  
 Bu hatalar kapsıyor gibi CServerItem içinde geçersiz kılmamış 'sanal saf' bazı işlevler vardır. Büyük olasılıkla bu OnDraw'ın parametre listesi değişti gerçeğiyle kaynaklanır. Bu hatayı düzeltmek için değiştirme **CServerItem::OnDraw** gibi (yanı sıra svritem.h bildiriminde):  
  
```  
BOOL CServerItem::OnDraw(CDC* pDC,
    CSize& rSize)  
{ *// request from OLE to draw node  
    pDC->SetMapMode(MM_TEXT);

// always in pixels  
    return DoDraw(pDC,
    CPoint(0,
    0),
    FALSE);

}  
```  
  
 Yeni bir parametre 'rSize' dir. Bu çizim boyutunda doldurmak uygun değilse sağlar. Bu boyutta olmalıdır **HIMETRIC**. Framework çağırması bu durumda, bu değeri, doldurmak uygun olmadığından `OnGetExtent` ölçüde alınamadı. Uygulamak, çalışmaya sahip olacaksınız `OnGetExtent`:  
  
```  
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect,
    CSize& rSize)  
{  
    if (dwDrawAspect != DVASPECT_CONTENT)  
    return COleServerItem::OnGetExtent(dwDrawAspect,
    rSize);

 
    rSize = CalcNodeSize();
return TRUE;  
}  
 
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier  
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type  
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'  
```  
  
 Öğe boyutunun dönüştürülür CServerItem::CalcNodeSize işlevinde **HIMETRIC** ve depolanan **m_rectBounds**. Belgelenmemiş '**m_rectBounds**' üyesi `COleServerItem` yok (tarafından kısmen değiştirilmiştir `m_sizeExtent`, ancak OLE 2'de bu daha çok biraz farklı kullanımı üyenin **m_rectBounds**OLE1 ' vermedi). Ayar yerine **HIMETRIC** boyutu bu üye değişkeni, onu döneceksiniz. Bu dönüş değeri kullanılır `OnGetExtent`, daha önce uygulanan.  
  
```  
CSize CServerItem::CalcNodeSize()  
{  
    CClientDC dcScreen(NULL);

 
    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,  
    m_strDescription.GetLength());

 m_sizeNode += CSize(CX_INSET* 2,
    CY_INSET* 2);

 *// set suggested HIMETRIC size  
    CSize size(m_sizeNode.cx,
    m_sizeNode.cy);

    dcScreen.SetMapMode(MM_HIMETRIC);

 dcScreen.DPtoLP(&size);

    return size;  
}  
```  
  
 CServerItem ayrıca geçersiz kılar **COleServerItem::OnGetTextData**. Bu işlev, MFC/OLE kullanımdan kalkmıştır ve farklı bir mekanizma değiştirilir. MFC OLE örnek MFC 3.0 sürümü [HIERSVR](../visual-cpp-samples.md) kılarak bu işlevselliğini hayata Geçiren `COleServerItem::OnRenderFileData`. Bu işlev, OnGetTextData geçersiz kılma kaldırabilmeniz için temel Bu bağlantı noktası için önemli değildir.  
  
 Ele alınmayan birçok daha fazla hata svritem.cpp de vardır. Bunlar "gerçek" hataları değildir — önceki hataları yalnızca hatalardır.  
  
```  
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters  
```  
  
 `COleServerItem::CopyToClipboard`artık 'bIncludeNative' bayrağı destekler. İlk parametre kaldırmak için yerel veriler (sunucu öğesi'nin serileştirme işlevi tarafından yazılan veriler) her zaman kopyalanır. Ayrıca, `CopyToClipboard` FALSE döndürme yerine bir hata oluştuğunda bir özel durum oluşturur. Kod CServerView::OnEditCopy için aşağıdaki gibi değiştirin:  
  
```  
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
  
 Daha fazla hata vardı daha OCLIENT aynı sürümü için HIERSVR MFC 2.0 sürümünü derlemeden kaynaklanan rağmen vardı gerçekten daha az değişiklik.  
  
 Bu noktada HIERSVR derlemek ve bağlamak ve OLE sunucusu, ancak sonraki uygulanacak yerinde düzenleme özelliği olmadan işlev.  
  
## <a name="adding-visual-editing"></a>"Görsel düzenleme" ekleme  
 Bu sunucu uygulama "Görsel düzenleme" (veya yerinde etkinleştirme) eklemek için ilişkin halletmeniz gerekir yalnızca birkaç şey vardır:  
  
-   Öğe yerinde etkin olduğunda kullanılacak bir özel menü kaynak gerekir.  
  
-   Bu uygulama bir araç sahiptir, bu nedenle, yalnızca bir alt kümesini (yukarıda belirtilen menü kaynağı eşleşir) menü komutlarını sunucudan kullanılabilir eşleştirilecek normal araç taşıyan bir araç çubuğu gerekir.  
  
-   Türetilen yeni bir sınıf gereken `COleIPFrameWnd` yerinde kullanıcı arabirimi sağlayan (çok türetilen CMainFrame benzer şekilde `CMDIFrameWnd`, MDI kullanıcı arabirimi sağlar).  
  
-   Bu özel kaynakları ve sınıfları hakkında framework bildirmeniz gerekir.  
  
 Menü kaynağı oluşturmak kolaydır. Visual C++ çalıştırın, IDR_HIERSVRTYPE_SRVR_IP adlı menü kaynak menüsü kaynak IDR_HIERSVRTYPE kopyalayın. Böylece yalnızca düzenleme ve Yardım menüsü açılır sol menü değiştirin. Düzenle ve Yardım menülerini Between menüye iki ayırıcı eklemek (gibi görünmelidir: düzenleme &#124; &#124; Yardım). İçindeki "Menüler ve kaynaklar: menü birleştirme" Bu ayırıcılar ne anlama geldiğini ve sunucu ve kapsayıcı menüleri nasıl birleştirilir ile ilgili daha fazla bilgi için bkz *OLE 2 sınıfları*.  
  
 Bit eşlem alt araç için kolayca kullanıma "Server" seçeneği ile tek bir yeni oluşturulan AppWizard uygulamasından kopyalayarak oluşturulabilir. Bu bit eşlemi ardından Visual C++ aktarılabilir. Bir kimliği IDR_HIERSVRTYPE_SRVR_IP bit eşlem verdiğinizden emin olun.  
  
 Sınıfın türetildiği `COleIPFrameWnd` server desteği ile oluşturulan AppWizard uygulamadan kopyalanabilir. Her iki dosya IPFRAME kopyalayın. CPP ve IPFRAME. H ve projeye ekleyin. Olduğundan emin olun `LoadBitmap` IDR_HIERSVRTYPE_SRVR_IP, önceki adımda oluşturduğunuz bit eşlem çağrı anlamına gelmektedir.  
  
 Tüm yeni kaynakları ve sınıfları oluşturulan, framework bunlar hakkında bilir (ve bu uygulamayı şimdi yerinde düzenlemeyi destekler bilir böylece) gerekli kodu ekleyin. Bu biraz daha fazla parametre ekleyerek yapılır `SetServerInfo` Çağır `InitInstance` işlevi:  
  
```  
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,  
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```  
  
 Artık yerinde çalıştırılmaya hazır herhangi kapsayıcısında yerinde etkinleştirmeyi de destekler. Ancak, yine kodda gizlenmiş bir küçük hata yoktur. HIERSVR kullanıcı farenin sağ düğmesiyle bastığında görüntülenen bir bağlam menüsü destekler. HIERSVR tam olarak açık, ancak bir katıştırma yerinde düzenlerken çalışmaz, bu menü çalışır. Neden bu tek satırlık bir CServerView::OnRButtonDown kodda sabitlenmiş:  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```  
  
 Başvuru fark **AfxGetApp() -> m_pMainWnd**. Sunucu yerinde etkin olduğunda, ana pencereyi sahiptir ve m_pMainWnd ayarlanmış, ancak genelde görünmez durumdadır. Bu pencere başvurduğu Ayrıca, *ana* penceresi uygulamanın sunucu tam olarak olduğunda görüntülenen MDI çerçeve penceresi açın veya tek başına çalıştırın. Etkin pencereyi başvurmuyor — yerinde olduğunda etkinleştirilmiş olduğu bir çerçeve penceresinde türetilen `COleIPFrameWnd`. Bile, düzenleme yerinde MFC bu sürümü yeni bir işlev eklediğinde doğru etkin pencereyi almak için `AfxGetMainWnd`. Genellikle, bu işlevi yerine kullanması gerekir **AfxGetApp() -> m_pMainWnd**. Bu kod şu şekilde değiştirmesi gerekir:  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetMainWnd());
```  
  
 Şimdi en düşük düzeyde işlev yerinde etkinleştirme için etkin bir OLE sunucusu var. Ancak hala birçok özellik MFC/OLE1 kullanılamayan MFC/OLE 2 ile kullanılabilir. Daha fazla fikir için HIERSVR örnek uygulamak isteyebilirsiniz özellikleri bakın. HIERSVR uygulayan özelliklerinden bazıları aşağıda listelenmiştir:  
  
-   , Kapsayıcı göre doğru WYSISYG davranışı için yakınlaştırma.  
  
-   Sürükle / bırak ve özel Pano biçimi.  
  
-   Seçim olarak kapsayıcı pencere kaydırma değiştirilir.  
  
 MFC 3.0 HIERSVR örnekte biraz farklı bir tasarım sunucu öğelerinden için de kullanır. Bu bellek korunmasına yardımcı olur ve bağlantılarınızı daha esnek hale getirir. HIERSVR 2.0 sürümü ile her düğüm ağacında *olan bir* `COleServerItem`. `COleServerItem`kesinlikle gerekli bu düğümlerinin her biri için olandan biraz daha yükünü taşıyan ancak `COleServerItem` etkin her bağlantı için gereklidir. Ancak çoğunlukla, çok az sayıda etkin bağlantıları vardır herhangi bir zamanda. Bu daha verimli hale getirmek için MFC bu sürümünde HIERSVR düğümden ayıran `COleServerItem`. Her iki bir CServerNode sahiptir ve **CServerItem** sınıfı. **CServerItem** (türetilmiş `COleServerItem`) yalnızca gerektiğinde oluşturulur. Kapsayıcı (veya kapsayıcıları), belirli bir düğüme belirli bu bağlantıyı kullanan durdurduğunuzda, CServerNode ile ilişkili CServerItem Nesne silindi. Bu, daha esnek ve daha verimli tasarımdır. Birden çok seçim bağlantılarıyla ilgilenirken, esneklik devreye girer. Bu iki HIERSVR sürümlerinin hiçbiri birden fazla seçimi destekler, ancak çok daha kolay eklemek için (ve bu tür seçimlere bağlantılarını desteklemek için) HIERSVR, MFC 3.0 sürümü ile bu yana `COleServerItem` yerel verileri ayrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

