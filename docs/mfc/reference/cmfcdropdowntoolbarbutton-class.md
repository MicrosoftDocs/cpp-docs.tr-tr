---
title: "CMFCDropDownToolbarButton sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f9481583c56676d206225ad76f8131c2a79821f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton sınıfı
Tıklandığında, normal bir düğme gibi davranan araç çubuğu düğmesi türü. Ancak, aşağı açılan araç çubuğunu açar ( [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md) kullanıcının tıklatıp araç çubuğu düğmesi tutan durumunda.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Oluşturan bir `CMFCDropDownToolbarButton` nesnesi.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi özelliklerini geçerli düğme kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCDropDownToolbarButton::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Aşağı açılan araç çubuğu açılır.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Metni araç çubuğu düğmesinden menü kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Düğmesi ile ilişkili açılan araç alır.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Aşağı açılan araç şu anda açık olup olmadığını belirler.|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Düğme genişletilmiş kenarlık ile görüntülenip belirler. (Geçersiz kılmaları [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Takma durumunu ve belirtilen cihaz bağlamı düğmesini boyutunu hesaplamak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|İşlenecek çerçevesi tarafından çağrılır [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) ileti. (Geçersiz kılmaları `CMCToolBarButton::OnCancelMode`.)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Yeni bir araç çubuğu düğmesi takıldığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Kullanıcının fare düğmesini tıklattığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Kullanıcının fare düğmesini bıraktığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Üst araç işlediğinde çerçevesi tarafından çağrılır bir `WM_HELPHITTEST` ileti. (Geçersiz kılmaları [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Uygulamanın bir kısayol menüsü üst araç çubuğunda görüntülediğinde sağlanan menü değiştirir. (Geçersiz kılmaları [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Belirtilen stilleri ve seçenekleri kullanarak düğmesi çizmek için framework tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Düğme çizmek için framework tarafından çağrılan **komutları** bölmesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Bu nesne arşivden okur veya arşive yazar. (Geçersiz kılmaları [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Bir kullanıcı düğmesine tıkladığında framework kullanan varsayılan komutu ayarlar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Aşağı açılan araç görüntülenmeden önce bir kullanıcının fare düğmesini basılı gereken süreyi belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CMFCDropDownToolBarButton` düğmesine sağ alt köşesinde küçük bir ok olan bir sıradan düğmesinden farklıdır. Kullanıcı aşağı açılan araç çubuğundan düğme seçtikten sonra framework simgesini (sağ alt köşesindeki küçük oklu düğmesi) en üst düzey araç çubuğu düğmesi görüntüler.  
  
 Aşağı açılan araç uygulama hakkında daha fazla bilgi için bkz: [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 `CMFCDropDownToolBarButton` Nesne verilebilir bir [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesne ve açılır menü ile menü düğmesi olarak görüntülenir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>CMFCDropDownToolbarButton::CopyFrom  
 Başka bir araç çubuğu düğmesi özelliklerini geçerli düğme kopyalar.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`src`  
 Kaynak düğmesini başvuru kopyalanacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu araç çubuğu düğmesi için başka bir araç çubuğu düğmesini kopyalamak için bu yöntemi çağırın. `src`türünde olmalıdır `CMFCDropDownToolbarButton`.  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
 Oluşturan bir `CMFCDropDownToolbarButton` nesnesi.  
  
```  
CMFCDropDownToolbarButton();

 
CMFCDropDownToolbarButton(
    LPCTSTR lpszName,  
    CMFCDropDownToolBar* pToolBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszName`  
 Düğmenin varsayılan metni.  
  
 [in]`pToolBar`  
 Bir işaretçi `CMFCDropDownToolBar` kullanıcı düğmesine bastığında görüntülenen nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci oluşturucu yüklemesini açılan düğmesine ilk düğme araç çubuğundaki kopyalar, `pToolBar` belirtir.  
  
 Genellikle, aşağı açılan araç çubuğu düğmesi metni en son kullanılan düğmesinden araç çubuğunda kullanır, `pToolBar` belirtir. Tarafından belirlenen metin kullanır `lpszName` zaman düğme bir menü düğmesi dönüştürülür veya görüntülenen **komutları** sekmesinde **Özelleştir** iletişim kutusu. Hakkında daha fazla bilgi için **Özelleştir** iletişim kutusu, bkz: [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCDropDownToolbarButton` sınıfı. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>CMFCDropDownToolbarButton::DropDownToolbar  
 Aşağı açılan araç çubuğu açılır.  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Aşağı açılan çerçevenin üst pencere veya `NULL` açılan araç çubuğu düğmesi üst pencerenin kullanılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCDropDownToolbarButton::OnClick](#onclick) yöntemi kullanıcı bastığında ve araç çubuğu düğmesi tutan açılan araç çubuğunu açmak için bu yöntemi çağırır.  
  
 Bu yöntemleri kullanarak açılan araç oluşturur [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) yöntemi. Üst araç dikey yerleştirilmişse, bu yöntem ya da uygun bağlı olarak üst araç sol veya sağ tarafında açılan araç yerleştirir. Aksi takdirde, bu yöntem, üst araç altındaki açılan araç yerleştirir.  
  
 Bu yöntem başarısız olursa `pWnd` olan `NULL` ve açılan araç çubuğu düğmesi bir üst penceresi yok.  
  
##  <a name="exporttomenubutton"></a>CMFCDropDownToolbarButton::ExportToMenuButton  
 Metni araç çubuğu düğmesinden menü kopyalar.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`menuButton`  
 Hedef menü düğmesi referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi çağırır ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) ve ardından hedef menü düğmesi için bu düğmeyi her bir araç çubuğu menü öğesi içeren bir açılır menü ekler. Bu yöntem, açılır menüsünün alt menüler ekleme değil.  
  
 Bu yöntem başarısız olursa üst araç çubuğunda, `m_pToolBar`, olan `NULL` veya temel sınıf uygulamasını döndürür `FALSE`.  
  
##  <a name="getdropdowntoolbar"></a>CMFCDropDownToolbarButton::GetDropDownToolBar  
 Düğmesi ile ilişkili açılan araç alır.  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesi ile ilişkili açılan araç çubuğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `m_pToolBar` veri üyesi.  
  
##  <a name="isdropdown"></a>CMFCDropDownToolbarButton::IsDropDown  
 Aşağı açılan araç şu anda açık olup olmadığını belirler.  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağı açılan araç şu anda açık ise, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework açılan araç kullanılarak açılır [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) yöntemi. Kullanıcı aşağı açılan araç istemci olmayan alanında sol fare düğmesini bastığında framework açılan araç kapatır.  
  
##  <a name="isextrasize"></a>CMFCDropDownToolbarButton::IsExtraSize  
 Düğme genişletilmiş kenarlık ile görüntülenip belirler.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç çubuğu düğmesi ile genişletilmiş bir sınır görüntülenebilir, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Genişletilmiş Kenarlıklar hakkında daha fazla bilgi için bkz: [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).  
  
##  <a name="m_uishowbardelay"></a>CMFCDropDownToolbarButton::m_uiShowBarDelay  
 Aşağı açılan araç görüntülenmeden önce bir kullanıcının fare düğmesini basılı gereken süreyi belirtir.  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Gecikme süresini milisaniye cinsinden ölçülür. Varsayılan değer 500'dür. Bu paylaşılan veri üyesi değerini değiştirerek başka bir gecikme ayarlayabilirsiniz.  
  
##  <a name="oncalculatesize"></a>CMFCDropDownToolbarButton::OnCalculateSize  
 Takma durumunu ve belirtilen cihaz bağlamı düğmesini boyutunu hesaplamak için çerçevesi tarafından çağrılır.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Düğme görüntüler cihaz bağlamı.  
  
 [in]`sizeDefault`  
 Düğme varsayılan boyutu.  
  
 [in]`bHorz`  
 Üst araç çubuğu yerleştirme durumu. Bu parametre `TRUE` araç yatay olarak yerleşik veya kayan, veya `FALSE` araç dikey yerleştirilmişse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `SIZE` piksel cinsinden düğmenin boyutlarını içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)) düğme boyutu yatay boyut için aşağı açılan okunu genişliğini ekleyerek.  
  
##  <a name="onchangeparentwnd"></a>CMFCDropDownToolbarButton::OnChangeParentWnd  
 Yeni bir araç çubuğu düğmesi takıldığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndParent`  
 Yeni üst pencere.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemi geçersiz kılar ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) metin etiketi Temizleme tarafından ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) ve ayarı [ CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) ve [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) veri üyelerine `FALSE`.  
  
##  <a name="onclick"></a>CMFCDropDownToolbarButton::OnClick  
 Kullanıcının fare düğmesini tıklattığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Araç çubuğu düğmesi üst pencere.  
  
 [in]`bDelay`  
 `TRUE`ileti bir gecikmeyle işleneceğini durumunda.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin click ileti işlediğinde sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), aşağı açılan araç durumunu güncelleştirerek.  
  
 Bir kullanıcı araç çubuğu düğmesini tıklattığında, bu yöntem tarafından belirtilen süre bekler bir zamanlayıcı oluşturur [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) veri üyesi ve kullanarakaçılıraçılanaraç[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) yöntemi. Bu yöntem açılan araç çubuğu araç çubuğu düğmesi kullanıcı ikinci kez kapatır.  
  
##  <a name="onclickup"></a>CMFCDropDownToolbarButton::OnClickUp  
 Kullanıcının fare düğmesini bıraktığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin click ileti işlediğinde sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), aşağı açılan araç durumunu güncelleştirerek.  
  
 Etkin değilse bu yöntem açılan araç Zamanlayıcı durdurur. Açıksa, aşağı açılan araç kapatır.  
  
 Açılan araç Zamanlayıcı ve açılan araç hakkında daha fazla bilgi için bkz: [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
##  <a name="oncontexthelp"></a>CMFCDropDownToolbarButton::OnContextHelp  
 Üst araç işlediğinde çerçevesi tarafından çağrılır bir `WM_HELPHITTEST` ileti.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
 Araç çubuğu düğmesi üst pencere.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme Yardım iletisi işlediğinde sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) çağırarak [CMFCDropDownToolbarButton::OnClick](#onclick) yöntemiyle `bDelay` kümesine `FALSE` . Bu yöntem tarafından döndürülen değeri döndürür [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
 Hakkında daha fazla bilgi için `WM_HELPHITTEST message, see` [TN028: Context-Sensitive Yardım Destek](../../mfc/tn028-context-sensitive-help-support.md).  
  
##  <a name="oncustomizemenu"></a>CMFCDropDownToolbarButton::OnCustomizeMenu  
 Uygulamanın bir kısayol menüsü üst araç çubuğunda görüntülediğinde sağlanan menü değiştirir.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMenu`  
 Özelleştirme menüsü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) aşağıdaki menü öğelerini devre dışı bırakarak:  
  
- **Düğme görüntüsü kopyalama**  
  
- **Düğme görünümünü**  
  
- **Görüntü**  
  
- **Metin**  
  
- **Resim ve metin**  
  
 Kısayol menüsünün framework özelleştirme modunda görüntüler değiştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="ondraw"></a>CMFCDropDownToolbarButton::OnDraw  
 Belirtilen stilleri ve seçenekleri kullanarak düğmesi çizmek için framework tarafından çağrılır.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Düğme görüntüler cihaz bağlamı.  
  
 [in]`rect`  
 Düğmenin sınırlayıcı dikdörtgenini.  
  
 [in]`pImages`  
 Araç çubuğu görüntüleri düğmesi ile ilişkili koleksiyonu.  
  
 [in]`bHorz`  
 Üst araç çubuğu yerleştirme durumu. Bu parametre `TRUE` zaman düğme yerleştirilmiştir yatay ve `FALSE` zaman düğme yerleştirilmiştir dikey olarak.  
  
 [in]`bCustomizeMode`  
 Araç çubuğunu özelleştirme modunda olup olmadığını belirtir. Bu parametre `TRUE` araç çubuğunu özelleştirme modunda olduğunda ve `FALSE` araç olmadığında özelleştirme modunda.  
  
 [in]`bHighlight`  
 Düğmesi vurgulanmış olup olmadığını belirtir. Bu parametre `TRUE` zaman düğmesi vurgulanmış ve `FALSE` zaman düğmesi değil vurgulanır.  
  
 [in]`bDrawBorder`  
 Düğme kenarlığını görüntüleyip görüntülemeyeceğini belirtir. Bu parametre `TRUE` düğmesi görüntülediğinizde kenarlığını ve `FALSE` düğmesi değil görüntülediğinizde kenarlığını.  
  
 [in]`bGrayDisabledButtons`  
 Devre dışı düğmeleri gölgelendirme veya devre dışı resim koleksiyonundaki kullanmayı belirtir. Bu parametre `TRUE` ne zaman devre dışı düğmeleri olmalıdır gölgeli ve `FALSE` ne zaman bu yöntem kullanması gereken devre dışı görüntüleri koleksiyonu.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç çubuğu düğmesi çizim özelleştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawoncustomizelist"></a>CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 Düğme çizmek için framework tarafından çağrılan **komutları** bölmesinde **Özelleştir** iletişim kutusu.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Düğme görüntüler cihaz bağlamı.  
  
 [in]`rect`  
 Düğmenin sınırlayıcı dikdörtgenini.  
  
 [in]`bSelected`  
 Olup düğmesi seçilir. Bu parametre ise `TRUE`, düğmesi seçilir. Bu parametre ise `FALSE`, düğme seçilmedi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen cihaz bağlamı düğmeyi piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem özelleştirme iletişim kutusu tarafından çağrılır ( **komutları** sekmesi) ne zaman düğmesi kendisini sahip çizim liste kutusunu görüntülemek için gereklidir.  
  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) düğmesinin metin etiketi düğmesinin adını değiştirerek (diğer bir deyişle, değerine `lpszName` , geçirilen parametre oluşturucuya).  
  
##  <a name="serialize"></a>CMFCDropDownToolbarButton::Serialize  
 Bu nesne arşivden okur veya arşive yazar.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ar`  
 `CArchive` Nesne içinden veya seri hale getirilemedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı uygulama bu yöntemin genişlettiği ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) tarafından üst araç çubuğu kaynak kimliği seri hale getirme. Arşiv zaman yükleme ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) sıfır olmayan bir değer döndürür), bu yöntem ayarlar `m_pToolBar` seri hale getirilmiş kaynak kimliğini içerir. araç çubuğuna veri üyesi  
  
##  <a name="setdefaultcommand"></a>CMFCDropDownToolbarButton::SetDefaultCommand  
 Bir kullanıcı düğmesine tıkladığında framework kullanan varsayılan komutu ayarlar.  
  
```  
void SetDefaultCommand(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmd`  
 Varsayılan komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı düğmesine tıkladığında, framework yürütür varsayılan komutu belirtmek için bu yöntemi çağırın. Belirtilen komut kimliği bir öğesiyle `uiCmd` üst açılan araç çubuğunda yer almalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



