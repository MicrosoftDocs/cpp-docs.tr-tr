---
title: CMFCPropertySheet sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53ec20a6fb45efc3848381d165256a429b80a386
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040018"
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet sınıfı
`CMFCPropertySheet` Sınıfı, burada her özellik sayfası belirtilen bir sayfa sekmesi, araç çubuğu düğmesi, ağaç denetim düğümü veya bir liste öğesi tarafından bir özellik sayfası destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Oluşturan bir `CMFCPropertySheet` nesnesi.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertySheet::AddPage](#addpage)|Bir sayfa özellik sayfasına ekler.|  
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Ağaç denetimi için yeni bir özellik sayfası ekler.|  
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Ağaç denetimi için yeni bir düğüm ekler.|  
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Sayfanın üst kısmındaki bir özel üst bilgi çizmek için her alan ayırır.|  
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Geçerli üstbilgi yüksekliğini alır.|  
|[CMFCPropertySheet::GetLook](#getlook)|Geçerli özellik sayfası görünümünü belirten bir numaralandırma değeri alır.|  
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Gezinti çubuğu piksel cinsinden genişliği yeniden dener.|  
|[CMFCPropertySheet::GetTab](#gettab)|Geçerli özellik sayfası denetimi destekleyen iç sekmesi denetim nesnesi alır.|  
|`CMFCPropertySheet::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Geçerli özellik sayfası denetiminin görünümünü başlatır.|  
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Özellik sayfası etkinleştirildiğinde çerçevesi tarafından çağrılır.|  
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Bir özel özellik sayfa üstbilgisi çizmek için çerçevesi tarafından çağrılır.|  
|`CMFCPropertySheet::OnInitDialog`|İşleme [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) ileti. (Geçersiz kılmaları [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Özellik sayfası ağaç denetiminden kaldırmak için framework tarafından çağrılır.|  
|`CMFCPropertySheet::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. (Geçersiz kılmaları `CPropertySheet::PreTranslateMessage`.)|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Bir düğüm ağaç denetiminden kaldırır.|  
|[CMFCPropertySheet::RemovePage](#removepage)|Özellik sayfası özellik sayfasından kaldırır.|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Kullanılan görüntüleri listesini Outlook bölmesi gezinti denetiminde belirtir.|  
|[CMFCPropertySheet::SetLook](#setlook)|Özellik sayfasını görünümünü belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCPropertySheet` Sınıfı, özellik sayfaları, olarak da bilinen sekme iletişim kutuları temsil eder. `CMFCPropertySheet` Sınıfı bir özellik sayfası çeşitli şekillerde görüntüleyebilirsiniz.  
  
 Kullanmak için aşağıdaki adımları gerçekleştirin `CMFCPropertySheet` uygulamanızdaki sınıf:  
  
1.  Öğesinden bir sınıf türetin `CMFCPropertySheet` sınıfı ve bu sınıf, örneğin, CMyPropertySheet olarak adlandırın.  
  
2.  Oluşturmak bir [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) her özellik sayfası için nesnesi.  
  
3.  Çağrı [CMFCPropertySheet::SetLook](#setlook) CMyPropertySheet oluşturucuda yöntemi. Bu yöntemin bir parametresi özellik sayfaları görüntülenen belirtir üst veya sol özellik sayfasının; sekmeleri olarak ya da Microsoft OneNote özellik sayfası stili sekmeleri; Microsoft Outlook araç çubuğu denetimi düğmeleri; Ağaç denetimi düğümlerinde; veya, özellik sayfasının sol tarafındaki öğelerin bir listesi olarak.  
  
4.  Microsoft Outlook araç stilinde bir özellik sayfası oluşturursanız, çağrı [CMFCPropertySheet::SetIconsList](#seticonslist) özellik sayfaları ile birlikte bir resim listesi ilişkilendirilecek yöntemi.  
  
5.  Çağrı [CMFCPropertySheet::AddPage](#addpage) her özellik sayfası için yöntem.  
  
6.  Oluşturma bir `CMFCPropertySheet` denetlemek ve arama kendi `DoModal` yöntemi.  
  
## <a name="illustrations"></a>Çizimler  
 Aşağıdaki çizimde, katıştırılmış bir Microsoft Outlook araç stilinde bir özellik sayfası gösterilmektedir. Outlook araç özellik sayfasının sol tarafında görünür.  
  
 ![CMFCPropertySheet renk denetimleri](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet_color")  
  
 Aşağıdaki çizimde gösterilmektedir içeren bir özellik sayfası bir [CMFCPropertyGridCtrl sınıfı](../../mfc/reference/cmfcpropertygridctrl-class.md) nesnesi. Bu standart bir ortak denetimleri özellik sayfası stilinde bir özellik sayfası nesnesidir.  
  
 ![CMFCPropertySheet liste ve özellik denetimleri](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet_list")  
  
 Ağaç denetimi stilinde olan bir özellik sayfası aşağıdaki çizimde gösterilmektedir.  
  
 ![Özellik ağacı](../../mfc/reference/media/proptree.png "proptree")  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpropertysheet.h  
  
##  <a name="addpage"></a>  CMFCPropertySheet::AddPage  
 Bir sayfa özellik sayfasına ekler.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *fsayfa*  
 Bir sayfa nesnesine işaretçi. Bu parametre olamaz `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, özellik sayfasında en sağdaki sekme olarak belirtilen özellik sayfası ekler. Bu nedenle, soldan sağa sırayla sayfaları eklemek için bu yöntemi kullanın.  
  
 Özellik sayfasını Microsoft Outlook stilinde ise, framework özellik sayfanın sol tarafında gezinti düğmeleri listesini görüntüler. Bu yöntem bir özellik sayfası ekledikten sonra karşılık gelen bir düğme listesine ekler. Bir özellik sayfasını görüntülemek için karşılık gelen düğmesini tıklatın. Özellik sayfaları stilleri hakkında daha fazla bilgi için bkz: [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="addpagetotree"></a>  CMFCPropertySheet::AddPageToTree  
 Ağaç denetimi için yeni bir özellik sayfası ekler.  
  
```  
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,  
    CMFCPropertyPage* pPage,  
    int nIconNum=-1,  
    int nSelIconNum=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pCategory*  
 Bir üst ağaç düğümü işaretçi veya `NULL` belirtilen sayfa üst düzey düğümle ilişkilendirilecek. Çağrı [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Bu işaretçinin elde etmek için yöntemi.  
  
 [in] *fsayfa*  
 Özellik sayfası nesnesine işaretçi.  
  
 [in] *nIconNum*  
 Simge veya hiçbir simge kullanılırsa, -1 sıfır tabanlı dizini. Sayfa seçilmediğinde simgesinin yanında ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.  
  
 [in] *nSelIconNum*  
 Simge veya hiçbir simge kullanılırsa, -1 sıfır tabanlı dizini. Sayfa seçildiğinde simgesinin yanında ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, özellik sayfası bir ağaç denetimi yaprak ekler. Özellik sayfası eklemek için oluşturma bir `CMFCPropertySheet` nesne, çağrı [CMFCPropertySheet::SetLook](#setlook) yöntemiyle *Ara* parametre kümesine `CMFCPropertySheet::PropSheetLook_Tree`ve özellik sayfası eklemek için bu yöntemi kullanın .  
  
##  <a name="addtreecategory"></a>  CMFCPropertySheet::AddTreeCategory  
 Ağaç denetimi için yeni bir düğüm ekler.  
  
```  
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,  
    int nIconNum=-1,  
    int nSelectedIconNum=-1,  
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszLabel*  
 Düğümün adı.  
  
 [in] *nIconNum*  
 Simge veya hiçbir simge kullanılırsa, -1 sıfır tabanlı dizini. Sayfa seçilmediğinde simgesinin yanında ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.  
  
 [in] *nSelectedIconNum*  
 Simge veya hiçbir simge kullanılırsa, -1 sıfır tabanlı dizini. Sayfa seçildiğinde simgesinin yanında ağaç denetimi özellik sayfası görüntülenir. Varsayılan değer -1'dir.  
  
 [in] *pParentCategory*  
 Bir üst ağaç düğümü işaretçi veya `NULL` belirtilen sayfa üst düzey düğümle ilişkilendirilecek. Bu parametre ile [CMFCPropertySheet::AddTreeCategory](#addtreecategory) yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ağaç denetimindeki yeni düğümü için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ağaç denetimi aynı zamanda bir kategori olarak adlandırılır, yeni bir düğüm eklemek için bu yöntemi kullanın. Bir düğüm eklemek için oluşturun bir `CMFCPropertySheet` nesne, çağrı [CMFCPropertySheet::SetLook](#setlook) yöntemiyle *Ara* parametre kümesine `CMFCPropertySheet::PropSheetLook_Tree`ve ardından düğümü eklemek için bu yöntemi kullanın.  
  
 Bu yöntemin dönüş değeri yapılan sonraki çağrılar kullanın [CMFCPropertySheet::AddPageToTree](#addpagetotree) ve [CMFCPropertySheet::AddTreeCategory](#addtreecategory).  
  
##  <a name="cmfcpropertysheet"></a>  CMFCPropertySheet::CMFCPropertySheet  
 Oluşturan bir `CMFCPropertySheet` nesnesi.  
  
```  
CMFCPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pszCaption*  
 Özellik sayfası başlığını içeren bir dize. Olamaz `NULL`.  
  
 [in] *nIDCaption*  
 Özellik sayfası başlığını içeren bir kaynak kimliği.  
  
 [in] *pParentWnd*  
 İşaretçi özellik sayfasının üst penceresine veya `NULL` üst pencere uygulamanın ana penceresi ise. Varsayılan değer `NULL` şeklindedir.  
  
 [in] *iSelectPage*  
 Üst özellik sayfasının sıfır tabanlı dizini. Varsayılan değer 0’dır.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametreler için daha fazla bilgi için bkz: [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) Oluşturucusu.  
  
##  <a name="enablepageheader"></a>  CMFCPropertySheet::EnablePageHeader  
 Sayfanın üst kısmındaki bir özel üst bilgi çizmek için her alan ayırır.  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nHeaderHeight*  
 Üstbilginin piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Değerini kullanacak şekilde *nHeaderHeight* özel bir üstbilgi çizmek için parametre geçersiz kılma [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) yöntemi.  
  
##  <a name="getheaderheight"></a>  CMFCPropertySheet::GetHeaderHeight  
 Geçerli üstbilgi yüksekliğini alır.  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üstbilginin piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [CMFCPropertySheet::EnablePageHeader](#enablepageheader) bu yöntemi çağırmadan önce yöntemi.  
  
##  <a name="getlook"></a>  CMFCPropertySheet::GetLook  
 Geçerli özellik sayfası görünümünü belirten bir numaralandırma değeri alır.  
  
```  
PropSheetLook GetLook() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik sayfasını görünümünü belirten numaralandırma değerlerinden biri. Olası değerler listesi için bkz: Açıklamalar bölümünde numaralandırması tablosu [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="getnavbarwidth"></a>  CMFCPropertySheet::GetNavBarWidth  
 Gezinti çubuğunun genişliğini alır.  
  
```  
int GetNavBarWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gezinti çubuğu piksel cinsinden genişliği.  
  
##  <a name="gettab"></a>  CMFCPropertySheet::GetTab  
 Geçerli özellik sayfası denetimi destekleyen iç sekmesi denetim nesnesi alır.  
  
```  
CMFCTabCtrl& GetTab() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir iç sekme denetimi nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özellik sayfası, gezinti düğmelerini veya sekmeli sayfalar kümesi listesi bir ağaç denetimi gibi farklı stillerde görüntülenir şekilde ayarlayabilirsiniz.  
  
 Bu yöntemi çağırmadan önce çağrısı [CMFCPropertySheet::SetLook](#setlook) özellik sayfası denetiminin görünümünü ayarlamak için yöntem. ' I çağırın [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) iç sekme denetimi nesneyi başlatmak için yöntem. Sekme denetimi nesnesini almak ve özellik sayfasında sekmelerle çalışmak için söz konusu nesne kullanmak için bu yöntemi kullanın.  
  
 Bu yöntem, özellik sayfası denetimi Microsoft OneNote stilde görünmesi ayarlanmamışsa hata ayıklama modunda onaylar.  
  
##  <a name="initnavigationcontrol"></a>  CMFCPropertySheet::InitNavigationControl  
 Geçerli özellik sayfası denetiminin görünümünü başlatır.  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik sayfası denetimi penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfası denetimi sekmeli sayfalar, ağaç denetimi ya da gezinti düğmeleri listesi gibi birkaç farklı form görüntülenebilir. Kullanım [CMFCPropertySheet::SetLook](#setlook) özellik sayfası denetiminin görünümünü belirtmek için yöntem.  
  
##  <a name="onactivatepage"></a>  CMFCPropertySheet::OnActivatePage  
 Özellik sayfası etkinleştirildiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *fsayfa*  
 Etkin özellik sayfasını temsil eden bir özellik sayfası nesnesi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak etkin özellik sayfası görünüme kaydırılan, bu yöntem sağlar. Geçerli özellik sayfası stili Microsoft Outlook bölmesi içeriyorsa, bu yöntem karşılık gelen bir Outlook düğme checked durumuna ayarlar.  
  
##  <a name="ondrawpageheader"></a>  CMFCPropertySheet::OnDrawPageHeader  
 Bir özel özellik sayfası için üstbilgi çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawPageHeader(
    CDC* pDC,  
    int nPage,  
    CRect rectHeader);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı işaretçi.  
  
 [in] *nPage*  
 Sıfır tabanlı özellik sayfa numarası.  
  
 [in] *rectHeader*  
 Üstbilgi çizmek konumu belirtir sınırlayıcı dikdörtgenini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem hiçbir şey yapmaz. Bu yöntemi geçersiz kılarsanız, çağrı [CMFCPropertySheet::EnablePageHeader](#enablepageheader) framework bu yöntemi çağırmadan önce yöntemi.  
  
##  <a name="onremovetreepage"></a>  CMFCPropertySheet::OnRemoveTreePage  
 Özellik sayfası ağaç denetiminden kaldırmak için framework tarafından çağrılır.  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *fsayfa*  
 Kaldırmak üzere özellik sayfasını temsil eden bir özellik sayfası nesnesi işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
##  <a name="removecategory"></a>  CMFCPropertySheet::RemoveCategory  
 Bir düğüm ağaç denetiminden kaldırır.  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pCategory*  
 İşaretçi kaldırmak için bir kategoriye (düğüm).  
  
### <a name="remarks"></a>Açıklamalar  
 Aynı zamanda bir kategori olarak ağaç denetiminden adlandırılır bir düğümünü kaldırmak için bu yöntemi kullanın. Kullanım [CMFCPropertySheet::AddTreeCategory](#addtreecategory) ağaç denetimi için bir düğüm eklemek için yöntem.  
  
##  <a name="removepage"></a>  CMFCPropertySheet::RemovePage  
 Özellik sayfası özellik sayfasından kaldırır.  
  
```  
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *fsayfa*  
 Kaldırmak üzere özellik sayfasını temsil eden özellik sayfası nesnesine işaretçi. Olamaz `NULL`.  
  
 [in] *nPage*  
 Sayfanın kaldırmak için sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, belirtilen özellik sayfasını kaldırır ve ilişkili onun penceresi yok eder. Özellik sayfası nesne *fsayfa* parametresi belirtir değil bozulur kadar [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) penceresi kapatıldığında.  
  
##  <a name="seticonslist"></a>  CMFCPropertySheet::SetIconsList  
 Kullanılan görüntüleri listesini Outlook bölmesi gezinti denetiminde belirtir.  
  
```  
BOOL SetIconsList(
    UINT uiImageListResID,  
    int cx,  
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiImageListResID*  
 Görüntü listesi kaynak kimliği.  
  
 [in] *cx*  
 Görüntü listesinde simgelerin piksel cinsinden genişliği.  
  
 [in] *clrTransparent*  
 Saydam Görüntü rengi. Bu renk olan bölümleri resminin saydam olacaktır. Renk Eflatun, RGB(255,0,255) varsayılan değerdir.  
  
 [in] *hIcons*  
 Varolan bir görüntü listesi için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sözdizimi, ilk yönteminde aşırı yükleme `TRUE` bu yöntem başarılı olursa Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfasını Microsoft Outlook stilinde ise, framework gezinti düğmeleri, Outlook bölmesi denetimi özelliği sayfanın sol tarafında adlı bir listesini görüntüler. Outlook bölmesi denetimi tarafından kullanılacak resim listesi ayarlamak için bu yöntemi kullanın.  
  
 Bu yöntem destek yöntemleri hakkında daha fazla bilgi için bkz: [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) ve [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Bir özellik sayfası stilini ayarlama hakkında daha fazla bilgi için bkz: [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="setlook"></a>  CMFCPropertySheet::SetLook  
 Özellik sayfasını görünümünü belirtir.  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *arayın*  
 Özellik sayfasını görünümünü belirten numaralandırma değerlerinden biri. Bir özellik sayfası için varsayılan stili `CMFCPropertySheet::PropSheetLook_Tabs`. Daha fazla bilgi için bu konunun Açıklamalar bölümündeki tabloya bakın.  
  
 [in] *nNavControlWidth*  
 Gezinti denetimin piksel cinsinden genişliği. Varsayılan değer 100’dür.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik Sayfası penceresini oluşturmadan önce varsayılan dışındaki stilinde bir özellik sayfasını görüntülemek için bu yöntemi çağırın.  
  
 Aşağıdaki tablo içinde belirtilen numaralandırma değerlerini listeler *Ara* parametresi.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(Varsayılan) Her özellik sayfası için bir sekme görüntüler. Sekmeler ve tek bir satırda sığmayacak kadar çok daha fazla sekme varsa Yığılmış özellik sayfasının en üstünde görüntülenir.|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Microsoft Outlook çubuğunun özellik sayfasının sol tarafında stili gezinti düğmeleri listesini görüntüler. Her düğme listesinde bir özellik sayfasında karşılık gelir. Liste görünür alana sığmayacak kadar çok daha fazla düğme varsa framework kaydırma oklarının görüntüler.|  
|`CMFCPropertySheet::PropSheetLook_Tree`|Ağaç denetimi özellik sayfasının sol tarafında görüntüler. Ağaç denetimi üst veya alt her düğümün bir özellik sayfasında karşılık gelir. Ağaç denetimi görünür alana sığmayacak kadar çok daha fazla düğüm varsa framework kaydırma oklarının görüntüler.|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Microsoft OneNote stilinde her özellik sayfasının bir sekmesinde görüntülenir. Framework sekmeleri özellik sayfasının en üstünde görüntüler ve kaydırma oklarının'den daha fazla sekme varsa tek bir satırda sığmayacak.|  
|`CMFCPropertySheet::PropSheetLook_List`|Özellik sayfasının sol tarafında görüntüler. Her liste öğesi bir özellik sayfasında karşılık gelir. Liste görünür alana sığmayacak kadar çok daha fazla liste öğeleri varsa framework kaydırma oklarının görüntüler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage sınıfı](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
