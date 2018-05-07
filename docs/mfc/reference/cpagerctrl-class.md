---
title: CPagerCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
dev_langs:
- C++
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d22aa408fe2933803083adc784c2dbf3a85dd4df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cpagerctrl-class"></a>CPagerCtrl sınıfı
`CPagerCtrl` Sınıfı görünüme içeren pencere sığmayan kapsanan bir pencere kaydırabilirsiniz Windows çağrı cihazı denetimi sarmalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Oluşturan bir `CPagerCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPagerCtrl::Create](#create)|Çağrı cihazı denetimi ile belirtilen stilleri oluşturur ve geçerli ekler `CPagerCtrl` nesnesi.|  
|[CPagerCtrl::CreateEx](#createex)|Belirtilen genişletilmiş stiliyle bir çağrı cihazı denetimi oluşturur ve geçerli ekler `CPagerCtrl` nesnesi.|  
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Etkinleştirir veya devre dışı bırakır, iletme [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) geçerli çağrı cihazı denetiminde bulunan pencere iletileri.|  
|[CPagerCtrl::GetBkColor](#getbkcolor)|Geçerli çağrı cihazı denetim arka plan rengini alır.|  
|[CPagerCtrl::GetBorder](#getborder)|Geçerli çağrı cihazı Denetim kenarlık boyutunu alır.|  
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Geçerli çağrı cihazı denetim düğmesi boyutunu alır.|  
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Belirtilen düğmesi geçerli çağrı cihazı denetiminde durumunu alır.|  
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Alır [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) geçerli çağrı cihazı denetimi için arabirim.|  
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Geçerli çağrı cihazı denetimin kaydırma konumunu alır.|  
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Belirtilen düğmesi geçerli çağrı cihazı denetiminin içinde olup olmadığını belirten `pressed` durumu.|  
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Belirtilen düğmesi geçerli çağrı cihazı denetiminin içinde olup olmadığını belirten `grayed` durumu.|  
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Belirtilen düğmesi geçerli çağrı cihazı denetiminin içinde olup olmadığını belirten `hot` durumu.|  
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Belirtilen düğmesi geçerli çağrı cihazı denetiminin içinde olup olmadığını belirten `invisible` durumu.|  
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Belirtilen düğmesi geçerli çağrı cihazı denetiminin içinde olup olmadığını belirten `normal` durumu.|  
|[CPagerCtrl::RecalcSize](#recalcsize)|Kapsanan pencere boyutunu yeniden hesaplamak geçerli çağrı cihazı denetimi neden olur.|  
|[CPagerCtrl::SetBkColor](#setbkcolor)|Geçerli çağrı cihazı denetim arka plan rengini belirler.|  
|[CPagerCtrl::SetBorder](#setborder)|Geçerli çağrı cihazı Denetim kenarlık boyutunu ayarlar.|  
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Geçerli çağrı cihazı denetim düğmesi boyutunu ayarlar.|  
|[CPagerCtrl::SetChild](#setchild)|Kapsanan pencerenin geçerli çağrı cihazı denetimi için ayarlar.|  
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Geçerli çağrı cihazı denetimin kaydırma konumunu ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrı cihazı denetim doğrusal ve içeren pencerenin daha büyük ve içerdiği pencere görünüme kaydırma sağlayan başka bir pencere içeren bir penceredir. Çağrı cihazı denetim içerdiği pencere kaydırılan yükleyen otomatik olarak en uzak ölçüde kaybolur iki kaydırma düğmeleri görüntüler ve aksi durumda yeniden. Yatay veya dikey olarak kayar bir çağrı cihazı denetim oluşturabilirsiniz.  
  
 Örneğin, uygulamanız tüm öğeleri göstermek için geniş değil bir araç çubuğu varsa, çağrı cihazı denetime araç atayabilirsiniz ve kullanıcıların araç çubuğuna tüm öğeleri erişmek için sağa veya sola kaydırma mümkün olacaktır. Microsoft Internet Explorer sürüm 4.0 (commctrl.dll sürüm 4.71) çağrı cihazı denetim sunar.  
  
 `CPagerCtrl` Sınıfı türetilir [CWnd](../../mfc/reference/cwnd-class.md) sınıfı. Daha fazla bilgi ve bir çağrı cihazı denetimi bir çizimi için bkz: [çağrı cihazı denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPagerCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl  
 Oluşturan bir `CPagerCtrl` nesnesi.  
  
```  
CPagerCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CPagerCtrl::Create](#create) veya [CPagerCtrl::CreateEx](#createex) çağrı cihazı denetim oluşturmak ve ona eklemek için yöntemi `CPagerCtrl` nesnesi.  
  
##  <a name="create"></a>  CPagerCtrl::Create  
 Çağrı cihazı denetimi ile belirtilen stilleri oluşturur ve geçerli ekler `CPagerCtrl` nesnesi.  
  
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
|[in] `dwStyle`|Bit düzeyinde bileşimini (veya) [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859) denetime uygulanacak.|  
|[in] `rect`|Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları denetiminde boyutunu ve konumunu içeren yapısı.|  
|[in] `pParentWnd`|Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst pencere nesnesi. Bu parametre olamaz `NULL`.|  
|[in] `nID`|Denetimin kimliği.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı cihazı denetimi oluşturmak için bildirme bir `CPagerCtrl` değişkeni,'ı çağırın [CPagerCtrl::Create](#create) veya [CPagerCtrl::CreateEx](#createex) değişken yöntemi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun düğme denetimi çağrı cihazı denetimiyle ilişkilendirmek için yöntem. Bu örnek daha sonra kullanır [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı cihazı denetimin yüksekliğini 20 piksel olarak ayarlayın ve [CPagerCtrl::SetBorder](#setborder) kalınlığını 1 piksel ayarlamak için yöntemi.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CPagerCtrl::CreateEx  
 Belirtilen genişletilmiş stiliyle bir çağrı cihazı denetimi oluşturur ve geçerli ekler `CPagerCtrl` nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `dwExStyle`|Denetime uygulanacak genişletilmiş stilleri Bitsel bir birleşimi. Daha fazla bilgi için bkz: `dwExStyle` parametresinin [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) işlevi.|  
|[in] `dwStyle`|Bit düzeyinde bileşimini (veya) [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859) denetime uygulanacak.|  
|[in] `rect`|Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları denetiminde boyutunu ve konumunu içeren yapısı.|  
|[in] `pParentWnd`|Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) denetiminin üst pencere nesnesi. Bu parametre olamaz `NULL`.|  
|[in] `nID`|Denetimin kimliği.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı cihazı denetimi oluşturmak için bildirme bir `CPagerCtrl` değişkeni,'ı çağırın [CPagerCtrl::Create](#create) veya [CPagerCtrl::CreateEx](#createex) değişken yöntemi.  
  
