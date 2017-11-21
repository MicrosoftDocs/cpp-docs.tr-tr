---
title: "Ccmduı sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
dev_langs: C++
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 657483c85c8b2f03d4a78e76cdc28a5dfff496e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccmdui-class"></a>Ccmduı sınıfı
İçinde yalnızca kullanılan bir `ON_UPDATE_COMMAND_UI` işleyicisinde bir `CCmdTarget`-türetilmiş sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|Geçerli ileti işleyicileri zincirine aşağı yönlendirme devam etmek için komut yönlendirme mekanizması söyler.|  
|[CCmdUI::Enable](#enable)|Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.|  
|[CCmdUI::SetCheck](#setcheck)|Bu komut için kullanıcı arabirimi öğesi onay durumunu ayarlar.|  
|[CCmdUI::SetRadio](#setradio)|Gibi `SetCheck` üye işlevi, ancak radyo grupları üzerinde çalışır.|  
|[CCmdUI::SetText](#settext)|Bu komut için kullanıcı arabirimi öğesi için metin ayarlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|Kullanıcı arabirimi nesnesinin kimliği.|  
|[CCmdUI::m_nIndex](#m_nindex)|Kullanıcı arabirimi nesne dizini.|  
|[CCmdUI::m_pMenu](#m_pmenu)|Tarafından temsil edilen menü işaret `CCmdUI` nesnesi.|  
|[CCmdUI::m_pOther](#m_pother)|Bildirimi tarafından gönderilen pencere nesnesi noktalarına.|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Tarafından temsil edilen Kapsanan alt menüsünde işaret `CCmdUI` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CCmdUI`bir taban sınıfı yok.  
  
 Olduğunda, uygulamanızın bir kullanıcı, her, etkin olarak görüntülenmesi gerekip gerekmediğini bilmeniz menü öğesi gereksinimlerini veya devre dışı bir menüyü çeker. Menü komutu hedef uygulayarak bu bilgileri sağlar. bir `ON_UPDATE_COMMAND_UI` işleyicisi. Her komut kullanıcı arabirimi nesneleri uygulamanızdaki her işleyicisi için bir ileti eşleme girişi ve işlev prototipi oluşturmak için Özellikler penceresini kullanın.  
  
 Menü çekilen framework arar ve her çağırır `ON_UPDATE_COMMAND_UI` işleyicisi her işleyici çağırır `CCmdUI` üye işlevleri gibi **etkinleştirmek** ve **denetleyin**ve ardından çerçevesi uygun şekilde her bir menü öğesi görüntüler.  
  
 Menü öğesi denetim çubuğu düğmesini veya diğer komutu kullanıcı arabirimi nesnesi içindeki kod değiştirmeden değiştirilebilir `ON_UPDATE_COMMAND_UI` işleyicisi.  
  
 Aşağıdaki tabloda özetlenmiştir etkisi `CCmdUI`kullanıcının üye işlevleri sahip çeşitli komutu kullanıcı arabirimi öğeleri.  
  
|Kullanıcı arabirimi öğesi|Etkinleştir|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|Menü öğesi|Etkinleştirir veya devre dışı bırakır|Ya da temizler|Bir nokta kullanarak denetler|Metin ayarlar öğesi|  
|Araç çubuğu düğmesi|Etkinleştirir veya devre dışı bırakır|Seçer, seçili olanları kaldırdığında, veya belirsiz|Aynı`SetCheck`|(Uygulanamaz)|  
|Durum çubuğu bölmesi|Metin görünür veya görünmez yapar|Ayarlar açılan veya normal kenarlığı|Aynı`SetCheck`|Bölmesinde metni ayarlar|  
|Normal düğmesi`CDialogBar`|Etkinleştirir veya devre dışı bırakır|Ya da onay kutusunu temizler|Aynı`SetCheck`|Metin Ayarlar düğmesi|  
|Normal denetiminde`CDialogBar`|Etkinleştirir veya devre dışı bırakır|(Uygulanamaz)|(Uygulanamaz)|Pencere metni ayarlar|  
  
 Bu sınıf kullanımı hakkında daha fazla bilgi için bkz: [güncelleştirme kullanıcı arabirimi nesnelerini nasıl](../../mfc/how-to-update-user-interface-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CCmdUI`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="continuerouting"></a>CCmdUI::ContinueRouting  
 Geçerli ileti işleyicileri zincirine aşağı yönlendirme devam etmek için komut yönlendirme mekanizması bildirmek için bu üye işlevini çağırın.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte kullanılması gereken bir Gelişmiş üye işlevi budur bir `ON_COMMAND_EX` döndürür işleyici **FALSE**. Daha fazla bilgi için bkz: [Teknik Not 6](../../mfc/tn006-message-maps.md).  
  
##  <a name="enable"></a>CCmdUI::Enable  
 Etkinleştirmek veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakmak için bu üye işlevini çağırın.  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bOn`  
 **DOĞRU** öğeyi etkinleştirmek için **FALSE** devre dışı bırakmak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="m_nid"></a>CCmdUI::m_nID  
 Menü öğesi, araç çubuğu düğmesini veya tarafından temsil edilen diğer kullanıcı arabirimi nesne Kimliğini `CCmdUI` nesnesi.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_nindex"></a>CCmdUI::m_nIndex  
 Menü öğesi, araç çubuğu düğmesini veya diğer kullanıcı arabirimi nesnesi tarafından temsil edilen dizinini `CCmdUI` nesnesi.  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="m_pmenu"></a>CCmdUI::m_pMenu  
 İşaretçi (biri `CMenu` türü) tarafından temsil edilen menüsüne `CCmdUI` nesnesi.  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **NULL** öğesi bir menü değilse.  
  
##  <a name="m_psubmenu"></a>CCmdUI::m_pSubMenu  
 İşaretçi (biri `CMenu` türü) Kapsanan alt menüsüne tarafından temsil edilen `CCmdUI` nesnesi.  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **NULL** öğesi bir menü değilse. Alt menü bir açılır pencere ise `m_nID` açılır menüde ilk öğe Kimliğini içerir. Daha fazla bilgi için bkz: [Teknik Not 21](../../mfc/tn021-command-and-message-routing.md).  
  
##  <a name="m_pother"></a>CCmdUI::m_pOther  
 İşaretçi (tür `CWnd`), bir aracı ya da durum çubuğu gibi pencere nesnesi için bildirim gönderilir.  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **NULL** öğesi bir menüsü veya olmayan bir olup olmadığını `CWnd` nesnesi.  
  
##  <a name="setcheck"></a>CCmdUI::SetCheck  
 Bu komut için kullanıcı arabirimi öğesi uygun onay durumunu ayarlamak için bu üye işlevini çağırın.  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCheck`  
 Ayarlamak için onay durumunu belirtir. 0, temizler; 1 denetler; ve 2 ise belirsiz ayarlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi menü öğeleri ve araç çubuğu düğmeleri için çalışır. Belirlenmemiş bir durum yalnızca araç çubuğu düğmeleri için geçerlidir.  
  
##  <a name="setradio"></a>CCmdUI::SetRadio  
 Bu komut için kullanıcı arabirimi öğesi uygun onay durumunu ayarlamak için bu üye işlevini çağırın.  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bOn`  
 **DOĞRU** ; öğeyi etkinleştirmek için aksi **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev gibi çalışır `SetCheck`dışında kullanıcı arabirimi öğeleri radyo grubunun bir parçası işlev gören üzerinde çalışır. Grup içindeki diğer öğeler kaldırılırsa, öğeleri kendilerini radyo Grup davranışı korumak sürece otomatik değildir.  
  
##  <a name="settext"></a>CCmdUI::SetText  
 Bu komut için kullanıcı arabirimi öğesi metni ayarlamak için bu üye işlevini çağırın.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszText`  
 Bir metin dizesi için bir işaretçi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)
