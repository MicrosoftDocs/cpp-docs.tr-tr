---
title: CSplitButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
dev_langs:
- C++
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42f7eb1864c2839ecce88785dfaef8ab62d0b423
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705282"
---
# <a name="csplitbutton-class"></a>CSplitButton sınıfı
`CSplitButton` Sınıfı, Bölünmüş düğme denetimini temsil eder. Bir kullanıcı düğmenin ana bölümünü tıkladığında ve kullanıcı düğmenin aşağı açılan oka tıkladığında bir açılan menü görüntüler varsayılan davranışı Bölünmüş düğme denetimi gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|Oluşturur bir `CSplitButton` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|Belirtilen stilleriyle bir Bölünmüş düğme denetimi oluşturur ve bunu geçerli ekler `CSplitButton` nesne.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Kullanıcı geçerli Bölünmüş düğme denetimi aşağı açılan okunu tıkladığında görüntülenen açılan menüden ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Sistem kullanıcı geçerli Bölünmüş düğme denetimi aşağı açılan okunu tıkladığında gönderdiği BCN_DROPDOWN bildirimleri işler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSplitButton` Sınıfı türetilen [CButton](../../mfc/reference/cbutton-class.md) sınıfı. Bölünmüş düğme denetimi BS_SPLITBUTTON stilini olan bir düğme denetimi ' dir. Kullanıcı aşağı açılan okunu tıkladığında bir özel menü görüntüler. Daha fazla bilgi için bkz: BS_SPLITBUTTON ve BS_DEFSPLITBUTTON stilleri [düğme stilleri](/windows/desktop/Controls/button-styles).  
  
 Aşağıdaki şekil, çağrı cihazı denetimi ve (1) Bölünmüş düğme denetimini içeren bir iletişim kutusu gösterir. (2) açılan liste okunu zaten tıklanan ve (3) alt görüntülenir.  
  
 ![Splitbutton ve çağrı cihazı denetimi ile iletişim. ](../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
 Bu sınıf, Windows Vista ve sonraki sürümlerde desteklenir.  
  
 Bu sınıf için ek gereksinimler açıklanmıştır [yapı gereksinimleri için Windows Vista ortak denetimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="create"></a>  CSplitButton::Create  
 Belirtilen stilleriyle bir Bölünmüş düğme denetimi oluşturur ve bunu geçerli ekler `CSplitButton` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*dwStyle*|[in] Bitsel bir birleşimi (veya) denetime uygulanacak stilleri. Daha fazla bilgi için [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
|*Rect*|[in] Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) denetimin boyutunu ve konumunu içeren yapısı.|  
|*pParentWnd*|[in] Null olmayan bir işaretçiye bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst penceresine olan nesne.|  
|*nID*|[in] Denetimin kimliği.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton  
 Oluşturur bir `CSplitButton` nesne. Kullanıcı Bölünmüş düğme denetimi aşağı açılan okunu tıkladığında görüntülenen bir alt oluşturucunun parametreleri belirtin.  
  
```  
CSplitButton();

 
CSplitButton(
    UINT nMenuId,   
    UINT nSubMenuId)  
