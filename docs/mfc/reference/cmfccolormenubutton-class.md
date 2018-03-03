---
title: "CMFCColorMenuButton sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c6e976b1a5497e8d2814208b6b3260037458fc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton sınıfı
`CMFCColorMenuButton` Sınıfı, bir komutu veya bir Renk Seçici iletişim kutusu başlayan araç çubuğu düğmesi destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Oluşturan bir `CMFCColorMenuButton` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Etkinleştirir ve normal renk düğmeleri konumlandırılmış bir "Otomatik" düğmesini devre dışı bırakır. (Standart sistem otomatik düğmesi etiketli **otomatik**.)|  
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Belge özgü renkler sistem renkleri yerine görüntülemeyi etkinleştirir.|  
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Sağlar ve normal renk düğmeleri yerleştirilmiş bir "diğer" düğmesini devre dışı bırakır. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha renkleri**.)|  
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Bir renk Bölmesi Kapalı ayırma olanağı sağlar.|  
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengi alır.|  
|[CMFCColorMenuButton::GetColor](#getcolor)|Geçerli düğmenin rengi alır.|  
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Belirtilen komut kimliğine karşılık gelen renk alır.|  
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Üst pencere değiştiğinde çerçevesi tarafından çağrılır.|  
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Bir renk seçimi iletişim kutusunu açar.|  
|[CMFCColorMenuButton::SetColor](#setcolor)|Geçerli renk düğmesi rengini belirler.|  
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Belirtilen renk menü düğmesinin rengini belirler.|  
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Belirtilen renk için yeni bir ad ayarlar.|  
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Tarafından görüntülenen sütunların sayısı ayarlar bir `CMFCColorBar` nesnesi.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi geçerli düğme kopyalar.|  
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Bir Renk Seçici iletişim kutusu oluşturur.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Boş menüleri desteklenip desteklenmediğini gösterir.|  
|[CMFCColorMenuButton::OnDraw](#ondraw)|Görüntüyü bir düğme görüntülenecek framework tarafından çağrılır.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Önce framework tarafından çağrılan bir `CMFCColorMenuButton` nesnesi bir araç çubuğunu özelleştirme iletişim kutusu, listesinde görüntülenir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Orijinal menü komut veya araç çubuğu düğmesi ile değiştirmek için bir `CMFCColorMenuButton` nesne, oluşturma `CMFCColorMenuButton` herhangi uygun ayarlanmış nesnesi [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) stilleri ve ardından arama `ReplaceButton` yöntemi[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfı. Bir araç çubuğunu özelleştirme çağırır [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) yöntemi.  
  
 Renk Seçici iletişim kutusu işlenmesi sırasında oluşturulan [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) olay işleyicisi. Olay işleyicisinin üst çerçevesiyle bildirir bir `WM_COMMAND` ileti. `CMFCColorMenuButton` Nesne özgün menü komut veya araç çubuğu düğmesi atanan denetim kimliği gönderir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanarak bir renk menü düğmesi oluşturulacağı ve yapılandırılacağı gösterilmiştir `CMFCColorMenuButton` sınıfı. Örnekte, bir `CPalette` nesnesi ilk oluşturulur ve bir nesne oluşturmak için kullanılan `CMFCColorMenuButton` sınıfı. `CMFCColorMenuButton` Nesnesi, otomatik ve diğer düğmeleri etkinleştirme ve rengini ve sütun sayısını ayarlama ardından yapılandırılmış. Bu kod parçası olan [Word paneli örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolormenubutton.h  
  
##  <a name="cmfccolormenubutton"></a>CMFCColorMenuButton::CMFCColorMenuButton  
 Oluşturan bir `CMFCColorMenuButton` nesnesi.  
  
```  
CMFCColorMenuButton();

 
CMFCColorMenuButton(
    UINT uiCmdID,  
    LPCTSTR lpszText,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmdID`  
 Düğme komut kimliği.  
  
 [in]`lpszText`  
 Düğme metni.  
  
 [in]`pPalette`  
 Düğmenin renk paletini gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu varsayılan Oluşturucu ' dir. Nesnenin geçerli ve otomatik rengi siyah (RGB (0, 0, 0)) başlatılır.  
  
 İkinci Oluşturucu, belirtilen komut kimliğine karşılık gelen renk düğme başlatır.  
  
##  <a name="copyfrom"></a>CMFCColorMenuButton::CopyFrom  
 Bir kopyalar [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)-nesne başka bir türetilmiş.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`src`  
 Kopyalanacak kaynak düğmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilmiş kopyalama nesneleri için bu yöntemi geçersiz kılın `CMFCColorMenuButton` nesnesi.  
  
##  <a name="createpopupmenu"></a>CMFCColorMenuButton::CreatePopupMenu  
 Bir Renk Seçici iletişim kutusu oluşturur.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir Renk Seçici iletişim kutusu temsil eden nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir renk menü düğmesi bastığında bu yöntem çerçevesi tarafından çağrılır.  
  
##  <a name="enableautomaticbutton"></a>CMFCColorMenuButton::EnableAutomaticButton  
 Etkinleştirir ve normal renk düğmeleri konumlandırılmış bir "Otomatik" düğmesini devre dışı bırakır. (Standart sistem otomatik düğmesi etiketli **otomatik**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Düğme otomatik hale geldiğinde görüntülenen düğme metni belirtir.  
  
 [in]`colorAutomatic`  
 Yeni bir otomatik rengini belirtir.  
  
 [in]`bEnable`  
 Düğme otomatik olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik düğmesine geçerli varsayılan renk uygular.  
  
##  <a name="enabledocumentcolors"></a>CMFCColorMenuButton::EnableDocumentColors  
 Belge özgü renkler sistem renkleri yerine görüntülemeyi etkinleştirir.  
  
```  
void EnableDocumentColors(
    LPCTSTR lpszLabel,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Düğme metni belirtir.  
  
 [in]`bEnable`  
 `TRUE`Belge özgü renkler görüntülenecek veya `FALSE` sistem renkleri görüntülemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir renk menü düğmesini tıklattığında geçerli belge renkleri veya sistem palet renklerini görüntülemek için bu yöntemi kullanın.  
  
##  <a name="enableotherbutton"></a>CMFCColorMenuButton::EnableOtherButton  
 Sağlar ve normal renk düğmeleri yerleştirilmiş bir "diğer" düğmesini devre dışı bırakır. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha renkleri**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Düğme metni belirtir.  
  
 [in]`bAltColorDlg`  
 Belirtin `TRUE` görüntülemek için `CMFCColorDialog` iletişim kutusu, veya `FALSE` standart sistem renk iletişim kutusu görüntülemek için.  
  
 [in]`bEnable`  
 Belirtin `TRUE` "diğer" düğmesini; görüntülemek için Aksi halde, `FALSE`. Varsayılan, `TRUE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enabletearoff"></a>CMFCColorMenuButton::EnableTearOff  
 Bir renk Bölmesi Kapalı ayırma olanağı sağlar.  
  
```  
void EnableTearOff(
    UINT uiID,  
    int nVertDockColumns=-1,  
    int nHorzDockRows=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiID`  
 Etiketleri bölmesinde Kimliğini belirtir.  
  
 [in]`nVertDockColumns`  
 Etiketleri durumundayken dikey yerleşik renk bölmesinde sütun sayısını belirtir.  
  
 [in]`nHorzDockRows`  
 Etiketleri durumundayken yatay yerleşik renk bölmesinde satır sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman POP renk bölmesi "etiketleri" özelliğini etkinleştirmek için bu yöntemi çağırın `CMFCColorMenuButton` düğmesine basıldığında.  
  
##  <a name="getautomaticcolor"></a>CMFCColorMenuButton::GetAutomaticColor  
 Geçerli otomatik rengi alır.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli otomatik rengi temsil eden bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirlenen otomatik renk elde etmek için bu yöntemi çağırın [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).  
  
##  <a name="getcolor"></a>CMFCColorMenuButton::GetColor  
 Geçerli düğmenin rengi alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme rengi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcolorbycmdid"></a>CMFCColorMenuButton::GetColorByCmdID  
 Belirtilen komut kimliğine karşılık gelen renk alır.  
  
```  
static COLORREF GetColorByCmdID(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmdID`  
 Komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen komut kimliğine karşılık gelen renk  
  
### <a name="remarks"></a>Açıklamalar  
 Birçok renk düğmesi bir uygulamanız varsa, bu yöntemi kullanın. Kullanıcı bir renk düğmesine tıkladığında, düğme komut Kimliğini gönderir bir `WM_COMMAND` üst ileti. `GetColorByCmdID` Yöntemi karşılık gelen renk almak için komut Kimliğini kullanır.  
  
##  <a name="isemptymenuallowed"></a>CMFCColorMenuButton::IsEmptyMenuAllowed  
 Boş menüleri desteklenip desteklenmediğini gösterir.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Boş ise sıfır olmayan menüleri izin verilir; Aksi durumda, sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Boş menüleri varsayılan olarak desteklenir. Türetilmiş sınıf içinde bu davranışı değiştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onchangeparentwnd"></a>CMFCColorMenuButton::OnChangeParentWnd  
 Üst pencere değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndParent`  
 Yeni üst pencere için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondraw"></a>CMFCColorMenuButton::OnDraw  
 Görüntüyü bir düğme görüntülenecek framework tarafından çağrılır.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz=TRUE,  
    BOOL bCustomizeMode=FALSE,  
    BOOL bHighlight=FALSE,  
    BOOL bDrawBorder=TRUE,  
    BOOL bGrayDisabledButtons=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in]`rect`  
 Alan çizilmesi bounds dikdörtgen.  
  
 [in]`pImages`  
 Araç çubuğu görüntülerinin noktaları bir listesi.  
  
 [in]`bHorz`  
 `TRUE`araç çubuğu yatay takılı durumda olduğunu belirtmek için; Aksi takdirde `FALSE`. Varsayılan, `TRUE` değeridir.  
  
 [in]`bCustomizeMode`  
 `TRUE`Uygulama özelleştirme modunda olduğunu belirtmek için; Aksi takdirde `FALSE`. Varsayılan, `FALSE` değeridir.  
  
 [in]`bHighlight`  
 `TRUE`düğme vurgulanır belirtmek için; Aksi takdirde `FALSE`. Varsayılan, `FALSE` değeridir.  
  
 [in]`bDrawBorder`  
 `TRUE`düğmenin kenarlık görüntüleneceğini belirtmek için; Aksi takdirde `FALSE`. Varsayılan, `TRUE` değeridir.  
  
 [in]`bGrayDisabledButtons`  
 `TRUE`devre dışı belirtmek için düğmeler (soluk) kullanıma; gri gösterilir Aksi takdirde `FALSE`. Varsayılan, `TRUE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawoncustomizelist"></a>CMFCColorMenuButton::OnDrawOnCustomizeList  
 Önce framework tarafından çağrılan bir `CMFCColorMenuButton` nesnesi bir araç çubuğunu özelleştirme iletişim kutusu, listesinde görüntülenir.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in]`rect`  
 Çizilecek düğmesi bounds dikdörtgen.  
  
 [in]`bSelected`  
 `TRUE`düğme seçili durumda olduğunu belirtir. Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmenin genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem çerçevesi tarafından çağrılır olduğunda bir `CMFCColorMenuButton` nesne araç çubuğunu özelleştirme işlemi sırasında liste kutusunda görüntülenir.  
  
##  <a name="opencolordialog"></a>CMFCColorMenuButton::OpenColorDialog  
 Bir renk seçimi iletişim kutusunu açar.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`colorDefault`  
 Renk iletişim kutusunda seçili olan varsayılan rengi.  
  
 [out]`colorRes`  
 Renk iletişim kutusundan kullanıcının seçtiği rengi döndürür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı yeni bir renk seçerse sıfır olmayan; Aksi durumda, sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü düğmesine tıklandığında, bir renk iletişim kutusu açmak için bu yöntemi çağırın. Dönüş değeri sıfır değilse, kullanıcının seçtiği rengi depolanan `colorRes` parametresi. Kullanım [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) standart renk iletişim kutusu arasında geçiş yapmak için yöntem ve [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu.  
  
##  <a name="setcolor"></a>CMFCColorMenuButton::SetColor  
 Geçerli renk düğmesi rengini belirler.  
  
```  
virtual void SetColor(
    COLORREF clr,  
    BOOL bNotify=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`clr`  
 RGB renk değeri.  
  
 [in]`bNotify`  
 `TRUE`uygulanacak `clr` parametresi renk herhangi bir ilişkili menü düğmesi veya araç çubuğu düğmesi; Aksi halde, `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli renk düğmesi rengini değiştirmek için bu yöntemi çağırın. Varsa `bNotify` parametre sıfır olmayan ve tüm ilişkili açılan menü veya araç çubuğunda karşılık gelen bir düğme rengi tarafından belirtilen renk değiştirilir `clr` parametresi.  
  
##  <a name="setcolorbycmdid"></a>CMFCColorMenuButton::SetColorByCmdID  
 Belirtilen renk menü düğmesinin rengini belirler.  
  
```  
static void SetColorByCmdID(
    UINT uiCmdID,  
    COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmdID`  
 Bir renk menü düğmesi kaynak kimliği.  
  
 [in]`color`  
 RGB renk değeri.  
  
##  <a name="setcolorname"></a>CMFCColorMenuButton::SetColorName  
 Belirtilen renk için yeni bir ad ayarlar.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 Adı değiştirir renk RGB değeri.  
  
 [in]`strName`  
 Renk yeni adı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setcolumnsnumber"></a>CMFCColorMenuButton::SetColumnsNumber  
 Bir renk seçimi denetiminde görüntülenecek sütun sayısını ayarlar ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) nesnesi).  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nColumns`  
 Görüntülenecek sütun sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton Sınıfı](../../mfc/reference/cmfccolorbutton-class.md)
