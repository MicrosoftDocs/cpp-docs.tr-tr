---
title: "CControlBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
dev_langs:
- C++
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a911ff6251a6b34162377610ae139cfa3a7cefaa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccontrolbar-class"></a>CControlBar sınıfı
Denetim çubuğu sınıfları için temel sınıf [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), ve [ COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|Oluşturan bir `CControlBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Dinamik denetim çubuğu olarak boyutu döndüren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Denetim çubuğu olarak boyutu döndüren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|Denetim çubuğu alanı geçerli boyutlarını döndürür; kenarlıkları dahil olmak üzere.|  
|[CControlBar::DoPaint](#dopaint)|Kenarlıklar ve denetim çubuğunun Mandal işler.|  
|[CControlBar::DrawBorders](#drawborders)|Denetim çubuğu kenarlık işler.|  
|[CControlBar::DrawGripper](#drawgripper)|Denetim çubuğu Mandal işler.|  
|[CControlBar::EnableDocking](#enabledocking)|Denetim çubuğu yerleşik veya kayan olmasını sağlar.|  
|[CControlBar::GetBarStyle](#getbarstyle)|Denetim çubuğu stil ayarlarını alır.|  
|[CControlBar::GetBorders](#getborders)|Denetim çubuğu kenarlık değerlerini alır.|  
|[CControlBar::GetCount](#getcount)|Olmayan sayısını döndürür `HWND` denetim çubuğu öğeleri.|  
|[CControlBar::GetDockingFrame](#getdockingframe)|Bir işaretçi bir denetim çubuğu yerleşik olduğunda çerçeve döndürür.|  
|[CControlBar::IsFloating](#isfloating)|Kayan denetim çubuğu denetim çubuğu söz konusu ise, sıfır olmayan bir değer döndürür.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Komut UI işleyicileri çağırır.|  
|[CControlBar::SetBarStyle](#setbarstyle)|Denetim çubuğu stil ayarlarını değiştirir.|  
|[CControlBar::SetBorders](#setborders)|Denetim çubuğu kenarlık değerlerini ayarlar.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Denetim çubuğu yerinde sahibini değiştirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Sıfır olmayan, `CControlBar` nesnesi, Windows Denetim çubuğu kaldırıldığı zaman silinir.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Denetim çubuğu yerinde sahibi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu sola veya sağa bir çerçeve penceresinde genellikle hizalanır bir penceredir. Ya da alt öğeleri içerebilir `HWND`- oluşturan ve Windows iletileri ya da olmayan yanıt Windows denetimleri tabanlı - `HWND`-windows olmayan ve uygulama kodu veya framework kodu tarafından yönetilen öğeleri alan. Liste kutuları ve düzenleme denetimlerinde örnekleridir `HWND`- tabanlı denetimler; durum çubuğu bölmeleri ve bit eşlem düğmeler örnekleridir olmayan - `HWND`-denetimleri tabanlı.  
  
 Denetim çubuğu windows genellikle bir üst çerçeve penceresinin alt öğe pencerelerini ve genellikle eşdüzey istemci görünüm veya MDI istemcisi çerçeve penceresi. A `CControlBar` nesne kendisini konumlandırmak için üst pencerenin istemci dikdörtgen hakkında bilgileri kullanır. Sonra ana pencereyi ne kadar alan üst pencerenin istemci alanında ayrılmamış kalır konusunda sizi bilgilendirir.  
  
 Daha fazla bilgi için `CControlBar`, bkz:  
  
- [Denetim Çubukları](../../mfc/control-bars.md)  
  
- [Teknik Not 31: Denetim çubukları](../../mfc/tn031-control-bars.md).  
  
-   Bilgi Bankası makalesi Q242577: sorun: güncelleştirme komut UI işleyicileri yapmak çalışmıyor menü ekli bir iletişim kutusu için  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout  
 Framework'te dinamik bir araç çubuğu boyutlarını hesaplamak için bu üye işlevi çağırır.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nLength`  
 Yatay veya dikey bağlı olarak denetim çubuğunun istenen boyutu `dwMode`.  
  
 `nMode`  
 Aşağıdaki önceden tanımlı bayrak dinamik denetim çubuğu genişliği ve yüksekliği belirlemek için kullanılır. Bit düzeyinde-OR (&#124;) kullanın bayrakları birleştirmek için işleci.  
  
|Düzen modu bayrakları|Ne anlama geldiğini|  
|-----------------------|-------------------|  
|`LM_STRETCH`|Denetim çubuğu çerçevesinin boyutunu uzatılmış olup olmadığını gösterir. Çubuk (yerleştirme için kullanılamaz) bir takma çubuğu değilse ayarlayın. Çubuğu yerleşik veya kayan olduğunda (yerleştirme için kullanılabilir) ayarlanmadı. Varsa ayarlayın, `LM_STRETCH` yoksayar `nLength` ve temel boyutları döndürür `LM_HORZ` durumu. `LM_STRETCH`benzer şekilde çalışır `bStretch` kullanılan parametre [CalcFixedLayout](#calcfixedlayout); bu üye işlevi uzatma ve yönlendirmesini arasındaki ilişki hakkında daha fazla bilgi için bkz.|  
|`LM_HORZ`|Çubuk yatay veya dikey olarak yönlendirilmiş olduğunu gösterir. Çubuk yatay olarak yönlendirilmiş ise ve dikey olarak yönlendirilmiş ise ayarlı değil ayarlayın. `LM_HORZ`benzer şekilde çalışır `bHorz` kullanılan parametre [CalcFixedLayout](#calcfixedlayout); bu üye işlevi uzatma ve yönlendirmesini arasındaki ilişki hakkında daha fazla bilgi için bkz.|  
|**LM_MRUWIDTH**|En son dinamik genişliği kullanılır. Yoksayar `nLength` parametresi ve kullandığı hatırlanan en son genişliği kullanılır.|  
|`LM_HORZDOCK`|Yatay boyutları yerleştirildi. Yoksayar `nLength` parametre ve en büyük genişliği ile dinamik boyutu döndürür.|  
|`LM_VERTDOCK`|Dikey boyutları yerleştirildi. Yoksayar `nLength` parametre ve en fazla yüksekliği dinamik boyutuyla döndürür.|  
|`LM_LENGTHY`|Ayarlanabilir `nLength` genişliği yerine yüksekliği (Y yönü) gösterir.|  
|`LM_COMMIT`|Sıfırlar **LM_MRUWIDTH** kayan denetim çubuğu geçerli genişliğine.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu boyutu piksel cinsinden bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi, türetilen sınıflarda dinamik kendi düzeni sağlamak için geçersiz kılma `CControlBar`. MFC sınıfları türetilen `CControlBar`, gibi [CToolbar](../../mfc/reference/ctoolbar-class.md), bu üye işlevi geçersiz kılma ve kendi uygulama sağlayın.  
  
##  <a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout  
 Denetim çubuğu yatay boyutunu hesaplamak için bu üye işlevini çağırın.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 `bStretch`  
 Çubuğu çerçevesinin boyutunu uzatılmış olup olmadığını gösterir. `bStretch` Parametresi olduğunda sıfır olmayan çubuğu bir takma çubuğu (yerleştirme için kullanılamaz) değil ve yerleşik veya kayan olduğunda 0 (yerleştirme için kullanılabilir).  
  
 `bHorz`  
 Çubuk yatay veya dikey olarak yönlendirilmiş olduğunu gösterir. `bHorz` Çubuğu yatay olarak yönlendirilmiş ve dikey olarak yönlendirilmiş ise 0 ise parametresi sıfırdan farklı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu boyutu piksel cinsinden bir `CSize` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubukları araç çubukları gibi yatay uzatabilirsiniz veya dikey düğmeleri uyum sağlamak için denetim çubuğunda bulunan.  
  
 Varsa `bStretch` olan **TRUE**, boyut tarafından sağlanan yönlendirme boyunca uzatma `bHorz`. Diğer bir deyişle, varsa `bHorz` olan **yanlış**, denetim çubuğu dikey olarak genişletilir. Varsa `bStretch` olan **yanlış**, hiçbir esnetme oluşur. Aşağıdaki tabloda, olası alternatifler ve sonuçta elde edilen denetim çubuğu stilleri gösterir `bStretch` ve `bHorz`.  
  
|bStretch|bHorz|Uzatma|Yönlendirme|Yerleştirme değil yerleştirme|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**TRUE**|**TRUE**|Yatay uzatma|Yatay yönelimli|Yerleştirme değil|  
|**TRUE**|**FALSE**|Dikey uzatma|Dikey yönelimli|Yerleştirme değil|  
|**FALSE**|**TRUE**|Hiçbir kullanılabilir uzatma|Yatay yönelimli|Yerleştirme|  
|**FALSE**|**FALSE**|Hiçbir kullanılabilir uzatma|Dikey yönelimli|Yerleştirme|  
  
##  <a name="calcinsiderect"></a>CControlBar::CalcInsideRect  
 Çerçeve denetim çubuğu istemci alanını hesaplamak için bu işlevi çağırır.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Denetim çubuğu geçerli boyutlarını içerir; kenarlıkları dahil olmak üzere.  
  
 `bHorz`  
 Çubuk yatay veya dikey olarak yönlendirilmiş olduğunu gösterir. `bHorz` Çubuğu yatay olarak yönlendirilmiş ve dikey olarak yönlendirilmiş ise 0 ise parametresi sıfırdan farklı.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu boyanır önce bu işlev çağrılır.  
  
 Kenarlıklar ve Mandal çubuğu denetim çubuğunun özelleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="ccontrolbar"></a>CControlBar::CControlBar  
 Oluşturan bir `CControlBar` nesnesi.  
  
```  
CControlBar();
```  
  
##  <a name="dopaint"></a>CControlBar::DoPaint  
 Kenarlıklar ve Mandal çubuğu denetim çubuğunun işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Kenarlıklar ve denetim çubuğunun Mandal çizmek için kullanılacak cihaz bağlamı noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu çizim davranışını özelleştirmek için bu işlevi geçersiz kılar.  
  
 Başka bir özelleştirme yöntemi geçersiz kılmaktır `DrawBorders` ve `DrawGripper` işlevleri ve tutma ve sınırları için özel çizim kodunu ekleyin. Bu yöntem varsayılan olarak adlandırılır çünkü `DoPaint` yöntemi, bir geçersiz kılma `DoPaint` gerekli değildir.  
  
##  <a name="drawborders"></a>CControlBar::DrawBorders  
 Denetim çubuğu kenarlık işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Denetim çubuğu Kenarlıkları çizmek için kullanılacak cihaz bağlamı noktalarına.  
  
 `rect`  
 A `CRect` denetim çubuğu boyutlarını içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu kenarlık görünümünü özelleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="drawgripper"></a>CControlBar::DrawGripper  
 Denetim çubuğu Mandal işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Denetim çubuğu Mandal çizmek için kullanılacak cihaz bağlamı noktalarına.  
  
 `rect`  
 A `CRect` denetim çubuğu Mandal boyutlarını içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubuğu Mandal görünümünü özelleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="enabledocking"></a>CControlBar::EnableDocking  
 Yerleşik bir denetim çubuğu etkinleştirmek için bu işlevini çağırın.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDockStyle`  
 Denetim çubuğu yerleştirme destekleyip desteklemediğini ve kendisine denetim çubuğu yerleşik, kendi üst penceresi yanlarından destekleniyorsa belirtir. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `CBRS_ALIGN_TOP`İstemci alanının üstünde yerleştirme sağlar.  
  
- `CBRS_ALIGN_BOTTOM`İstemci alanı altındaki yerleştirme sağlar.  
  
- `CBRS_ALIGN_LEFT`İstemci alanını sol tarafta yerleştirme sağlar.  
  
- `CBRS_ALIGN_RIGHT`İstemci alanını sağ tarafta yerleştirme sağlar.  
  
- `CBRS_ALIGN_ANY`Tüm istemci alanını tarafında yerleştirme sağlar.  
  
- `CBRS_FLOAT_MULTI`Birden çok denetim çubukları tek kısa çerçeve penceresinde kaydırılmış sağlar.  
  
 0 ise (diğer bir deyişle, hiçbir bayrakları belirtir), denetim çubuğu değil sabitleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen yanları hedef çerçeve penceresinde yerleştirme için etkin yanları biriyle eşleşmelidir veya denetim çubuğu, çerçeve penceresi yerleşik olamaz.  
  
##  <a name="getbarstyle"></a>CControlBar::GetBarStyle  
 Hangi belirlemek için bu işlevi çağırmak **CBRS_** için denetim çubuğu ayarlayın (denetim çubuğu stilleri) ayarlar.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli **CBRS_** denetim çubuğu için (denetim çubuğu stilleri) ayarlar. Bkz: [CControlBar::SetBarStyle](#setbarstyle) kullanılabilir stiller tam listesi için.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlemiyor **WS_** (pencere stili) stilleri.  
  
##  <a name="getborders"></a>CControlBar::GetBorders  
 Denetim çubuğu geçerli sınır değerleri döndürür.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CRect` her iki tarafındaki denetim çubuğu nesnesi geçerli genişliğini (piksel cinsinden) içeren nesne. Örneğin, değeri `left` üyesi, [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne, sol kenarlık genişliği.  
  
##  <a name="getcount"></a>CControlBar::GetCount  
 Olmayan sayısını döndürür `HWND` üzerinde öğelerini `CControlBar` nesnesi.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olmayan sayısı `HWND` üzerinde öğelerini `CControlBar` nesnesi. Bu işlev için 0 döndürür bir [CDialogBar](../../mfc/reference/cdialogbar-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir nesne üzerinde öğesi türüne bağlıdır: bölmeleri için [CStatusBar](../../mfc/reference/cstatusbar-class.md) nesneleri ve düğmeleri ve ayırıcılar için [CToolBar](../../mfc/reference/ctoolbar-class.md) nesneleri.  
  
##  <a name="getdockingframe"></a>CControlBar::GetDockingFrame  
 Denetim çubuğu yerleşik olduğunda geçerli çerçeve penceresi için bir işaretçi almak için bu üye işlevini çağırın.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve penceresi başarılı olursa bir işaretçi; Aksi takdirde **NULL**.  
  
 Varsa (diğer bir deyişle, denetim çubuğu kayan varsa) için bir çerçeve pencere denetim çubuğu yerleştirilmedi, bu işlev, üst bir işaretçi döndürülecek [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Dockable denetim çubukları hakkında daha fazla bilgi için bkz: [CControlBar::EnableDocking](#enabledocking) ve [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
##  <a name="isfloating"></a>CControlBar::IsFloating  
 Denetim çubuğu kayan veya yerleştirilmiş olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim çubuğu kayan, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan yerleşik bir denetim çubuğundan durumunu değiştirmek için arama [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).  
  
##  <a name="m_bautodelete"></a>CControlBar::m_bAutoDelete  
 Sıfır olmayan, `CControlBar` nesnesi, Windows Denetim çubuğu kaldırıldığı zaman silinir.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_bAutoDelete`tür genel bir değişkendir **BOOL**.  
  
 Denetim çubuğu nesne, genellikle bir çerçeve penceresi nesnesinde katıştırılır. Bu durumda, `m_bAutoDelete` çerçeve pencere bozulduğunda katıştırılmış denetim çubuğu nesnesi yok olduğundan 0'dır.  
  
 Bu değişken tahsis sıfır olmayan bir değere ayarlamanız bir `CControlBar` öbek ve nesnesinde değil çağırmak planlama **silmek**.  
  
##  <a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner  
 Denetim çubuğu yerinde sahibi.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI  
 Bu üye işlev araç veya durum çubuğu durumunu güncelleştirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pTarget`  
 Uygulamanın ana çerçeve penceresi noktalarına. Bu işaretçinin güncelleştirme iletileri yönlendirmek için kullanılır.  
  
 `bDisableIfNoHndler`  
 Güncelleştirme işleyicisi sahip bir denetim otomatik olarak devre dışı görüntülenmesi gerekip gerekmediğini belirten bayrak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bireysel düğme veya bölmesi güncelleştirmek için `ON_UPDATE_COMMAND_UI` makro bir güncelleştirme işleyici uygun şekilde ayarlamak için ileti eşlemesi içinde. Bkz: [on_update_command_uı](message-map-macros-mfc.md#on_update_command_ui) bu makrosu kullanma hakkında daha fazla bilgi için.  
  
 `OnUpdateCmdUI`Uygulama boştayken çerçevesi tarafından çağrılır. Güncelleştirilecek çerçeve penceresi alt pencere görünür çerçeve pencerenin en az bir dolaylı olarak olmalıdır. `OnUpdateCmdUI`İleri düzey bir geçersiz kılınabilir.  
  
##  <a name="setbarstyle"></a>CControlBar::SetBarStyle  
 İstenen ayarlamak için bu işlevi çağırmak **CBRS_** denetim çubuğu stilleri.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Denetim çubuğu için istenen stilleri. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `CBRS_ALIGN_TOP`Çerçeve penceresi istemci alanının üstüne yerleştirilmiş denetim çubuğu sağlar.  
  
- `CBRS_ALIGN_BOTTOM`Çerçeve penceresi istemci alanını altına yerleştirilmiş denetim çubuğu sağlar.  
  
- `CBRS_ALIGN_LEFT`Çerçeve penceresi istemci sayfasının sol tarafındaki için yerleşik denetim çubuğu sağlar.  
  
- `CBRS_ALIGN_RIGHT`İstemci alanını bir çerçeve penceresinin sağ tarafındaki yerleşik denetim çubuğu sağlar.  
  
- `CBRS_ALIGN_ANY`Herhangi bir çerçeve penceresinde istemci alanını tarafına yerleşik denetim çubuğu sağlar.  
  
- `CBRS_BORDER_TOP`Görünür zaman denetim çubuğunun üst kenarı çizilecek kenarlık neden olur.  
  
- `CBRS_BORDER_BOTTOM`Görünür zaman denetim çubuğu alt köşesine çizilecek kenarlık neden olur.  
  
- `CBRS_BORDER_LEFT`Görünür zaman denetim çubuğu sol kenarı çizilecek kenarlık neden olur.  
  
- `CBRS_BORDER_RIGHT`Görünür zaman üzerinde denetim çubuğunun sağ köşesine çizilecek kenarlık neden olur.  
  
- `CBRS_FLOAT_MULTI`Birden çok denetim çubukları tek kısa çerçeve penceresinde kaydırılmış sağlar.  
  
- `CBRS_TOOLTIPS`Denetim çubuğu için görüntülenecek araç ipuçları neden olur.  
  
- `CBRS_FLYBY`Araç ipuçları aynı zamanda güncelleştirilmesi ileti metni neden olur.  
  
- **CBRS_GRIPPER** bantları içinde kullanılan benzeyen bir Mandal neden olan bir **CReBar** için çizilecek nesne `CControlBar`-türetilmiş sınıf.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkilemez **WS_** (pencere stili) ayarlar.  
  
##  <a name="setborders"></a>CControlBar::SetBorders  
 Denetim çubuğu kenarlık boyutunu ayarlamak için bu işlevini çağırın.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 *cxLeft*  
 Denetim çubuğu sol kenarlık genişliğini (piksel cinsinden).  
  
 *cyTop*  
 Denetim çubuğu üst kenarlık yüksekliği (piksel cinsinden).  
  
 *cxRight*  
 Denetim çubuğunun sağ kenarlık genişliğini (piksel cinsinden).  
  
 *cyBottom*  
 Denetim çubuğu alt kenarlık yüksekliği (piksel cinsinden).  
  
 `lpRect`  
 Bir işaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) her kenarlık denetim çubuğu nesnesinin geçerli genişliğini (piksel cinsinden) içeren nesne.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde 5 piksel denetim çubuğunun üst ve alt kenarlık ve sol ve sağ kenarlıkları 2 piksel olarak ayarlar:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="setinplaceowner"></a>CControlBar::SetInPlaceOwner  
 Denetim çubuğu yerinde sahibini değiştirir.  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Bir işaretçi bir `CWnd` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CToolBar sınıfı](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar sınıfı](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar sınıfı](../../mfc/reference/cstatusbar-class.md)   
 [CReBar Sınıfı](../../mfc/reference/crebar-class.md)
