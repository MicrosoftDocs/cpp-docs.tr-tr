---
title: CScrollBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
dev_langs:
- C++
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90f672cbeeee0c297e3d1deb6a6b5e83bffda3e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372775"
---
# <a name="cscrollbar-class"></a>CScrollBar sınıfı
Windows kaydırma çubuğu denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CScrollBar : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CScrollBar::CScrollBar](#cscrollbar)|Oluşturan bir `CScrollBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CScrollBar::Create](#create)|Windows kaydırma çubuğu oluşturur ve ona ekler `CScrollBar` nesnesi.|  
|[CScrollBar::EnableScrollBar](#enablescrollbar)|Etkinleştirir veya bir kaydırma çubuğunun biri veya her ikisi oklarının devre dışı bırakır.|  
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|Kaydırma çubuğu kullanma hakkında bilgi alır bir `SCROLLBARINFO` yapısı.|  
|[CScrollBar::GetScrollInfo](#getscrollinfo)|Kaydırma çubuğu hakkında bilgi alır.|  
|[CScrollBar::GetScrollLimit](#getscrolllimit)|Kaydırma çubuğu sınırını alır.|  
|[CScrollBar::GetScrollPos](#getscrollpos)|Bir kaydırma kutusunun geçerli konumunu alır.|  
|[CScrollBar::GetScrollRange](#getscrollrange)|Verilen kaydırma çubuğu için geçerli minimum ve maksimum kaydırma çubuğu konumlarına alır.|  
|[CScrollBar::SetScrollInfo](#setscrollinfo)|Kaydırma çubuğu hakkında bilgi ayarlar.|  
|[CScrollBar::SetScrollPos](#setscrollpos)|Bir kaydırma kutusunun geçerli konumunu ayarlar.|  
|[CScrollBar::SetScrollRange](#setscrollrange)|Verilen kaydırma çubuğu için minimum ve maksimum konum değerleri ayarlar.|  
|[CScrollBar::ShowScrollBar](#showscrollbar)|Gösterir veya bir kaydırma çubuğunun gizler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaydırma çubuğu denetimi iki adımda oluşturun. İlk olarak, Oluşturucusu çağrısı `CScrollBar` oluşturmak için `CScrollBar` nesne sonra çağırın [oluşturma](#create) Windows kaydırma çubuğu denetimi oluşturmak ve ona eklemek için üye işlevi `CScrollBar` nesnesi.  
  
 Oluşturursanız, bir `CScrollBar` nesnesi (aracılığıyla bir iletişim kutusu kaynağı), bir iletişim kutusu içinde `CScrollBar` kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Oluşturursanız, bir `CScrollBar` nesne bir pencere içinde de gerekebilir, yok.  
  
 Oluşturursanız, `CScrollBar` nesne yığında otomatik olarak yok. Oluşturursanız, `CScrollBar` nesnesi kullanarak yığında **yeni** işlevini çağırmanız gerekir **silmek** kullanıcı Windows kaydırma çubuğu sonlandırıldığında yok etmek için nesne üzerinde.  
  
 Tüm bellekte ayırdığınızda `CScrollBar` nesne, geçersiz kılma `CScrollBar` yıkıcı ayrılmasını silmek için.  
  
 Kullanma hakkında ilgili bilgiler için `CScrollBar`, bkz: [denetimleri](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="create"></a>  CScrollBar::Create  
 Windows kaydırma çubuğu oluşturur ve ona ekler `CScrollBar` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Belirtir kaydırma çubuğunun stili. Herhangi bir bileşimini uygulamak [kaydırma çubuğu stilleri](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) kaydırma çubuğu.  
  
 `rect`  
 Kaydırma çubuğunun boyutunu ve konumunu belirtir. Ya da olabilir bir `RECT` yapısı veya `CRect` nesnesi.  
  
 `pParentWnd`  
 Belirtir kaydırma çubuğunun ana penceresinde, genellikle bir `CDialog` nesnesi. Değil olmalıdır **NULL**.  
  
 `nID`  
 Kaydırma çubuğu denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CScrollBar` iki adımda nesne. İlk olarak, yapıları Oluşturucusu çağrısı `CScrollBar` nesne;'ı çağırın **oluşturma**, oluşturur ve ilişkili Windows kaydırma çubuğu başlatır ve ekleninceye `CScrollBar` nesne.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir kaydırma çubuğuna:  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
- **WS_GROUP** grup denetimleri için  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]  
  
##  <a name="cscrollbar"></a>  CScrollBar::CScrollBar  
 Oluşturan bir `CScrollBar` nesnesi.  
  
```  
CScrollBar();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne oluşturma sonra çağrısı **oluşturma** oluşturmak ve Windows kaydırma çubuğu başlatmak için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]  
  
##  <a name="enablescrollbar"></a>  CScrollBar::EnableScrollBar  
 Etkinleştirir veya bir kaydırma çubuğunun biri veya her ikisi oklarının devre dışı bırakır.  
  
```  
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```  
  
### <a name="parameters"></a>Parametreler  
 `nArrowFlags`  
 Kaydırma oklarının etkin veya devre dışı bırakılan ve hangi okları etkin veya devre dışı belirtir. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- **ESB_ENABLE_BOTH** bir kaydırma çubuğunun her iki ok sağlar.  
  
- **ESB_DISABLE_LTUP** yatay kaydırma çubuğunun sol ok veya dikey kaydırma çubuğunun yukarı ok devre dışı bırakır.  
  
- **ESB_DISABLE_RTDN** yatay kaydırma çubuğunun sağ ok veya aşağı oka dikey kaydırma çubuğunun devre dışı bırakır.  
  
- **ESB_DISABLE_BOTH** bir kaydırma çubuğunun her iki ok devre dışı bırakır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oklar etkinleştirilirse veya belirtildiği şekilde devre dışı sıfır olmayan; Aksi takdirde 0, okları istenen durumda olduğunu veya bir hata oluştuğunu gösterir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="getscrollbarinfo"></a>  CScrollBar::GetScrollBarInfo  
 Bilgi alır, **SCROLLBARINFO** yapısı hakkında bir kaydırma çubuğunun korur.  
  
```  
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pScrollInfo*  
 Bir işaretçi [SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787535) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen [SBM_SCROLLBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb787545) , Windows SDK'ın açıklandığı gibi ileti.  
  
##  <a name="getscrollinfo"></a>  CScrollBar::GetScrollInfo  
 Bilgi alır, `SCROLLINFO` yapısı hakkında bir kaydırma çubuğunun korur.  
  
```  
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    UINT nMask = SIF_ALL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpScrollInfo`  
 Bir işaretçi bir [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) yapısı. Bu yapı hakkında daha fazla bilgi için Windows SDK konusuna bakın.  
  
 `nMask`  
 Alınacak kaydırma çubuğu parametreleri belirtir. Tipik kullanım, SIF_ALL, SIF_PAGE, SIF_POS, SIF_TRACKPOS ve SIF_RANGE bileşimini belirtir. Bkz: `SCROLLINFO` nMask değerleri hakkında daha fazla bilgi için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir değeri ileti alınan dönüş varsa, **doğru**. Aksi takdirde, değer **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetScrollInfo` uygulamaların 32-bit kaydırma konumlar kullanmasını sağlar.  
  
 [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) yapısı çubuğu, minimum ve maksimum konumlar, sayfa boyutu ve kaydırma kutusunun (Flash) konumunu kaydırma dahil olmak üzere bir kaydırma hakkında bilgiler içerir. Bkz: `SCROLLINFO` yapısı varsayılanları değiştirme hakkında daha fazla bilgi için Windows SDK yapısı konuda.  
  
 MFC Windows iletisi kaydırma çubuğu konumunu belirtmek işleyicileri [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) ve [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll), yalnızca 16 bit konum verileri sağlar. `GetScrollInfo` ve `SetScrollInfo` 32 bit kaydırma çubuğu konum verileri düzeyi sağlayın. Bu nedenle, bir uygulamanın çağırabileceği `GetScrollInfo` ya da işlerken `CWnd::OnHScroll` veya `CWnd::OnVScroll` 32-bit kaydırma çubuğu konum verileri elde edilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrolllimit"></a>  CScrollBar::GetScrollLimit  
 Konum kaydırma çubuğunun kaydırma maksimum alır.  
  
```  
int GetScrollLimit();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kaydırma çubuğunun başarılı olursa maksimum konumunu belirtir; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollpos"></a>  CScrollBar::GetScrollPos  
 Bir kaydırma kutusunun geçerli konumunu alır.  
  
```  
int GetScrollPos() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa kaydırma kutusunun geçerli konumunu belirler; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli konumu geçerli kaydırma aralığına bağlıdır göreli bir değerdir. Örneğin, 100 ile 200 kaydırma aralığı ve Kaydırma kutusu çubuğu ortasında ise, geçerli 150 konumdur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="getscrollrange"></a>  CScrollBar::GetScrollRange  
 Tarafından belirlenen konumlara verilen kaydırma çubuğu için geçerli minimum ve maksimum kaydırma çubuğu konumlarına kopyalar `lpMinPos` ve `lpMaxPos`.  
  
```  
void GetScrollRange(
    LPINT lpMinPos,  
    LPINT lpMaxPos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpMinPos`  
 En az konum alacak tamsayı değişken noktalarına.  
  
 `lpMaxPos`  
 En fazla konum alacak tamsayı değişken noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaydırma çubuğu denetimi için varsayılan aralığı boş (her iki değeri 0 olan).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll).  
  
##  <a name="setscrollinfo"></a>  CScrollBar::SetScrollInfo  
 Bilgi ayarlar `SCROLLINFO` yapısı hakkında bir kaydırma çubuğunun korur.  
  
```  
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpScrollInfo`  
 Bir işaretçi bir [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) yapısı.  
  
 `bRedraw`  
 Kaydırma çubuğu yeni bilgileri yansıtacak şekilde yeniden olup olmadığını belirtir. Varsa `bRedraw` olan **doğru**, kaydırma çubuğu çizilir. Eğer öyleyse **yanlış**, değil çizilir. Kaydırma çubuğu varsayılan olarak çizilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, dönüş olup olmadığını **doğru**. Aksi takdirde, değer **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekli değerleri de sağlamanız gerekir `SCROLLINFO` yapısı bayrak değerleri dahil parametreleri.  
  
 `SCROLLINFO` Yapısı çubuğu, minimum ve maksimum konumlar, sayfa boyutu ve kaydırma kutusunun (Flash) konumunu kaydırma dahil olmak üzere bir kaydırma hakkında bilgiler içerir. Bkz: [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) yapısı varsayılanları değiştirme hakkında daha fazla bilgi için Windows SDK yapısı konuda.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]  
  
##  <a name="setscrollpos"></a>  CScrollBar::SetScrollPos  
 Bir kaydırma kutusunun geçerli konumunu tarafından belirtilen ayarlar `nPos` ve belirtilmişse, yeni konumu yansıtacak şekilde kaydırma çubuğu yeniden çizer.  
  
```  
int SetScrollPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Kaydırma kutusu yeni konumunu belirtir. Kaydırma aralığında olmalıdır.  
  
 `bRedraw`  
 Kaydırma çubuğu yeni konumu yansıtacak şekilde yeniden olup olmadığını belirtir. Varsa `bRedraw` olan **doğru**, kaydırma çubuğu çizilir. Eğer öyleyse **yanlış**, değil çizilir. Kaydırma çubuğu varsayılan olarak çizilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa kaydırma kutusunun önceki konumunu belirler; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `bRedraw` için **FALSE** her kaydırma çubuğu yeniden düzenlenmiş iki kez kısa bir süre içinde yeniden kaydırma çubuğu zorunda kalmamak için bir sonraki başka bir işlevi çağrısı tarafından.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CScrollBar::SetScrollRange](#setscrollrange).  
  
##  <a name="setscrollrange"></a>  CScrollBar::SetScrollRange  
 Verilen kaydırma çubuğu için minimum ve maksimum konum değerleri ayarlar.  
  
```  
void SetScrollRange(
    int nMinPos,  
    int nMaxPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMinPos`  
 Konum kaydırma en küçük belirtir.  
  
 `nMaxPos`  
 Konum kaydırma en büyük belirtir.  
  
 `bRedraw`  
 Kaydırma çubuğu değişikliği yansıtacak şekilde yeniden olup olmadığını belirtir. Varsa `bRedraw` olan **TRUE**, kaydırma çubuğu; varsa çizilme **yanlış**, değil çizilir. Varsayılan olarak çizilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `nMinPos` ve `nMaxPos` standart kaydırma çubukları gizlemek için 0.  
  
 Bir kaydırma çubuğunun kaydırma çubuğu bildirim iletisi işlenirken gizlemek için bu işlevi çağırmayın.  
  
 Çağrı, `SetScrollRange` hemen takip `SetScrollPos` set üyesi işlevi `bRedraw` içinde `SetScrollPos` kaydırma çubuğu iki kez yeniden engellemek için 0.  
  
 Tarafından belirtilen değerler arasındaki farkın `nMinPos` ve `nMaxPos` 32.767 büyük olmamalıdır. Kaydırma çubuğu denetimi için varsayılan aralığı boş (her ikisi de `nMinPos` ve `nMaxPos` 0).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]  
  
##  <a name="showscrollbar"></a>  CScrollBar::ShowScrollBar  
 Gösterir veya bir kaydırma çubuğunun gizler.  
  
```  
void ShowScrollBar(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bShow`  
 Kaydırma çubuğu gösterileceğini veya gizleneceğini olup olmadığını belirtir. Bu parametre ise **doğru**, kaydırma çubuğu gösterilir; Aksi halde gizlenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uygulama bir kaydırma çubuğunun kaydırma çubuğu bildirim iletisi işlenirken gizlemek için bu işlevi çağırmalıdır değil.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CScrollBar::Create](#create).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CButton sınıfı](../../mfc/reference/cbutton-class.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CListBox sınıfı](../../mfc/reference/clistbox-class.md)   
 [CStatic sınıfı](../../mfc/reference/cstatic-class.md)   
 [CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
