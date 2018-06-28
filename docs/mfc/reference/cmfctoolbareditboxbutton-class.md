---
title: CMFCToolBarEditBoxButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e6c4493239030380ab935d473af48d4107556d4
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041428"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton sınıfı
Bir düzen denetimi içeren bir araç çubuğu düğmesi ( [CEdit sınıfı](../../mfc/reference/cedit-class.md)).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Oluşturan bir `CMFCToolBarEditBoxButton` nesnesi.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Bir kullanıcı özelleştirmesi sırasında düğmesi uzatma olup olmadığını belirtir. (Geçersiz kılmaları [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi özelliklerini geçerli düğme kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Yeni bir düzen denetim düğmesini oluşturur.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|İlk alır `CMFCToolBarEditBoxButton` belirtilen komut kimliği olan uygulama nesnesinde|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Belirtilen komut kimliğe sahip ilk düzenleme kutusu araç çubuğu denetimi metni alır|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini alır.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Düzenleme kutusu düğmesi düzenleme parçası sınırlayıcı dikdörtgenini alır.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Düğmesini katıştırılmış düzenleme denetimine işaretçi döndürür.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Araç çubuğu düğmesi ile ilişkili bir pencere tanıtıcının alır. (Geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|İstemci alanını çizilmesi gerektiği düğmesinin bölgesini alır. (Geçersiz kılmaları [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Bir kullanıcı düğmesine tıkladığında düğmesinin kenarlık görüntülenip görüntülenmeyeceğini belirler. (Geçersiz kılmaları [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Düzenleme kutusu düğmeleri düz bir stil sahip olup olmadığını belirler.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Düğme işler olup olmadığını belirtir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) ileti. (Geçersiz kılmaları [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Düğme eklendiğinde çerçevesi tarafından çağrılır bir **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Takma durumunu ve belirtilen cihaz bağlamı düğmesini boyutunu hesaplamak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Yeni bir araç çubuğu düğmesi takıldığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Kullanıcının fare düğmesini tıklattığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Üst araç WM_CTLCOLOR iletisi işlediğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Belirtilen stilleri ve seçenekleri kullanarak düğmesi çizmek için framework tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Düğme çizmek için framework tarafından çağrılan **komutları** bölmesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Genel yazı tipi değiştiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Üst araç taşındığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Düğme olduğunda görünür veya görünmez çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Üst araç boyutuna değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek için düğmesini çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Üst araç çubuğu araç ipucu metni güncelleştirdiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|Bu nesne arşivden okur veya arşive yazar. (Geçersiz kılmaları [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Sağlanan doldurur `CAccessibilityData` araç çubuğu düğmesinden erişilebilirlik verilerle nesnesi. (Geçersiz kılmaları [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|Metin düğmesinin düzenleme denetimi ayarlar.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Belirtilen komut Kimliğine sahip ve bu düğme düzenleme denetiminde metni ayarlar Düzenle denetim düğmesi bulur.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini belirtir.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Düzenleme kutusu düğmelerin düz stil görünümünü uygulamada belirtir.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Düğme stilini belirtir. (Geçersiz kılmaları [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir araç için bir düzenleme kutusu düğmesi eklemek için aşağıdaki adımları izleyin:  
  
 1. Bir kukla kaynağı kimliği üst araç çubuğu kaynak düğmesi için ayrılmış.  
  
 2. Oluşturmak bir `CMFCToolBarEditBoxButton` nesnesi.  
  
 3. AFX_WM_RESETTOOLBAR iletisini işler ileti işleyicisi kukla düğmesini kullanarak yeni birleşik giriş kutusu düğmesi ile değiştirin [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Daha fazla bilgi için bkz: [izlenecek yol: üzerinde denetimler koyma araç'çubukları](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCToolBarEditBoxButton` sınıfı. Örnek, belirtmek bir kullanıcı düğmesini özelleştirme sırasında uzatma, bir kullanıcı düğmesine tıkladığında düğmesinin kenarlık görüntülendiğini belirten, metin kutusu denetiminde metni ayarlama Uy düzenleme kutusu düğmeleri düz stil görünümünü belirtmek olduğunu nasıl gösterir kimlik doğrulama ve bir araç çubuğu stilini düzenleme kutusu denetimi belirtin.  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbareditboxbutton.h  
  
##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched  
 Bir kullanıcı özelleştirmesi sırasında düğmesi uzatma olup olmadığını belirtir.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bir araç çubuğu düğmesini özelleştirme sırasında uzatmak kullanıcı framework izin vermiyor. Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) bir düzenleme kutusu araç çubuğu düğmesini özelleştirme sırasında uzatmak kullanıcı sağlayarak.  
  
##  <a name="cmfctoolbareditboxbutton"></a>  CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
 Oluşturan bir [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) nesnesi.  
  
```  
CMFCToolBarEditBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=ES_AUTOHSCROLL,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiID*  
 Denetim kimliğini belirtir.  
  
 [in] *iImage*  
 Araç çubuğu görüntüsünü sıfır tabanlı dizini belirtir. Görüntü bulunan [CMFCToolBarImages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesinin [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfı korur.  
  
 [in] *dwStyle*  
 Düzenle denetim stilini belirtir.  
  
 [in] *iWidth*  
 Düzenleme denetimi piksel cinsinden genişliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Oluşturucu aşağıdaki birleşimi Düzenle denetim stilini ayarlar:  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 Denetimin varsayılan genişliğini 150 pikseldir.  
  
##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom  
 Başka bir araç çubuğu düğmesi özelliklerini geçerli düğme kopyalar.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *src*  
 Kaynak düğmesini başvuru kopyalanacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu araç çubuğu düğmesi için başka bir araç çubuğu düğmesini kopyalamak için bu yöntemi çağırın. *src* türünde olmalıdır `CMFCToolBarEditBoxButton`.  
  
##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit  
 Yeni bir düzen denetim düğmesini oluşturur.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Düzenle denetim üst pencerenin belirtir. NULL olmamalıdır.  
  
 [in] *rect*  
 Düzenle denetim boyutunu ve konumunu belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan düzenleme denetimine işaretçi; Bu `NULL` denetimin oluşturulmasını ve ek başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CMFCToolBarEditBoxButton` iki adımda nesne. İlk Oluşturucusu arayın ve ardından arama `CreateEdit`, hangi Windows düzenleme denetimi oluşturur ve ona iliştirir `CMFCToolBarEditBoxButton` nesnesi.  
  
##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd  
 İlk alır `CMFCToolBarEditBoxButton` belirtilen komut kimliği olan uygulama nesnesinde  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Komut Kimliği almak düğmesinin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk `CMFCToolBarEditBoxButton` belirtilen komut kimliği olan uygulama nesnesinde veya `NULL` böyle bir nesne varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu paylaşılan yardımcı yöntem yöntemler tarafından da kullanılır [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) ve [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) ayarlamak veya ilk düzenleme kutusu araç metni almak için Belirtilen komut kimliğe sahip denetimi  
  
##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll  
 Belirtilen komut kimliğe sahip ilk düzenleme kutusu araç çubuğu denetimi metni alır  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Düğme içeriğini almak üzere komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` belirtilen komut kimliğe sahip ilk düzenleme kutusu araç çubuğu denetimi metnini içeren nesne  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem boş dize yoksa döndürür `CMFCToolBarEditBoxButton` nesneler sahip belirtilen komut kimliği.  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID  
 Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini alır.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesi ilişkili kısayol menüsü varsa, düğme veya 0 ile ilişkili olan kısayol menüsünün kaynak kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve kaynak kimliği kullanıcı düğmesini tıklattığında kısayol menüsünün oluşturmak için kullanılır.  
  
##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder  
 Düzenleme kutusu düğmesi düzenleme parçası sınırlayıcı dikdörtgenini alır.  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *rectBorder*  
 Bir başvuru `CRect` sınırlayıcı dikdörtgenini alan nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem istemci koordinatları düzenleme denetimine sınırlayıcı dikdörtgenini alır. Bu, bir piksel dikdörtgenin her yönde boyutunu genişletir.  
  
 [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) yöntemi çevresinde kenarlık çizer zaman bu yöntemi çağırır bir `CMFCToolBarEditBoxButton` nesnesi.  
  
##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox  
 Bir işaretçi döndürür [CEdit sınıfı](../../mfc/reference/cedit-class.md) düğmesini katıştırılmış denetim.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CEdit sınıfı](../../mfc/reference/cedit-class.md) düğmeyi içeren denetim. Bu `NULL` varsa `CEdit` denetim henüz oluşturulmadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturduğunuz `CEdit` çağırarak denetim [CMFCToolBarEditBoxButton::CreateEdit](#createedit).  
  
##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd  
 Araç çubuğu düğmesi ile ilişkili bir pencere tanıtıcının alır.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesi ile ilişkili pencere işleyicisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçersiz kılmaları [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) düzenleme kutusu düğmesi düzenleme denetimi parçası pencere tanıtıcısı döndürerek yöntemi.  
  
##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect  
 İstemci alanını çizilmesi gerektiği düğmesinin bölgesini alır.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CRect` çizilmesi gerektiği bölge belirtir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), metin etiketi alanının bölgede ekleyerek.  
  
##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder  
 Bir kullanıcı düğmesine tıkladığında düğmesinin kenarlık görüntülenip görüntülenmeyeceğini belirler.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme seçildiğinde kenarlığını görüntülerse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), denetimi görünür durumdaysa tarafından sıfır olmayan bir değer döndürüyor.  
  
##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode  
 Düzenleme kutusu düğmeleri düz bir stil sahip olup olmadığını belirler.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmeleri düz bir stil varsa sıfır olmayan; Aksi takdirde, 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, düz bir stil düzenleme kutusu düğmeleri sahiptir. Kullanım [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) uygulamanız için düz stil görünümünü değiştirmek için yöntem.  
  
##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand  
 Düğme işler olup olmadığını belirtir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) ileti.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iNotifyCode*  
 Komutu ile ilişkili bildirim iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Düğme WM_COMMAND ileti işlediğinde veya `FALSE` iletinin üst araç tarafından işlenmiş olduğunu belirtmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Göndermek üzere olduğunda framework bu metodu çağıran bir [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) üst pencere iletisi.  
  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) işleme tarafından [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687) bildirim. Bu nesnenin aynı komutu kimlikli her düzenleme kutusu için bu nesnenin metin etiketi metin etiketini ayarlar.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 Düğme eklendiğinde çerçevesi tarafından çağrılır bir **Özelleştir** iletişim kutusu.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) özelliklerini bu nesne ile aynı komut Kimliğine sahip herhangi bir araç çubuğu düzenleme kutusu denetiminde kopyalayarak. Bu nesne ile aynı komut Kimliğine sahip bir düzenleme kutusu denetimini hiçbir araç varsa, bu yöntem hiçbir şey yapmaz.  
  
 Hakkında daha fazla bilgi için **Özelleştir** iletişim kutusu, bkz: [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd  
 Yeni bir araç çubuğu düğmesi takıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Yeni üst pencere için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) iç yeniden tarafından `CEdit` nesnesi.  
  
##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick  
 Kullanıcının fare düğmesini tıklattığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Kullanılmayan.  
  
 [in] *bDelay*  
 Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin click ileti işlediğinde sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)), sıfır olmayan bir değer döndürerek iç `CEdit` nesnesidir görünür.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor  
 Üst araç WM_CTLCOLOR iletisi işlediğinde çerçevesi tarafından çağrılır.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Düğme görüntüler cihaz bağlamı.  
  
 [in] *nCtlColor*  
 Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Genel pencere fırça için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) sağlanan cihaz bağlamı metin ve arka plan renklerini genel metin ve arka plan renklerini, sırasıyla ayarlayarak.  
  
 Uygulamanız için kullanılabilen genel seçenekleri hakkında daha fazla bilgi için bkz: [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 Genel yazı tipi değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)), genel yazı tipi yazı tipini denetimi değiştirerek.  
  
 Uygulamanız için kullanılabilen genel seçenekleri hakkında daha fazla bilgi için bkz: [AFX_GLOBAL_DATA yapısı](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove  
 Üst araç taşındığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem varsayılan sınıf uygulaması geçersiz kılar ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) iç konumunu güncelleştirerek `CEdit` nesnesi  
  
##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow  
 Düğme olduğunda görünür veya görünmez çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bBilgi Göster*  
 Düğmenin görünür olup olmadığını belirtir. Bu parametre ise `TRUE`, düğmesi görünür. Aksi takdirde düğmesi görünür değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), düğme görüntüleyerek *bBilgi Göster* olan `TRUE`. Aksi takdirde, bu yöntem düğmesini gizler.  
  
##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize  
 Üst araç boyutuna değiştirir veya konumu ve bu değişiklik neden boyutunu değiştirmek için düğmesini çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iSize*  
 Yeni genişliğini piksel cinsinden düğmenin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem varsayılan sınıf uygulaması geçersiz kılmaları [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), boyutunu ve konumunu iç güncelleştirerek `CEdit` nesnesi.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarEditBoxButton::OnUpdateToolTip  
 Üst araç çubuğu araç ipucu metni güncelleştirdiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Kullanılmayan.  
  
 [in] *iButtonIndex*  
 Kullanılmayan.  
  
 [in] *wndToolTip*  
 Araç İpucu metni görüntüleyen denetim.  
  
 [out] *str*  
 A `CString` güncelleştirilmiş araç ipucu metni alan nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu metni yöntemi güncelleştirmeleri olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) düğmesini Düzenle bölümüyle ilişkili araç ipucu metni görüntüleyerek. Varsa iç `CEdit` nesne `NULL` veya pencere tanıtıcısı `CEdit` nesneyi var olan bir pencere belirlemek değil, bu yöntem, hiçbir şey yapmaz ve döndürür `FALSE`.  
  
##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents  
 Metni metin kutusu denetiminde ayarlar.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *sContents*  
 Ayarlanacak yeni metni belirtir.  
  
##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll  
 Bulur bir [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) belirtilen komut Kimliğine sahip ve belirtilen metni, metin kutusundaki ayarlar nesnesi.  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Metin değiştirilecek denetim komut Kimliğini belirtir.  
  
 [in] *strContents*  
 Ayarlanacak yeni metni belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin ayarlarsanız sıfır olmayan; 0 ise `CMFCToolBarEditBoxButton` belirtilen komut kimliği olan denetim yok.  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID  
 Kısayol menüsünün düğmesi ile ilişkili kaynak Kimliğini belirtir.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Kısayol menüsünün kaynak kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve kaynak kimliği kullanıcı araç çubuğu düğmesini tıklattığında kısayol menüsünün oluşturmak için kullanılır.  
  
##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode  
 Düzenleme kutusu düğmelerin düz stil görünümünü uygulamada belirtir.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bFlat*  
 Düzenleme kutusu düğmelerinin düz stili. Bu parametre ise `TRUE`, düz stil görünümü etkinleştirilir; Aksi takdirde düz stil görünümü devre dışı bırakılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Düzenleme kutusu düğmeleri için varsayılan düz stili `TRUE`. Kullanım [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) uygulamanız için düz stil görünümü alma yöntemi.  
  
##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle  
 Araç çubuğu stilini düzenleme kutusu denetimi belirtir.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nStyle*  
 Ayarlamak için yeni bir stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ayarlar [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) için *nStyle* uygulama Özelleştir modunda olduğunda ve uygulama (bkz: Özelleştirmodundaolmadığındasağlar,ayrıcametinkutusudevredışıbırakır[ CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) ve [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Bkz: [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md) geçerli bir stil bayrakları listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



