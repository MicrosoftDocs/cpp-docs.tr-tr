---
title: "CReBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
dev_langs: C++
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cd32c4df0465426d99ca6246648520d160f382e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crebar-class"></a>CReBar sınıfı
Denetim çubuğu düzeni, sürdürme ve rebar denetimleri için durum bilgilerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CReBar : public CControlBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CReBar::AddBar](#addbar)|Bir bandı bir rebar ekler.|  
|[CReBar::Create](#create)|Rebar denetimi oluşturur ve ona ekler `CReBar` nesnesi.|  
|[CReBar::GetReBarCtrl](#getrebarctrl)|Temel alınan ortak denetimi doğrudan erişim sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir rebar nesnesi alt öğe pencerelerini, Düzen kutuları, araç çubukları ve liste kutuları dahil genellikle diğer denetimler çeşitli içerebilir. Bir rebar nesnesi, alt öğe pencerelerini belirtilen bir bit eşlem görüntüleyebilirsiniz. Uygulamanızı rebar otomatik olarak yeniden boyutlandırın veya tıklatarak ya da Mandal çubuğunu sürükleyerek kullanıcı el ile rebar genişletebilir.  
  
 ![RebarMenu örneği](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Rebar denetimi  
 Bir rebar nesnesi bir araç nesnesine benzer şekilde davranır. Bir rebar kendi bantları yeniden boyutlandırmak için tıklatın ve sürükleyin mekanizması kullanır. Rebar denetimiyle Mandal çubuğu, bir bit eşlem, bir metin etiketi ve alt pencere herhangi bir bileşimini sahip her bant ile bir veya daha fazla bantları içerebilir. Ancak, bantlar birden fazla alt pencere içeremez.  
  
 **CReBar** kullanan [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) kendi uygulama sunmak amacıyla sınıfı. Rebar denetimi aracılığıyla erişebilirsiniz [GetReBarCtrl](#getrebarctrl) denetimin özelleştirme seçenekleri yararlanmak için. Rebar denetimleri hakkında daha fazla bilgi için bkz: `CReBarCtrl`. Rebar denetimleri kullanma hakkında daha fazla bilgi için bkz: [kullanarak CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  Rebar ve rebar denetimi nesneleri yerleştirme çubuğu MFC denetim desteklemez. Varsa **CRebar::EnableDocking** , uygulamanızın assert denir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="addbar"></a>CReBar::AddBar  
 Rebar bir bant eklemek için bu üye işlevini çağırın.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

 
BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBar`  
 Bir işaretçi bir `CWnd` rebar eklenecek alt pencere nesnesi. Başvurulan nesne olmalıdır bir **WS_CHILD**.  
  
 `lpszText`  
 Rebar üzerinde görüntülenecek metni içeren bir dize için bir işaretçi. **NULL** varsayılan olarak. Bulunan metin `lpszText` alt pencere; parçası olmayan rebar üzerinde değil.  
  
 `pbmp`  
 Bir işaretçi bir `CBitmap` rebar arka planda görüntülenecek nesne. **NULL** varsayılan olarak.  
  
 `dwStyle`  
 A `DWORD` rebar uygulamak için stili içeren. Bkz **fStyle** işlev Win32 yapısı açıklamasında [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) bant stilleri tam bir listesi.  
  
 *clrFore*  
 A **COLORREF** rebar ön plan rengini gösteren bir değer.  
  
 *clrBack*  
 A **COLORREF** rebar arka plan rengi temsil eden bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]  
  
##  <a name="create"></a>CReBar::Create  
 Bir rebar oluşturmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 İşaretçi `CWnd` olan Windows penceresi durum çubuğunun üst nesne. Normalde, çerçeve penceresi.  
  
 `dwCtrlStyle`  
 Rebar denetimi stili. Varsayılan olarak, **RBS_BANDBORDERS**, hangi görüntüler rebar denetimi içinde bitişik bantları ayırmak için satırları daraltın. Bkz: [Rebar denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb774377) stilleri listesi için Windows SDK.  
  
 `dwStyle`  
 Rebar pencere stilleri.  
  
 `nID`  
 Rebar ait alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CReBar::AddBar](#addbar).  
  
##  <a name="getrebarctrl"></a>CReBar::GetReBarCtrl  
 Bu üye işlevi temel ortak denetimi doğrudan erişim sağlar.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru bir [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Rebar özelleştirme Windows rebar ortak kontrol işlevsellikten yararlanmak için bu üye işlevini çağırın. Çağırdığınızda `GetReBarCtrl`, bir başvuru nesnesi döndüren `CReBarCtrl` ya da kümesi üye işlevlerini kullanabilmeniz için nesne.  
  
 Kullanma hakkında daha fazla bilgi için `CReBarCtrl` , rebar özelleştirmek için bkz: [kullanarak CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MFCIE](../../visual-cpp-samples.md)   
 [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



