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
ms.openlocfilehash: fbced65aa76206d040ff1c13267fe9b7d3c69eca
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122793"
---
# <a name="csplitbutton-class"></a>CSplitButton sınıfı
`CSplitButton` Sınıfı, Bölünmüş düğme denetimi temsil eder. Kullanıcı düğmesi ana bölümü tıkladığında ve bir kullanıcı düğmesinin aşağı açılan okunu tıkladığında açılır menü görüntüler varsayılan davranışı Bölünmüş düğme denetimi gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|Oluşturan bir `CSplitButton` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|Bölünmüş düğme denetimi ile belirtilen stilleri oluşturur ve geçerli iliştirir `CSplitButton` nesnesi.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Kullanıcı aşağı açılan okunu geçerli Bölünmüş düğme denetimi tıklattığında görüntülenen açılır menü ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Sistem bir kullanıcı aşağı açılan okunu geçerli Bölünmüş düğme denetiminin tıkladığında göndereceğini BCN_DROPDOWN bildirim işler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSplitButton` Sınıfı türetilir [CButton](../../mfc/reference/cbutton-class.md) sınıfı. Bölünmüş düğme denetim stilini BS_SPLITBUTTON olan bir düğme denetimdir. Kullanıcı aşağı açılan okunu tıklattığında özel menü görüntüler. Daha fazla bilgi için bkz: BS_SPLITBUTTON ve BS_DEFSPLITBUTTON stillerde [düğme stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 Aşağıdaki şekilde bir çağrı ve (1) Bölünmüş düğme denetimi içeren bir iletişim kutusu gösterilmektedir. (2) aşağı açılan okunu zaten tıklamıştır ve (3) alt görüntülenir.  
  
 ![Ve çağrı cihazı denetimiyle denetimi ile iletişim. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
 Bu sınıf desteklenir [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] ve daha sonra.  
  
 Bu sınıf için ek gereksinimler açıklanmıştır [yapı gereksinimleri için Windows Vista ortak denetimleri](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="create"></a>  CSplitButton::Create  
 Bölünmüş düğme denetimi ile belirtilen stilleri oluşturur ve geçerli iliştirir `CSplitButton` nesnesi.  
  
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
|[in] *dwStyle*|Bitsel bir birleşimi (veya) denetime uygulanacak stilleri. Daha fazla bilgi için bkz: [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
|[in] *rect*|Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) denetimin boyutunu ve konumunu içeren yapısı.|  
|[in] *pParentWnd*|Null olmayan gösteren bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst pencere nesnesi.|  
|[in] *nID*|Denetimin kimliği.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton  
 Oluşturan bir `CSplitButton` nesnesi. Kullanıcı aşağı açılan okunu Bölünmüş düğme denetimi tıklattığında görüntülenen bir alt Oluşturucusu ait parametreleri belirtin.  
  
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
|[in] *nMenuId*|Menü çubuğu kaynak kimliği.|  
|[in] *nSubMenuId*|Bir alt kaynak kimliği.|  
|[in] *pMenu*|Bir işaretçi bir [CMenu](../../mfc/reference/cmenu-class.md) belirten bir alt nesne. `CSplitButton` Nesne siler `CMenu` nesne ve onun ilişkili HMENU zaman `CSplitButton` nesne kapsam dışında gider.|  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CSplitButton::Create](#create) Bölünmüş düğme denetimi oluşturmak ve ona eklemek için yöntem `CSplitButton` nesnesi.  
  
##  <a name="ondropdown"></a>  CSplitButton::OnDropDown  
 Sistem bir kullanıcı aşağı açılan okunu geçerli Bölünmüş düğme denetiminin tıkladığında göndereceğini BCN_DROPDOWN bildirim işler.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *pNMHDR*|İşaretçi bir [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) hakkında bilgi içeren yapısı [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) bildirim.|  
|[out] *pResult*|(Kullanılmaz; herhangi bir değer döndürdü.) Değerini döndürmek [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) bildirim.|  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı aşağı açılan okunu Bölünmüş düğme denetimi tıklattığında sistem BCN_DROPDOWN bildirim gönderir. ileti, hangi `OnDropDown` yöntemi işler. Ancak, `CSplitButton` nesne Bölünmüş düğme denetimi içeren denetimi için BCN_DROPDOWN bildirim iletme değil. Sonuç olarak, içeren denetimi, özel bir eylem bildirime yanıt destekleyemez.  
  
 İçeren denetimi destekler özel bir eylemi uygulamak için kullandığınız bir [CButton](../../mfc/reference/cbutton-class.md) yerine BS_SPLITBUTTON stili nesnesiyle bir `CSplitButton` nesnesi. BCN_DROPDOWN bildirim için bir işleyici uygulamak `CButton` nesnesi. Daha fazla bilgi için bkz: [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 Bölünmüş düğme destekler kendisini kontrol özel bir eylemi uygulamak için kullandığınız [ileti yansıma](../../mfc/tn062-message-reflection-for-windows-controls.md). Kendi sınıfından türetilen `CSplitButton` sınıfı ve bu, örneğin, CMySplitButton olarak adlandırın. Daha sonra aşağıdaki ileti eşlemesi BCN_DROPDOWN bildirimini işlemek için uygulamanıza ekleyin:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu  
 Kullanıcı aşağı açılan okunu geçerli Bölünmüş düğme denetimi tıklattığında görüntülenen açılır menü ayarlar.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] *nMenuId*|Menü çubuğu kaynak kimliği.|  
|[in] *nSubMenuId*|Bir alt kaynak kimliği.|  
|[in] *pMenu*|İşaretçi bir [CMenu](../../mfc/reference/cmenu-class.md) belirten bir alt nesne. `CSplitButton` Nesne siler `CMenu` nesne ve onun ilişkili HMENU zaman `CSplitButton` nesne kapsam dışında gider.|  
  
### <a name="remarks"></a>Açıklamalar  
 *NMenuId* parametre yatay menü çubuğu öğeleri listesini bir menü çubuğu tanımlar. *NSubMenuId* her menü çubuğu öğesiyle ilişkili menü öğelerinin açılan listesi olan bir alt tanımlayan sıfır tabanlı bir dizin numarasını parametresidir. Örneğin, bir genel uygulama "Düzenle" ve "Help." "Dosyası," menü çubuğu öğeleri içeren bir menüsünde vardır Menü öğelerini içeren bir alt "Dosyası" menü çubuğu öğesi olan "Açın," "Kapat" ve "Çıkın." Bölünmüş düğme denetim aşağı açılan okunu tıklandığında, belirtilen alt menü çubuğu denetim görüntüler.  
  
 Aşağıdaki şekilde bir çağrı ve (1) Bölünmüş düğme denetimi içeren bir iletişim kutusu gösterilmektedir. (2) aşağı açılan okunu zaten tıklamıştır ve (3) alt görüntülenir.  
  
 ![Ve çağrı cihazı denetimiyle denetimi ile iletişim. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği işlemindeki ilk deyim gösteren [CSplitButton::SetDropDownMenu](#setdropdownmenu) yöntemi. Menü ile Visual Studio kaynak otomatik olarak IDR_MENU1 menü çubuğu kimliği adlı Düzenleyicisi oluşturduk. *NSubMenuId* sıfır olan parametre, menü çubuğundaki yalnızca menüye başvuruyor.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSplitButton sınıfı](../../mfc/reference/csplitbutton-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CButton Sınıfı](../../mfc/reference/cbutton-class.md)