CSplitButton(CMenu* pMenu)  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*nMenuId*|[in] Menü çubuğu kaynak kimliği.|  
|*nSubMenuId*|[in] Bir alt kaynak kimliği.|  
|*pMenu*|[in] Bir işaretçi bir [CMenu](../../mfc/reference/cmenu-class.md) belirten bir alt nesne. `CSplitButton` Nesne silme `CMenu` nesne ve onun ilişkili HMENU olduğunda `CSplitButton` nesne kapsam dışına gider.|  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CSplitButton::Create](#create) ekleyebilir ve Bölünmüş düğme denetimi oluşturmak için yöntem `CSplitButton` nesne.  
  
##  <a name="ondropdown"></a>  CSplitButton::OnDropDown  
 Sistem kullanıcı geçerli Bölünmüş düğme denetimi aşağı açılan okunu tıkladığında gönderdiği BCN_DROPDOWN bildirimleri işler.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*pNMHDR*|[in] İşaretçi bir [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) hakkında bilgi içeren yapısı [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown) bildirim.|  
|*pResult*|[out] (Kullanılmaz; hiçbir değer döndürülmez.) Dönüş değeri [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown) bildirim.|  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Bölünmüş düğme denetimini bulunan aşağı açılan oka tıkladığında, sistemi BCN_DROPDOWN bildirim gönderir. ileti, hangi `OnDropDown` yöntemi işler. Ancak, `CSplitButton` nesne, Bölünmüş düğme denetimi içeren denetimi BCN_DROPDOWN bildirim iletme değil. Sonuç olarak, denetimi içeren özel bir eylem bildirime yanıt destekleyemez.  
  
 İçeren denetim destekleyen özel bir eylem uygulamak için kullanmak bir [CButton](../../mfc/reference/cbutton-class.md) yerine BS_SPLITBUTTON stilini nesneyle bir `CSplitButton` nesne. Ardından BCN_DROPDOWN bildiriminde için bir işleyici uygulamak `CButton` nesne. Daha fazla bilgi için [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 Bölünmüş düğme kendisini destekleyen denetim özel bir eylemi uygulamak için kullanma [ileti yansıma](../../mfc/tn062-message-reflection-for-windows-controls.md). Kendi sınıfından türetilir `CSplitButton` sınıfı ve, örneğin, CMySplitButton adlandırın. Ardından aşağıdaki ileti eşlemesi BCN_DROPDOWN bildirimini işlemek için uygulamanıza ekleyin:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu  
 Kullanıcı geçerli Bölünmüş düğme denetimi aşağı açılan okunu tıkladığında görüntülenen açılan menüden ayarlar.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*nMenuId*|[in] Menü çubuğu kaynak kimliği.|  
|*nSubMenuId*|[in] Bir alt kaynak kimliği.|  
|*pMenu*|[in] İşaretçi bir [CMenu](../../mfc/reference/cmenu-class.md) belirten bir alt nesne. `CSplitButton` Nesne silme `CMenu` nesne ve onun ilişkili HMENU olduğunda `CSplitButton` nesne kapsam dışına gider.|  
  
### <a name="remarks"></a>Açıklamalar  
 *NMenuId* menü çubuğu öğelerini yatay bir listesi olan bir menü çubuğu parametresi tanımlar. *NSubMenuId* parametresi, her bir menü çubuğu öğesi ile ilişkili menü öğelerinin açılan listenin bir alt menüye tanımlayan bir sıfır tabanlı dizin numarası. Örneğin, "Düzenle" ve "Help", "File" menü çubuğu öğelerini içeren bir menü tipik bir uygulaması vardır "Dosya" menü çubuğu öğesini menü öğeleri içeren bir alt menüye sahip "Açın," "Kapat" ve "Çıkın." Bölünmüş düğme denetimi aşağı açılan oka tıklandığında denetimin belirtilen alt menü çubuğu görüntüler.  
  
 Aşağıdaki şekil, çağrı cihazı denetimi ve (1) Bölünmüş düğme denetimini içeren bir iletişim kutusu gösterir. (2) açılan liste okunu zaten tıklanan ve (3) alt görüntülenir.  
  
 ![Splitbutton ve çağrı cihazı denetimi ile iletişim. ](../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde ilk deyimde gösterir [CSplitButton::SetDropDownMenu](#setdropdownmenu) yöntemi. Menü ile Visual Studio kaynak IDR_MENU1 menü çubuğu kimliği otomatik olarak adlandırılan Düzenleyicisi oluşturduk. *NSubMenuId* sıfır olan parametre menü çubuğu için yalnızca alt ifade eder.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSplitButton sınıfı](../../mfc/reference/csplitbutton-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CButton Sınıfı](../../mfc/reference/cbutton-class.md)
