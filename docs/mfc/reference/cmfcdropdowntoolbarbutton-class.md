---
title: CMFCDropDownToolbarButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ea64180a9f7abf37f379e3e8feccc4ee41fd44
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850202"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton sınıfı
Tıklandığında normal bir düğme gibi davranan araç çubuğu düğmesi türü. Ancak, bir açılır araç çubuğunu açar ( [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md) kullanıcının bastığında ve araç çubuğu düğmesini içeren.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Oluşturur bir `CMFCDropDownToolbarButton` nesne.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi özelliklerini geçerli düğmeyi kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCDropDownToolbarButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Bir açılır araç çubuğunu açar.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Menüye araç çubuğu düğmesi metni kopyalar. (Geçersiz kılmaları [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Düğme ile ilişkili açılan araç alır.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Aşağı açılan araç şu anda açık olup olmadığını belirler.|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Düğme ile genişletilmiş bir kenarlık görüntülenip belirler. (Geçersiz kılmaları [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Yerleştirme durumu ve belirtilen bir cihaz bağlamı için düğmenin boyutunu hesaplamak için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|İşlemek için framework tarafından çağırılır [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) ileti. (Geçersiz kılmaları `CMCToolBarButton::OnCancelMode`.)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Yeni bir araç çubuğu düğmesi eklendiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Kullanıcı fare düğmesine tıkladığında framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Kullanıcı fare düğmesini bıraktığında framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Üst araç çubuğunda WM_HELPHITTEST iletisi işlediğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Uygulamanın üst araç çubuğunda bir kısayol menü görüntülendiğinde sağlanan menü değiştirir. (Geçersiz kılmaları [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Belirtilen stillerini ve seçeneklerini kullanarak bir düğme çizmek için framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Düğme çizim için framework tarafından çağırılır **komutları** bölmesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Bu nesne bir arşivden okur veya arşive yazar. (Geçersiz kılmaları [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Bir kullanıcı düğmeye tıkladığında framework kullanan varsayılan komutu ayarlar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Aşağı açılan araç görünmeden önce bir kullanıcının fare düğmesini basılı gereken süreyi belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CMFCDropDownToolBarButton` düğmeye sağ alt köşesinde bulunan küçük ok olan bir sıradan düğmesinden farklıdır. Kullanıcının açılan araç çubuğundan düğme seçtiği sonra framework simgesini (sağ alt köşesindeki küçük ok düğmesi) en üst düzey araç çubuğu düğmesini görüntüler.  
  
 Bir açılır araç çubuğunu gerçekleştirme hakkında daha fazla bilgi için bkz. [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 `CMFCDropDownToolBarButton` Nesnesi verilebilir bir [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md) nesnesi ve bir menü düğmesi içeren bir açılır menü olarak görüntülenir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>  CMFCDropDownToolbarButton::CopyFrom  
 Başka bir araç çubuğu düğmesi özelliklerini geçerli düğmeyi kopyalar.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *src*  
 Kopyalanacak kaynak düğmesini başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu araç çubuğu düğmesi için başka bir araç çubuğu düğmesini kopyalama için bu yöntemi çağırın. *src* türünde olmalıdır `CMFCDropDownToolbarButton`.  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>  CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
 Oluşturur bir `CMFCDropDownToolbarButton` nesne.  
  
```  
CMFCDropDownToolbarButton();

 
CMFCDropDownToolbarButton(
    LPCTSTR lpszName,  
    CMFCDropDownToolBar* pToolBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszName*  
 Düğmenin varsayılan metin.  
  
 [in] *pToolBar*  
 Bir işaretçi `CMFCDropDownToolBar` kullanıcı düğmeye bastığında görüntülenen nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci oluşturucu aşırı yüklemesi açılan düğmeyi ilk düğme araç çubuğundan kopyalar, *pToolBar* belirtir.  
  
 Genellikle, en son kullanılan düğme metni açılan araç çubuğu düğmesi araç çubuğunda kullanır, *pToolBar* belirtir. Tarafından belirtilen metin kullanan *lpszName* ne zaman düğme için bir menü düğmesi dönüştürülür veya görüntülenen **komutları** sekmesinde **Özelleştir** iletişim kutusu. Hakkında daha fazla bilgi için **Özelleştir** iletişim kutusu, bkz: [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCDropDownToolbarButton` sınıfı. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>  CMFCDropDownToolbarButton::DropDownToolbar  
 Bir açılır araç çubuğunu açar.  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Aşağı açılan çerçeve ya da açılan araç çubuğu düğmesini ana pencerenin kullanmak için NULL üst pencere.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCDropDownToolbarButton::OnClick](#onclick) yöntemi, kullanıcının bastığında ve araç çubuğu düğmesini içeren açılır araç çubuğunu açmak için bu yöntemi çağırır.  
  
 Bu yöntemleri kullanarak açılır araç çubuğunu oluşturur [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) yöntemi. Üst araç çubuğunda dikey yerleştirilmişse, bu yöntem ya da uygun bağlı olarak üst araç çubuğunda sol veya sağ tarafındaki aşağı açılan araç yerleştirir. Aksi takdirde, bu yöntem, üst araç çubuğu düğmesinin altındaki açılan araç yerleştirir.  
  
 Bu yöntem, başarısız *pWnd* NULL ve açılan araç çubuğu düğmesini üst penceresine sahip değil.  
  
##  <a name="exporttomenubutton"></a>  CMFCDropDownToolbarButton::ExportToMenuButton  
 Menüye araç çubuğu düğmesi metni kopyalar.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *menuButton*  
 Hedef menü düğmesine bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu yöntemi çağırır ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) ve ardından bu düğmeye her bir araç çubuğu menü öğesi içeren bir açılır menü için hedef menü düğmesine ekler. Bu yöntem, menüye alt menü eklemez.  
  
 Bu yöntem, başarısız üst araç çubuğunda `m_pToolBar`, null veya temel sınıf uygulamasına false değerini döndürür.  
  
##  <a name="getdropdowntoolbar"></a>  CMFCDropDownToolbarButton::GetDropDownToolBar  
 Düğme ile ilişkili açılan araç alır.  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme ile ilişkili açılan araç çubuğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem döndürür `m_pToolBar` veri üyesi.  
  
##  <a name="isdropdown"></a>  CMFCDropDownToolbarButton::IsDropDown  
 Aşağı açılan araç şu anda açık olup olmadığını belirler.  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağı açılan araç şu anda açık olan olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve açılır araç çubuğunu kullanarak açılır [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) yöntemi. Kullanıcı açılan araç çubuğu'nun istemci olmayan alanda sol fare düğmesine bastığında framework açılır araç çubuğunu kapatır.  
  
##  <a name="isextrasize"></a>  CMFCDropDownToolbarButton::IsExtraSize  
 Düğme ile genişletilmiş bir kenarlık görüntülenip belirler.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç çubuğu düğmesi ile genişletilmiş bir kenarlık görüntülenebilen olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Genişletilmiş Kenarlıklar hakkında daha fazla bilgi için bkz: [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).  
  
##  <a name="m_uishowbardelay"></a>  CMFCDropDownToolbarButton::m_uiShowBarDelay  
 Aşağı açılan araç görünmeden önce bir kullanıcının fare düğmesini basılı gereken süreyi belirtir.  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Gecikme süresi, milisaniye cinsinden ölçülür. Varsayılan değer 500'dür. Bu paylaşılan veri üyesinin değerini değiştirerek, başka bir gecikme ayarlayabilirsiniz.  
  
##  <a name="oncalculatesize"></a>  CMFCDropDownToolbarButton::OnCalculateSize  
 Yerleştirme durumu ve belirtilen bir cihaz bağlamı için düğmenin boyutunu hesaplamak için framework tarafından çağırılır.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Düğme görüntüler cihaz bağlamı.  
  
 [in] *sizeDefault*  
 Düğme varsayılan boyutu.  
  
 [in] *bHorz*  
 Üst araç çubuğu yerleştirme durumu. Bu parametre, araç dikey yerleştirilmişse araç yatay olarak yerleştirildiğini veya kayan olan TRUE veya FALSE olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `SIZE` piksel cinsinden düğmenin boyutlar içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)) yatay boyutunu düğme boyutu için açılan liste okunu genişliğini ekleyerek.  
  
##  <a name="onchangeparentwnd"></a>  CMFCDropDownToolbarButton::OnChangeParentWnd  
 Yeni bir araç çubuğu düğmesi eklendiğinde framework tarafından çağırılır.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Yeni üst pencere.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu metodu geçersiz kılar ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) metin etiketi öğenizin ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) ve ayarı [ CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) ve [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) veri üyeleri false.  
  
##  <a name="onclick"></a>  CMFCDropDownToolbarButton::OnClick  
 Kullanıcı fare düğmesine tıkladığında framework tarafından çağırılır.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Üst penceresine araç çubuğu düğmesi.  
  
 [in] *bDelay*  
 İleti bir gecikmeyle işleneceğini TRUE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin click iletiyi işler olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu yöntemin genişlettiği [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), aşağı açılan araç durumunu güncelleştirerek.  
  
 Kullanıcı araç çubuğu düğmesini tıkladığında, bu yöntem tarafından belirtilen sürenin uzunluğunu beklediği Zamanlayıcı oluşturur [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) veri üyesi'i ve ardından açılır açılan araç kullanarak[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) yöntemi. Bu yöntem kullanıcı araç çubuğu düğmesini tıkladığında ikinci kez açılan araç kapatır.  
  
##  <a name="onclickup"></a>  CMFCDropDownToolbarButton::OnClickUp  
 Kullanıcı fare düğmesini bıraktığında framework tarafından çağırılır.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin click iletiyi işler olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu yöntemin genişlettiği [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), aşağı açılan araç durumunu güncelleştirerek.  
  
 Etkin değilse bu yöntem aşağı açılan araç Zamanlayıcıyı durdurur. Açık değilse açılan araç kapatır.  
  
 Aşağı açılan araç çubuğu ve açılır araç çubuğunu Zamanlayıcı hakkında daha fazla bilgi için bkz. [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
##  <a name="oncontexthelp"></a>  CMFCDropDownToolbarButton::OnContextHelp  
 Üst araç çubuğunda WM_HELPHITTEST iletisi işlediğinde framework tarafından çağırılır.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWnd*  
 Üst penceresine araç çubuğu düğmesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme yardım iletisini işler olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) çağırarak [CMFCDropDownToolbarButton::OnClick](#onclick) yöntemiyle *bDelay*FALSE olarak ayarlayın. Bu yöntem tarafından döndürülen değeri döndürür [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
 WM_HELPHITTEST ileti hakkında daha fazla bilgi için bkz. [TN028: Context-Sensitive Yardım desteği](../../mfc/tn028-context-sensitive-help-support.md).  
  
##  <a name="oncustomizemenu"></a>  CMFCDropDownToolbarButton::OnCustomizeMenu  
 Uygulamanın üst araç çubuğunda bir kısayol menü görüntülendiğinde sağlanan menü değiştirir.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMenu*  
 Özelleştirme menüsü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem, TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) aşağıdaki menü öğelerini devre dışı bırakarak:  
  
- **Kopyala düğmesi**  
  
- **Düğme görünümünü**  
  
- **Görüntü**  
  
- **Metin**  
  
- **Resim ve metin**  
  
 Özelleştirme modu framework görüntüler kısayol menüsünü değiştirmek için bu yöntemi yok sayın.  
  
##  <a name="ondraw"></a>  CMFCDropDownToolbarButton::OnDraw  
 Belirtilen stillerini ve seçeneklerini kullanarak bir düğme çizmek için framework tarafından çağırılır.  
  
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
 [in] *pDC*  
 Düğme görüntüler cihaz bağlamı.  
  
 [in] *dikdörtgen*  
 Dikdörtgen düğmesi.  
  
 [in] *pImages*  
 Araç çubuğu görüntülerini düğmesi ile ilişkili olan koleksiyonu.  
  
 [in] *bHorz*  
 Üst araç çubuğu yerleştirme durumu. Bu parametre, düğmeyi dikey yerleştirildiğinde düğmenin yatay ve yanlış yerleştirildiğinde TRUE olur.  
  
 [in] *bCustomizeMode*  
 Araç çubuğunu özelleştirme modunda olup olmadığını belirtir. Araç çubuğu özelleştirme modu ve FALSE olduğunda araç çubuğunu özelleştirme modunda olmadığında, bu parametre TRUE olur.  
  
 [in] *bHighlight*  
 Düğme vurgulanmış olup olmadığını belirtir. Bu parametre, düğme değil vurgulandığında düğmesi vurgulanmış, TRUE ve FALSE olur.  
  
 [in] *bDrawBorder*  
 Düğmenin kenarlığı görüntülemesi gerekip gerekmediğini belirtir. Bu parametre, düğmenin kenarlığı görüntülenmelidir değil, kendi kenarlık ve FALSE düğme görüntülenmelidir olduğunda TRUE olur.  
  
 [in] *bGrayDisabledButtons*  
 Devre dışı düğmeleri gölgelendirme veya devre dışı resimler koleksiyonu kullanmayı belirtir. Bu yöntem, devre dışı resimler koleksiyonu kullanmalısınız devre dışı düğmeleri gölgeli ve FALSE olması gerektiğinde, bu parametre TRUE olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç çubuğu düğmesi çizim özelleştirmek için bu yöntemi yok sayın.  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 Düğme çizim için framework tarafından çağırılır **komutları** bölmesinde **Özelleştir** iletişim kutusu.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Düğme görüntüler cihaz bağlamı.  
  
 [in] *dikdörtgen*  
 Dikdörtgen düğmesi.  
  
 [in] *bSelected*  
 Düğme seçili. Bu parametre TRUE ise düğmesi seçilir. Bu parametre FALSE ise, düğme seçili değilse.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden belirtilen bir cihaz bağlamı düğmenin genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem özelleştirme iletişim kutusu tarafından çağrılır ( **komutları** sekmesi) ne zaman düğmeye kendisini sahip çizim liste kutusunu görüntülemek için gereklidir.  
  
 Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) düğmesinin metin etiketi düğmeyi adını değiştirerek (diğer bir deyişle, değerine *lpszName* oluşturucuya geçirilen parametre).  
  
##  <a name="serialize"></a>  CMFCDropDownToolbarButton::Serialize  
 Bu nesne bir arşivden okur veya arşive yazar.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ar*  
 `CArchive` Nesne içinden veya hangi serileştirmek.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel sınıf uygulamasına bu yöntemin genişlettiği ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) kaynak kimliği üst araç çubuğunun serileştirmek tarafından. Arşiv yükleniyor ne zaman ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) sıfır olmayan bir değer döndürür), bu yöntem ayarlar `m_pToolBar` seri hale getirilmiş kaynak kimliğini içeren bir araç çubuğuna veri üyesi  
  
##  <a name="setdefaultcommand"></a>  CMFCDropDownToolbarButton::SetDefaultCommand  
 Bir kullanıcı düğmeye tıkladığında framework kullanan varsayılan komutu ayarlar.  
  
```  
void SetDefaultCommand(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmd*  
 Varsayılan komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı düğmeye tıkladığında framework yürüten varsayılan komutu belirtmek için bu yöntemi çağırın. Bir öğe tarafından belirtilen komut kimliği ile *uiCmd* üst açılan araç çubuğunda yer alması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