##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse  
 Etkinleştirir veya devre dışı bırakır, iletme [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) geçerli çağrı cihazı denetiminde bulunan pencere iletileri.  
  
```  
void ForwardMouse(BOOL bForward);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `bForward`|`true` Fare iletilerini iletecek şekilde veya `false` fare iletileri iletmesini değil.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_FORWARDMOUSE](http://msdn.microsoft.com/library/windows/desktop/bb760867) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getborder"></a>  CPagerCtrl::GetBorder  
 Geçerli çağrı cihazı Denetim kenarlık boyutunu alır.  
  
```  
int GetBorder() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli kenarlık boyutunu piksel cinsinden ölçülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760869) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [CPagerCtrl::GetBorder](#getborder) çağrı cihazı denetimin kenarlığının kalınlığını alma yöntemi.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]  
  
##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor  
 Geçerli çağrı cihazı denetim arka plan rengini alır.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) çağrı cihazı denetim geçerli arka plan rengini içeren değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760868) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [CPagerCtrl::SetBkColor](#setbkcolor) yöntemi için kırmızı, çağrı cihazı denetim arka plan rengini ayarlama ve [CPagerCtrl::GetBkColor](#getbkcolor) yöntemi değişikliğinin yapıldığını onaylayın.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize  
 Geçerli çağrı cihazı denetim düğmesi boyutunu alır.  
  
```  
int GetButtonSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli düğme boyutu piksel cinsinden ölçülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760870) Windows SDK'ın açıklanan ileti.  
  
 Çağrı cihazı denetim varsa `PGS_HORZ` stilini, düğme boyutu çağrı cihazı düğmeleri genişliğini belirler ve çağrı cihazı denetim varsa `PGS_VERT` stilini, düğme boyutu çağrı cihazı düğmeleri yüksekliğini belirler. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState  
 Belirtilen kaydırma düğmesi geçerli çağrı cihazı denetiminde durumunu alır.  
  
```  
DWORD GetButtonState(int iButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iButton`|İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetim stil ise `PGS_HORZ`, belirtin `PGB_TOPORLEFT` sol düğmesi için ve `PGB_BOTTOMORRIGHT` sağ düğmesi için. Çağrı cihazı denetim stil ise `PGS_VERT`, belirtin `PGB_TOPORLEFT` üst düğmesi için ve `PGB_BOTTOMORRIGHT` alt düğmesi için. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen düğmesinin durumunun `iButton` parametresi. Ya da bir durumda `PGF_INVISIBLE`, `PGF_NORMAL`, `PGF_GRAYED`, `PGF_DEPRESSED`, veya `PGF_HOT`. Daha fazla bilgi için dönüş değeri bölümüne bakın [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) ileti.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget  
 Alır [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) geçerli çağrı cihazı denetimi için arabirim.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `IDropTarget` geçerli çağrı cihazı denetimi için arabirim.  
  
### <a name="remarks"></a>Açıklamalar  
 `IDropTarget` Uygulamanız için arabirimleri biri uygulamanızda sürükle ve bırak işlemleri destekler.  
  
 Bu yöntem gönderir [PGM_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb760872) Windows SDK'ın açıklanan ileti. Bu yöntem arayan çağırmadan sorumludur `Release` üyesi [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) arabirim arabirimi artık gerekli olmadığında.  
  
##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos  
 Geçerli çağrı cihazı denetimin kaydırma konumunu alır.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli kaydırma konumunu piksel cinsinden ölçülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760874) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [CPagerCtrl::GetScrollPos](#getscrollpos) çağrı cihazı denetim geçerli kaydırma konumunu alma yöntemi. Çağrı cihazı denetim zaten sıfır, soldaki konumu kaydırılan değil örnek kullanıyorsa [CPagerCtrl::SetScrollPos](#setscrollpos) yöntemi kaydırma konumunu sıfır olarak ayarlayın.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]  
  
##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed  
 Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesini basılı durumda olup olmadığını gösterir.  
  
```  
BOOL IsButtonDepressed(int iButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iButton`|İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetim stil ise `PGS_HORZ`, belirtin `PGB_TOPORLEFT` sol düğmesi için ve `PGB_BOTTOMORRIGHT` sağ düğmesi için. Çağrı cihazı denetim stil ise `PGS_VERT`, belirtin `PGB_TOPORLEFT` üst düğmesi için ve `PGB_BOTTOMORRIGHT` alt düğmesi için. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Belirtilen düğmesini basılı durumdaysa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK'ın açıklanan ileti. Daha sonra döndürülen bir durumda olup olmadığını sınar `PGF_DEPRESSED`. Daha fazla bilgi için dönüş değeri bölümüne bakın [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) ileti.  
  
##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed  
 Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesi gri durumda olup olmadığını gösterir.  
  
```  
BOOL IsButtonGrayed(int iButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iButton`|İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetim stil ise `PGS_HORZ`, belirtin `PGB_TOPORLEFT` sol düğmesi için ve `PGB_BOTTOMORRIGHT` sağ düğmesi için. Çağrı cihazı denetim stil ise `PGS_VERT`, belirtin `PGB_TOPORLEFT` üst düğmesi için ve `PGB_BOTTOMORRIGHT` alt düğmesi için. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Belirtilen düğmesi gri durumda ise; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK'ın açıklanan ileti. Daha sonra döndürülen bir durumda olup olmadığını sınar `PGF_GRAYED`. Daha fazla bilgi için dönüş değeri bölümüne bakın [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) ileti.  
  
##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot  
 Geçerli çağrı cihazı denetiminin belirtilen kaydırma düğmesi etkin durumda olup olmadığını gösterir.  
  
```  
BOOL IsButtonHot(int iButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iButton`|İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetim stil ise `PGS_HORZ`, belirtin `PGB_TOPORLEFT` sol düğmesi için ve `PGB_BOTTOMORRIGHT` sağ düğmesi için. Çağrı cihazı denetim stil ise `PGS_VERT`, belirtin `PGB_TOPORLEFT` üst düğmesi için ve `PGB_BOTTOMORRIGHT` alt düğmesi için. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Belirtilen düğmesi etkin durumda ise; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK'ın açıklanan ileti. Daha sonra döndürülen bir durumda olup olmadığını sınar `PGF_HOT`. Daha fazla bilgi için dönüş değeri bölümüne bakın [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) ileti.  
  
##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible  
 Belirtilen kaydırma düğmesi geçerli çağrı cihazı denetiminin görünmez durumda olup olmadığını gösterir.  
  
```  
BOOL IsButtonInvisible(int iButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iButton`|İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetim stil ise `PGS_HORZ`, belirtin `PGB_TOPORLEFT` sol düğmesi için ve `PGB_BOTTOMORRIGHT` sağ düğmesi için. Çağrı cihazı denetim stil ise `PGS_VERT`, belirtin `PGB_TOPORLEFT` üst düğmesi için ve `PGB_BOTTOMORRIGHT` alt düğmesi için. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Belirtilen düğme görünmez durumda ise; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla düğmesini tıklatarak kapsanan pencerenin daha görünüme yapılamıyor çünkü kapsanan pencerenin en uzak ölçüde kaydırılan olduğunda Windows kaydırma düğmesi belirli bir yönde görünmez hale getirir.  
  
 Bu yöntem gönderir [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK'ın açıklanan ileti. Daha sonra döndürülen bir durumda olup olmadığını sınar `PGF_INVISIBLE`. Daha fazla bilgi için dönüş değeri bölümüne bakın [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) çağrı cihazı denetim sol ve sağ kaydırma düğmeleri görünür olup olmadığını belirlemek amacıyla yöntemi.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]  
  
##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal  
 Belirtilen kaydırma düğmesi geçerli çağrı cihazı denetiminin normal durumda olup olmadığını gösterir.  
  
```  
BOOL IsButtonNormal(int iButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iButton`|İçin durumu alınacağı düğmesini gösterir. Çağrı cihazı denetim stil ise `PGS_HORZ`, belirtin `PGB_TOPORLEFT` sol düğmesi için ve `PGB_BOTTOMORRIGHT` sağ düğmesi için. Çağrı cihazı denetim stil ise `PGS_VERT`, belirtin `PGB_TOPORLEFT` üst düğmesi için ve `PGB_BOTTOMORRIGHT` alt düğmesi için. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Belirtilen düğme normal durumdaysa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) Windows SDK'ın açıklanan ileti. Daha sonra döndürülen bir durumda olup olmadığını sınar `PGF_NORMAL`. Daha fazla bilgi için dönüş değeri bölümüne bakın [PGM_GETBUTTONSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760871) ileti.  
  
##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize  
 Kapsanan pencere boyutunu yeniden hesaplamak geçerli çağrı cihazı denetimi neden olur.  
  
```  
void RecalcSize();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_RECALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760876) Windows SDK'ın açıklanan ileti. Sonuç olarak, çağrı cihazı denetim gönderir [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) kapsanan penceresinin kaydırılabilir boyutları almak için bildirim.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [CPagerCtrl::RecalcSize](#recalcsize) boyutuna yeniden hesaplamak için geçerli çağrı cihazı denetim istek yöntemi.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [ileti yansıma](../../mfc/tn062-message-reflection-for-windows-controls.md) hesaplama gerçekleştirmek için denetimin üst iletişim gerektirmek yerine kendi boyutu yeniden hesaplamak çağrı cihazı denetimini etkinleştirmek için. Örnek türetilen `MyPagerCtrl` sınıfıyla [CPagerCtrl sınıfı](../../mfc/reference/cpagerctrl-class.md), ilişkilendirmek için ileti eşlemesi kullanır [PGN_CALCSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760864) bildirimi `OnCalcsize` bildirim işleyici. Bu örnekte, bildirim işleyici genişlik ve yükseklik çağrı cihazı denetiminin sabit değerleri ayarlar.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]  
  
##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor  
 Geçerli çağrı cihazı denetim arka plan rengini belirler.  
  
```  
COLORREF SetBkColor(COLORREF clrBk);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `clrBk`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) çağrı cihazı denetim yeni arka plan rengini içeren değer.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) çağrı cihazı denetim önceki arka plan rengini içeren değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760878) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [CPagerCtrl::SetBkColor](#setbkcolor) yöntemi için kırmızı, çağrı cihazı denetim arka plan rengini ayarlama ve [CPagerCtrl::GetBkColor](#getbkcolor) yöntemi değişikliğinin yapıldığını onaylayın.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]  
  
##  <a name="setborder"></a>  CPagerCtrl::SetBorder  
 Geçerli çağrı cihazı Denetim kenarlık boyutunu ayarlar.  
  
```  
int SetBorder(int iBorder);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iBorder`|Yeni sınır boyutu piksel cinsinden ölçülür. Varsa `iBorder` parametresi negatif, kenarlık boyutu sıfır olarak ayarlanır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki kenarlık boyutunu piksel cinsinden ölçülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_SETBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760880) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun düğme denetimi çağrı cihazı denetimiyle ilişkilendirmek için yöntem. Bu örnek daha sonra kullanır [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı cihazı denetimin yüksekliğini 20 piksel olarak ayarlayın ve [CPagerCtrl::SetBorder](#setborder) kalınlığını 1 piksel ayarlamak için yöntemi.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize  
 Geçerli çağrı cihazı denetim düğmesi boyutunu ayarlar.  
  
```  
int SetButtonSize(int iButtonSize);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iButtonSize`|Yeni düğmesi boyutunu piksel cinsinden ölçülür.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki düğmesini boyutunu piksel cinsinden ölçülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_SETBUTTONSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760886) Windows SDK'ın açıklanan ileti.  
  
 Çağrı cihazı denetim varsa `PGS_HORZ` stilini, düğme boyutu çağrı cihazı düğmeleri genişliğini belirler ve çağrı cihazı denetim varsa `PGS_VERT` stilini, düğme boyutu çağrı cihazı düğmeleri yüksekliğini belirler. Kaydırma çubuğu genişliği üç fourths varsayılan düğme boyutudur ve en az düğme boyutu 12 pikseldir. Daha fazla bilgi için bkz: [çağrı cihazı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760859).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun düğme denetimi çağrı cihazı denetimiyle ilişkilendirmek için yöntem. Bu örnek daha sonra kullanır [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı cihazı denetimin yüksekliğini 20 piksel olarak ayarlayın ve [CPagerCtrl::SetBorder](#setborder) kalınlığını 1 piksel ayarlamak için yöntemi.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setchild"></a>  CPagerCtrl::SetChild  
 Kapsanan pencerenin geçerli çağrı cihazı denetimi için ayarlar.  
  
```  
void SetChild(HWND hwndChild);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `hwndChild`|Pencereyi dahil edilmek üzere işleyin.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_SETCHILD](http://msdn.microsoft.com/library/windows/desktop/bb760884) Windows SDK'ın açıklanan ileti.  
  
 Bu yöntem kapsanan penceresinin üst değiştirmez; yalnızca kaydırma için çağrı cihazı denetlemek için bir pencere tanıtıcının atar. Çoğu durumda, çağrı cihazı denetimi alt pencere içerdiği pencere olacaktır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir çağrı cihazı denetimi oluşturur, ardından kullanan [CPagerCtrl::SetChild](#setchild) çok uzun düğme denetimi çağrı cihazı denetimiyle ilişkilendirmek için yöntem. Bu örnek daha sonra kullanır [CPagerCtrl::SetButtonSize](#setbuttonsize) yöntemi çağrı cihazı denetimin yüksekliğini 20 piksel olarak ayarlayın ve [CPagerCtrl::SetBorder](#setborder) kalınlığını 1 piksel ayarlamak için yöntemi.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]  
  
##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos  
 Geçerli çağrı cihazı denetimin kaydırma konumunu ayarlar.  
  
```  
void SetScrollPos(int iPos);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `iPos`|Yeni kaydırma konumunu piksel cinsinden ölçülür.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [PGM_SETPOS](http://msdn.microsoft.com/library/windows/desktop/bb760886) Windows SDK'ın açıklanan ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CPagerCtrl sınıfı](../../mfc/reference/cpagerctrl-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Çağrı cihazı denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb760855)



