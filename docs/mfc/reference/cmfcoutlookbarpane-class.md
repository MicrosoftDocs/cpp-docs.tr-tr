---
title: CMFCOutlookBarPane sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe72b43d8930e77bea274e20e5f150cc93617c20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374090"
---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane sınıfı
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Bir denetim türetilmiş [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) bir Outlook çubuğuna eklenebilir ( [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)). Outlook Çubuğu bölmesinde bir sütun büyük düğmelerini içerir. Bölmesinde büyükse kullanıcı düğmeleri liste yukarı ve aşağı kaydırma yapabilir. Kullanıcı bir Outlook Çubuğu Outlook Çubuğu bölmesinden ayırır, float veya ana çerçeve penceresinde yerleştirme yükleyebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Varsayılan Oluşturucu.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Bir düğme Outlook Çubuğu bölmesine ekler.|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Başka bir bölme veya çerçeveye penceresine bölmesinde yerleştirilmiş olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|  
|`CMFCOutlookBarPane::CanBeRestored`|Sistemi bir araç çubuğu özgün durumuna geri özelleştirme sonrasında geri yükleyebilirsiniz olup olmadığını belirler. (Geçersiz kılmaları [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Outlook Çubuğu bölmesinde görüntüleri tarafından kullanılan kaynakları serbest bırakır.|  
|[CMFCOutlookBarPane::Create](#create)|Outlook Çubuğu bölmesi oluşturur.|  
|`CMFCOutlookBarPane::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCOutlookBarPane::Dock`|Outlook Çubuğu bölmesi sabitlemek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları `CPane::Dock`.)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Outlook Çubuğu bölmesinde kaydırma oklarının sayfası tarafından ya da düğmesi düğmelerin listesini ilerletmek olup olmadığını belirtir.|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Outlook Çubuğu bölmesinin normal (seçili olmayan) metin rengi döndürür.|  
|`CMFCOutlookBarPane::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Outlook Çubuğu bölmesi yüklenen bir arka plan görüntüsü olup olmadığını belirler.|  
|`CMFCOutlookBarPane::IsChangeState`|Bir kayan bölmesi yuvalanmış olup olmadığını belirler. (Geçersiz kılmaları `CPane::IsChangeState`.)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Düğme kenarlığı bir düğmesi vurgulanmış ve arka plan resmi görüntülendiğinde gölgeli olup olmadığını belirler.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Kayana bölme hakkında olduğunda çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Belirtilen komut kimliğe sahip düğmesini kaldırır|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Bir araç çubuğunun özgün durumunu geri yükler. (Geçersiz kılmaları [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Arka plan rengini belirler.|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Arka plan resmi ayarlar.|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Outlook Çubuğu bölmesi düğmelerinin özgün kümesine sıfırlar.|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Outlook Çubuğu bölmesi düğmeleri geçici kullanılan doldurma piksel sayısını ayarlar.|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Outlook Çubuğu Bölmesi'nde normal ve vurgulanan metin rengini belirler.|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Outlook Çubuğu bölmesi saydam rengini belirler.|  
|`CMFCOutlookBarPane::SmartUpdate`|Outlook Çubuğu güncelleştirmek için dahili olarak kullanılır. (Geçersiz kılmaları `CMFCToolBar::SmartUpdate`.)|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Hangi kısayol menüsü öğelerini özelleştirme modunda görüntüleneceğini belirtir.|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Tüm düğmeleri Outlook Çubuğu bölmesinden kaldırır. (Geçersiz kılmaları [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Outlook Çubuğu uygulama hakkında daha fazla bilgi için bkz: [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 OutlookDemo örnek proje Outlook çubuğu örneği için bkz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemleri kullanmayı gösterilmiştir `CMFCOutlookBarPane` sınıfı. Örneğin, bir Outlook Çubuğu bölmesi oluşturmak, sayfa kaydırma modunu etkinleştirmek, yerleştirme etkinleştirmek ve Outlook çubuğu arka plan rengini ayarlama gösterilmektedir. Bu kod parçacığını parçası olan [Outlook çoklu görünümler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxoutlookbarpane.h  
  
##  <a name="addbutton"></a>  CMFCOutlookBarPane::AddButton  
 Bir düğme Outlook Çubuğu bölmesine ekler.  
  
```  
BOOL AddButton(
    UINT uiImage,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    UINT uiImage,  
    UINT uiLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    LPCTSTR szBmpFileName,  
    LPCTSTR szLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HBITMAP hBmp,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HICON hIcon,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiImage`  
 Bir bit eşlem kaynak tanımlayıcısını belirtir.  
  
 [in] `lpszLabel`  
 Düğmenin metni belirtir.  
  
 [in] `iIdCommand`  
 Düğme denetiminin kimliğini belirtir.  
  
 [in] `iInsertAt`  
 Ekle düğmesi için outlook çubuğunun sayfa üzerinde sıfır tabanlı dizini belirtir.  
  
 [in] `uiLabel`  
 Bir dize kaynak kimliği  
  
 [in] `szBmpFileName`  
 Yüklemek için disk görüntü dosyasının adını belirtir.  
  
 [in] `szLabel`  
 Düğmenin metni belirtir.  
  
 [in] `hBmp`  
 Düğmenin bit eşlem için bir tanıtıcı.  
  
 [in] `hIcon`  
 Bir düğme simgesi için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bir düğme başarıyla eklendi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir Outlook çubuğunun sayfasına yeni bir düğme eklemek için bu yöntemi kullanın. Düğmenin resim uygulama kaynaklarını veya bir disk dosyası yüklenebilir.  
  
 Sayfa kimliği ile belirtilen `uiPageID` -1 ' dir düğmesine ilk sayfasına eklenir.  
  
 Dizin ile belirtilen `iInsertAt` -1 ' dir düğme sayfa sonuna eklenir.  
  
##  <a name="canbeattached"></a>  CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="clearall"></a>  CMFCOutlookBarPane::ClearAll  
 Outlook Çubuğu bölmesi görüntülerinde tarafından kullanılan kaynakları serbest bırakır.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem doğrudan çağıran [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), Outlook Çubuğu bölmesinin kullandığı görüntülerinde çağrılır.  
  
##  <a name="create"></a>  CMFCOutlookBarPane::Create  
 Outlook Çubuğu bölmesi oluşturur.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT uiID=(UINT)-1,  
    DWORD dwControlBarStyle=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pParentWnd`  
 Outlook Çubuğu bölmesi denetiminin üst pencere belirtir. Olmamalıdır `NULL`.  
  
 [in] `dwStyle`  
 Pencere stili.  Pencere stilleri listesi için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `uiID`  
 Denetim kimliği. Etkinleştirmek için benzersiz olması gerekir denetimin durumunu kaydetme.  
  
 [in] `dwControlBarStyle`  
 Outlook Çubuğu'ndan ayrılmış olduğunda, Outlook Çubuğu bölmesi denetimi davranışını tanımlayan özel stiller belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak için bir `CMFCOutlookBarPane` nesne, ilk Oluşturucusu arayın ve sonra çağrısı `Create`, Outlook bölmesinde denetim çubuğu oluşturur ve ekler `CMFCOutlookBarPane` nesnesi.  
  
 Hakkında daha fazla bilgi için `dwControlBarStyle` bkz [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
##  <a name="enablecontextmenuitems"></a>  CMFCOutlookBarPane::EnableContextMenuItems  
 Hangi kısayol menüsü öğelerini özelleştirme modunda görüntüleneceğini belirtir.  
  
```  
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,  
    CMenu* pPopup);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pButton`  
 Bir kullanıcının bir araç çubuğu düğmesi için bir işaretçi.  
  
 [in] `pPopup`  
 Kısayol menüsünün gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` kısayol menüsünün olmalıdır, aksi görüntülenen `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Özelleştirme modunda framework görüntüler framework standart kısayol menüsünün değiştirmek için bu yöntemi geçersiz kılın.  
  
 Varsayılan uygulama özelleştirme modu denetler ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) ve onu ayarlanmışsa `TRUE`, dışındaki tüm kısayol menü öğelerini devre dışı bırakır **silmek**. Daha sonra giriş parametreleri yalnızca geçirir `CMFCToolBar::EnableContextMenuItems`.  
  
> [!NOTE]
> *Bağlam menüsü* kısayol menüsü eşanlamlısı olduğu.  
  
##  <a name="enablepagescrollmode"></a>  CMFCOutlookBarPane::EnablePageScrollMode  
 Outlook Çubuğu bölmesinde kaydırma oklarının düğmelerin sayfa tarafından ya da düğmesini tarafından düğmesi listesini ilerletmek olup olmadığını belirtir.  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bPageScroll`  
 Varsa `TRUE`, sayfa kaydırma modunu etkinleştirin. Varsa `FALSE`, sayfa kaydırma modu devre dışı bırakın.  
  
##  <a name="getregularcolor"></a>  CMFCOutlookBarPane::GetRegularColor  
 Normal döndürür (diğer bir deyişle, seçili olmayan) Outlook Çubuğu bölmesinin metin rengi.  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 RGB renk değeri olarak geçerli metin rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCOutlookBarPane::SetTextColor](#settextcolor) Outlook Çubuğu geçerli (normal ve seçilen) metin rengini ayarlamak için. Varsayılan metin rengi çağırarak elde edebileceğiniz [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) ile işlev `COLOR_WINDOW` dizini.  
  
##  <a name="isbackgroundtexture"></a>  CMFCOutlookBarPane::IsBackgroundTexture  
 Outlook Çubuğu bölmesi yüklenen bir arka plan görüntüsü olup olmadığını belirler.  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` görüntülemek için arka plan resmini ise; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak bir arka plan görüntüsü ekleyebilirsiniz [CMFCOutlookBarPane::SetBackImage](#setbackimage) işlevi.  
  
 Arka plan görüntüsü varsa, arka plan kullanılarak belirtilen renkle boyanır [CMFCOutlookBarPane::SetBackColor](#setbackcolor).  
  
##  <a name="isdrawshadedhighlight"></a>  CMFCOutlookBarPane::IsDrawShadedHighlight  
 Düğme kenarlığı bir düğmesi vurgulanmış ve arka plan resmi görüntülendiğinde gölgeli olup olmadığını belirler.  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` düğmenin Kenarlıklar gölgeli Aksi takdirde `FALSE`.  
  
##  <a name="removeallbuttons"></a>  CMFCOutlookBarPane::RemoveAllButtons  
 Tüm düğmeleri Outlook Çubuğu bölmesinden kaldırır.  
  
```  
virtual void RemoveAllButtons();
```  
  
##  <a name="removebutton"></a>  CMFCOutlookBarPane::RemoveButton  
 Belirtilen komut kimliğe sahip düğmesini kaldırır  
  
```  
BOOL RemoveButton(UINT iIdCommand);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iIdCommand`  
 Kaldırmak için bir düğmeye komut Kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Düğme başarıyla kaldırıldıysa; `FALSE` belirtilen komut kimliği geçerli değilse.  
  
##  <a name="setbackcolor"></a>  CMFCOutlookBarPane::SetBackColor  
 Outlook çubuğu arka plan rengini belirler.  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `color`  
 Yeni arka plan rengini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Outlook Çubuğu geçerli arka plan rengini ayarlamak için bu işlevini çağırın. Arka plan rengi, yalnızca hiçbir arka plan görüntüsü olduğunda kullanılır.  
  
##  <a name="setbackimage"></a>  CMFCOutlookBarPane::SetBackImage  
 Arka plan resmi ayarlar.  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiImageID`  
 Resim kaynak kimliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Outlook ayarlamak için bu yöntemi çağırın çubuğunun arka plan görüntüsü. Arka plan görüntüleri listesi yönetilen katıştırılmış tarafından [CMFCToolBarImages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesi.  
  
##  <a name="setdefaultstate"></a>  CMFCOutlookBarPane::SetDefaultState  
 Outlook Çubuğu bölmesi düğmelerinin özgün kümesine sıfırlar.  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, özgün kümesine Outlook çubuğu düğmelerini geri yükler. Bu yöntem benzer `CMFCOutlookBarPane::RestoreOriginalstate`, Outlook Çubuğu bölmesinin yeniden düzenlenen tetiklemez dışında.  
  
##  <a name="setextraspace"></a>  CMFCOutlookBarPane::SetExtraSpace  
 Outlook Çubuğu bölmesi düğmeleri geçici kullanılan doldurma piksel sayısını ayarlar.  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="settextcolor"></a>  CMFCOutlookBarPane::SetTextColor  
 Outlook Çubuğu Bölmesi'nde normal ve vurgulanan metin rengini belirler.  
  
```  
void SetTextColor(
    COLORREF clrRegText,  
    COLORREF clrSelText=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `clrRegText`  
 Seçili olmayan metin yeni rengini belirtir.  
  
 [in] `clrSelText`  
 Seçili metni yeni rengini belirtir.  
  
##  <a name="settransparentcolor"></a>  CMFCOutlookBarPane::SetTransparentColor  
 Outlook Çubuğu bölmesi saydam rengini belirler.  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 Yeni saydam rengini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Saydam rengi saydam görüntüleri göstermek için gereklidir. Bu rengin görüntüdeki herhangi bir tekrarlamasını yerine arka plan rengiyle boyanır.  Hiç arka plan ve ön plan görüntülerini karışım yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl Sınıfı](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
