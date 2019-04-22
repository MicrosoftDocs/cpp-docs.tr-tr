---
title: CControlBar sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 41e40b3da7b4a294fe396a9d93f7c6a93593ff95
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773248"
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
|[CControlBar::CControlBar](#ccontrolbar)|Oluşturur bir `CControlBar` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Bir dinamik denetim çubuğu boyutunu döndürür bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne.|
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Denetim çubuğu boyutunu döndürür bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne.|
|[CControlBar::CalcInsideRect](#calcinsiderect)|Denetim çubuğu alanına geçerli boyutlarını döndürür; sınırları dahil olmak üzere.|
|[CControlBar::DoPaint](#dopaint)|Kenarlıklar ve denetim çubuğu kavrayıcı işler.|
|[CControlBar::DrawBorders](#drawborders)|Denetim çubuğu kenarlıklarını işler.|
|[CControlBar::DrawGripper](#drawgripper)|Denetim çubuğu kavrayıcı işler.|
|[CControlBar::EnableDocking](#enabledocking)|Bir denetim çubuğuna sabitlenmiş veya kayan olmasını sağlar.|
|[CControlBar::GetBarStyle](#getbarstyle)|Denetim çubuğu stili ayarlarını alır.|
|[CControlBar::GetBorders](#getborders)|Denetim çubuğu kenarlık değerlerini alır.|
|[CControlBar::GetCount](#getcount)|Denetim çubuğuna HWND olmayan öğe sayısını döndürür.|
|[CControlBar::GetDockingFrame](#getdockingframe)|İçin bir denetim çubuğuna sabitlenmiş çerçevenin bir işaretçi döndürür.|
|[CControlBar::IsFloating](#isfloating)|Söz konusu denetim çubuğu kayan bir denetim çubuğu ise sıfır olmayan bir değer döndürür.|
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Komut UI işleyicilerini çağırır.|
|[CControlBar::SetBarStyle](#setbarstyle)|Denetim çubuğu stili ayarları değiştirir.|
|[CControlBar::SetBorders](#setborders)|Denetim çubuğu kenarlık değerlerini ayarlar.|
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Denetim çubuğu yerinde sahibini değiştirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Sıfır olmayan, `CControlBar` Windows Denetim çubuğu kaldırıldığında Nesne silindi.|
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Denetim çubuğu yerinde sahibi.|

## <a name="remarks"></a>Açıklamalar

Denetim çubuğu genellikle sola veya bir çerçeve penceresinin sağa hizalanmış bir penceredir. Alt öğeleri oluşturan ve Windows iletileri cevaplayin Windows HWND tabanlı denetimler ya da windows dışındaki ve uygulama kodu veya framework kodu tarafından yönetilen HWND tabanlı olmayan öğeler içerebilir. Liste kutuları ve düzenleme denetimleri HWND tabanlı denetimler örnektir; Durum çubuğu bölmeleri ve bit eşlem düğmeleri HWND tabanlı olmayan denetimleri örnekleridir.

Denetim çubuğu windows genellikle bir ana çerçeve penceresinin alt pencereler ve genellikle kardeş MDI çerçeve penceresinin istemci ve istemci görünümü. A `CControlBar` nesnenin kendisini konumlandırmak için ana pencerenin istemci dikdörtgeni hakkında bilgi kullanır. Ardından, ana pencerenin istemci alanında ne kadar alan ayrılmamış kalır seçeceğine üst penceresine bildirir.

Daha fazla bilgi için `CControlBar`, bkz:

- [Denetim Çubukları](../../mfc/control-bars.md)

- [Teknik Not 31: Denetim çubukları](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="calcdynamiclayout"></a>  CControlBar::CalcDynamicLayout

Framework, dinamik bir araç çubuğu boyutlarını hesaplamak için bu üye işlevini çağırır.

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>Parametreler

*nLength*<br/>
Yatay veya dikey bağlı olarak, denetim çubuğunun istenen boyutu *dwMode*.

*nMode*<br/>
Aşağıdaki önceden tanımlanmış bayrakları dinamik denetim çubuğu genişliği ve yüksekliği belirlemek için kullanılır. Bit düzeyinde OR kullanın (&#124;) bayraklarını birleştirmek istiyorsanız işleci.

|Düzen modu bayrakları|Anlamı|
|-----------------------|-------------------|
|LM_STRETCH|Denetim çubuğu çerçevenin boyutuna esnetilmiş olup olmadığını gösterir. Çubuk (yerleştirme için kullanılamaz) bir takma çubuğu değilse ayarlayın. Çubuk yerleşik veya kayan olduğunda (yerleştirme için kullanılabilir) ayarlanmadı. Ayarlanırsa, LM_STRETCH yoksayar, *nLength* ve boyutları LM_HORZ durumuna göre döndürür. Benzer şekilde çalışır LM_STRETCH *bStretch* kullanılan parametre [CalcFixedLayout](#calcfixedlayout); bu üye işlevi yönlendirme esnetmeyi ve arasındaki ilişki hakkında daha fazla bilgi için bkz.|
|LM_HORZ|Çubuk yatay veya dikey yönlendirilmiş olduğunu gösterir. Çubuk yatay olarak yönlendirilmiş olur ve dikey yönlendirilmiş ise ayarlı değil ayarlayın. Benzer şekilde çalışır LM_HORZ *bHorz* kullanılan parametre [CalcFixedLayout](#calcfixedlayout); bu üye işlevi yönlendirme esnetmeyi ve arasındaki ilişki hakkında daha fazla bilgi için bkz.|
|LM_MRUWIDTH|En son dinamik genişliği kullanılır. Yoksayar *nLength* parametresi ve kullandığı hatırlanan en son genişliği kullanılır.|
|LM_HORZDOCK|Yatay boyutları yerleştirilmiş. Yoksayar *nLength* parametre ve en büyük genişliği ile dinamik boyutu döndürür.|
|LM_VERTDOCK|Boyut dikey yerleştirilmiş. Yoksayar *nLength* parametresi ve dinamik boyut en fazla yüksekliği ile döndürür.|
|LM_LENGTHY|Verilirse *nLength* yüksekliği (Y yönünde) yerine genişliğini belirtir.|
|LM_COMMIT|Kayan denetim çubuğu geçerli genişliğini LM_MRUWIDTH sıfırlar.|

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu boyutu piksel cinsinden bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Kendi dinamik düzeni, türetilen sınıflarda sağlamak için bu üye işlevi geçersiz kılma `CControlBar`. MFC sınıflarından türetilen `CControlBar`, gibi [CToolbar](../../mfc/reference/ctoolbar-class.md), bu üye işlevi geçersiz kılma ve kendi uygulanmasını sağlar.

##  <a name="calcfixedlayout"></a>  CControlBar::CalcFixedLayout

Denetim çubuğu yatay boyutunu hesaplamak için bu üye işlevini çağırın.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

*bStretch*<br/>
Çubuk çerçevenin boyutuna esnetilmiş olup olmadığını gösterir. *BStretch* parametre olduğunda sıfır olmayan çubuğu (yerleştirme için kullanılamaz) bir takma çubuğu ve yerleşik veya kayan olduğunda 0 (yerleştirme için kullanılabilir).

*bHorz*<br/>
Çubuk yatay veya dikey yönlendirilmiş olduğunu gösterir. *BHorz* parametresi ise sıfır olmayan çubuğu yönlendirilmiş yatay ve dikey yönlendirilmiş ise 0'dır.

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu boyutu piksel cinsinden bir `CSize` nesne.

### <a name="remarks"></a>Açıklamalar

Denetim çubukları araç çubukları gibi yatay olarak genişletmek veya dikey olarak düğmeleri uyum sağlamak için denetim çubuğunda bulunan.

Varsa *bStretch* TRUE ise boyut tarafından sağlanan yönlendirmesini boyunca esnetme *bHorz*. Diğer bir deyişle, varsa *bHorz* yanlış, denetim çubuğu dikey olarak genişletilir. Varsa *bStretch* yanlış hiçbir esnetme gerçekleşir. Aşağıdaki tabloda, olası permutasyonları ve sonuçta elde edilen denetim çubuğu stilleri gösterir *bStretch* ve *bHorz*.

|bStretch|bHorz|Uzatma|Hizalama|Yerleştirme olmayan yerleştirme|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|Yatay uzatma|Yatay olarak yönelik|Yerleştirme değil|
|TRUE|FALSE|Dikey uzatma|Dikey yönelik|Yerleştirme değil|
|FALSE|TRUE|Kullanılabilir hiçbir uzatma|Yatay olarak yönelik|Yerleştirme|
|FALSE|FALSE|Kullanılabilir hiçbir uzatma|Dikey yönelik|Yerleştirme|

##  <a name="calcinsiderect"></a>  CControlBar::CalcInsideRect

Çerçevenin istemci alanını denetim çubuğunun hesaplamak için bu işlevi çağırır.

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Denetim çubuğu geçerli boyutlarını içerir. sınırları dahil olmak üzere.

*bHorz*<br/>
Çubuk yatay veya dikey yönlendirilmiş olduğunu gösterir. *BHorz* parametresi ise sıfır olmayan çubuğu yönlendirilmiş yatay ve dikey yönlendirilmiş ise 0'dır.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu boyanır önce bu işlev çağrılır.

Kenarlıklar ve denetim çubuğu kavrayıcı çubuğuna özelleştirmek için bu işlevi geçersiz kılar.

##  <a name="ccontrolbar"></a>  CControlBar::CControlBar

Oluşturur bir `CControlBar` nesne.

```
CControlBar();
```

##  <a name="dopaint"></a>  CControlBar::DoPaint

Kenarlıklar ve denetim çubuğu kavrayıcı çubuğunu işlemek için framework tarafından çağırılır.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Denetim çubuğu kavrayıcı ve Kenarlıkları çizmek için kullanılacak cihaz bağlamı işaret eder.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu çizim davranışını özelleştirmek için bu işlevi geçersiz kılar.

Başka bir özelleştirme yöntemi geçersiz kılmak için olan `DrawBorders` ve `DrawGripper` işlevleri ve tutma ve sınırları için özel çizim kodunu ekleyin. Bu yöntemler, varsayılan olarak adlandırılır çünkü `DoPaint` yöntemi, bir geçersiz kılma `DoPaint` gerekli değildir.

##  <a name="drawborders"></a>  CControlBar::DrawBorders

Denetim çubuğu kenarlıklarını işlemek için framework tarafından çağırılır.

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Denetim çubuğunun kenarlık çizmek için kullanılacak cihaz bağlamı işaret eder.

*Rect*<br/>
A `CRect` denetim çubuğu boyutlarını içeren nesne.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu kenarlık görünümünü özelleştirmek için bu işlevi geçersiz kılar.

##  <a name="drawgripper"></a>  CControlBar::DrawGripper

Denetim çubuğu kavrayıcı işlemek için framework tarafından çağırılır.

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Denetim çubuğu kavrayıcı çizmek için kullanılacak cihaz bağlamı işaret eder.

*Rect*<br/>
A `CRect` denetim çubuğu kavrayıcı boyutlarını içeren nesne.

### <a name="remarks"></a>Açıklamalar

Denetim çubuğu kavrayıcı görünümünü özelleştirmek için bu işlevi geçersiz kılar.

##  <a name="enabledocking"></a>  CControlBar::EnableDocking

Yerleştirilemediğinde denetim çubuğu etkinleştirmek için bu işlevi çağırın.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

*dwDockStyle*<br/>
Denetim çubuğu yerleştirme destekleyip desteklemediğini ve kendisine yerleştirilmiş denetim çubuğu olabilir, üst pencereye tarafının destekleniyorsa belirtir. Bir veya daha fazlasını olabilir:

- İstemci alanının en üstünde yerleştirme CBRS_ALIGN_TOP sağlar.

- İstemci alanının altındaki yerleştirme CBRS_ALIGN_BOTTOM sağlar.

- CBRS_ALIGN_LEFT istemci alanını sol tarafta yerleştirmeye izin verir.

- CBRS_ALIGN_RIGHT istemci alanının sağ tarafta yerleştirmeye izin verir.

- Cbrs_alıgn_any istemci alanının herhangi bir tarafta yerleştirmeye izin verir.

- Bir tek mini çerçeve penceresinde kaydırıldı birden çok denetim çubukları CBRS_FLOAT_MULTI sağlar.

0 ise (diğer bir deyişle, hiçbir bayrak belirten) denetim çubuğu değil sabitleneceğini.

### <a name="remarks"></a>Açıklamalar

Belirtilen yüz yüze hedef çerçeve penceresinde yerleştirme için etkin biriyle eşleşmelidir veya denetim çubuğu için bu çerçeve penceresinin yerleştirilmiş olamaz.

##  <a name="getbarstyle"></a>  CControlBar::GetBarStyle

Hangi belirlemek için bu işlevi çağırın **CBRS_** için denetim çubuğu ayarlayın (denetim çubuğu stilleri) ayarlar.

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli **CBRS_** (denetim çubuğu stilleri) ayarlarını denetim çubuğu. Bkz: [CControlBar::SetBarStyle](#setbarstyle) kullanılabilir stiller tam listesi için.

### <a name="remarks"></a>Açıklamalar

İşlemiyor **WS_** (pencere stili) stilleri.

##  <a name="getborders"></a>  CControlBar::GetBorders

Denetim çubuğu için geçerli sınır değerlerini döndürür.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CRect` her iki tarafındaki denetim çubuğuna nesnesinin geçerli genişliğini (piksel cinsinden) içeren nesne. Örneğin, değeri *sol* üyesi, [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne, sol kenarlık genişliği.

##  <a name="getcount"></a>  CControlBar::GetCount

HWND olmayan öğe sayısını verir `CControlBar` nesne.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

HWND olmayan öğe sayısını `CControlBar` nesne. Bu işlev için 0 değerini döndürür. bir [CDialogBar](../../mfc/reference/cdialogbar-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Öğenin türü türetilen nesneye bağlıdır: bölmelerini [CStatusBar](../../mfc/reference/cstatusbar-class.md) nesneleri ve düğmeler ve ayırıcılar için [CToolBar](../../mfc/reference/ctoolbar-class.md) nesneleri.

##  <a name="getdockingframe"></a>  CControlBar::GetDockingFrame

İçin denetim çubuğu yerleştirildiğini geçerli çerçeve işaretçisi elde etmek için bu üye işlevini çağırın.

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir çerçeve penceresi için bir işaretçi; bulunmazsa null değerini DÖNDÜRÜR.

Varsa (diğer bir deyişle, denetim çubuğu kayan varsa) denetim çubuğu için bir çerçeve penceresi yerleştirilmedi, bu işlev üst göreve işaretçi döndürür [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).

### <a name="remarks"></a>Açıklamalar

Yerleştirilebilir denetim çubukları hakkında daha fazla bilgi için bkz: [CControlBar::EnableDocking](#enabledocking) ve [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).

##  <a name="isfloating"></a>  CControlBar::IsFloating

Denetim çubuğu kayan veya sabit olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim çubuğu kayan olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kayan yerleştirilmiş denetim çubuğundan durumunu değiştirmek için çağrı [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).

##  <a name="m_bautodelete"></a>  CControlBar::m_bAutoDelete

Sıfır olmayan, `CControlBar` Windows Denetim çubuğu kaldırıldığında Nesne silindi.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Açıklamalar

*m_bAutoDelete* BOOL türü genel değişkenidir.

Bir denetim çubuğuna nesnesinin genellikle bir çerçeve pencere nesnesi eklenir. Bu durumda, *m_bAutoDelete* çerçeve penceresi kaldırıldığında denetim çubuğu gömülü nesne yok edilir çünkü 0'dır.

Bu değişken, ayırmak için sıfır olmayan bir değer verilirse bir `CControlBar` ve yığın nesnesi değil çağırmak planlama **Sil**.

##  <a name="m_pinplaceowner"></a>  CControlBar::m_pInPlaceOwner

Denetim çubuğu yerinde sahibi.

```
CWnd* m_pInPlaceOwner;
```

##  <a name="onupdatecmdui"></a>  CControlBar::OnUpdateCmdUI

Bu üye işlevi araç ya da durum çubuğunun durumunu güncelleştirmek için framework tarafından çağırılır.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
Uygulamanın ana çerçeve penceresinin işaret. Bu işaretçinin güncelleştirme iletileri yönlendirmek için kullanılır.

*bDisableIfNoHndler*<br/>
Hiçbir güncelleştirme işleyici içeren bir denetim devre dışı otomatik olarak görüntülenip görüntülenmeyeceğini gösteren bayrak.

### <a name="remarks"></a>Açıklamalar

Bir düğmeye veya bölmesi güncelleştirmek için bir güncelleştirme işleyici uygun şekilde ayarlamak için ileti eşlemede on_update_command_uı makrosu kullanın. Bkz: [on_update_command_uı](message-map-macros-mfc.md#on_update_command_ui) Bu makroyu kullanma hakkında daha fazla bilgi için.

`OnUpdateCmdUI` uygulamanın boşta olduğunda framework tarafından çağırılır. Güncelleştirilecek çerçeve penceresi bir alt pencere görünür bir çerçeve en az bir dolaylı olarak olmalıdır. `OnUpdateCmdUI` İleri düzey bir geçersiz kılınabilir.

##  <a name="setbarstyle"></a>  CControlBar::SetBarStyle

İstenen ayarlamak için bu işlevi çağırın **CBRS_** denetim çubuğu stilleri.

```
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Denetim çubuğu için istenen stilleri. Bir veya daha fazlasını olabilir:

- Bir çerçeve penceresinin istemci alanına üstüne yerleştirilemediğinde denetim çubuğu CBRS_ALIGN_TOP sağlar.

- Bir çerçeve penceresinin istemci alanına altına yerleştirilemediğinde denetim çubuğu CBRS_ALIGN_BOTTOM sağlar.

- Bir çerçeve penceresinin istemci alanına sol tarafına sabitlenebilir denetim çubuğu CBRS_ALIGN_LEFT sağlar.

- Bir çerçeve penceresinin istemci alanına sağ tarafına sabitlenebilir denetim çubuğu CBRS_ALIGN_RIGHT sağlar.

- Cbrs_alıgn_any herhangi bir çerçeve penceresinin istemci alanına tarafına sabitlenebilir denetim çubuğu sağlar.

- CBRS_BORDER_TOP zaman bunu görünür olur çubuğu denetiminin üst kenarı çizilecek kenarlık neden olur.

- CBRS_BORDER_BOTTOM zaman bunu görünür olur çubuğu denetimin alt kenarı çizilecek kenarlık neden olur.

- CBRS_BORDER_LEFT zaman bunu görünür olur çubuğu denetiminin sol kenarda çizilecek kenarlık neden olur.

- CBRS_BORDER_RIGHT zaman bunu görünür olur çubuğu denetiminin sağ kenarda çizilecek kenarlık neden olur.

- Bir tek mini çerçeve penceresinde kaydırıldı birden çok denetim çubukları CBRS_FLOAT_MULTI sağlar.

- Denetim çubuğu için görüntülenecek ipuçları aracı cbrs_tooltıps neden olur.

- Araç ipuçları olarak aynı anda güncelleştirilmesini metin iletisi CBRS_FLYBY neden olur.

- CBRS_GRIPPER kavrayıcı, benzer şekilde bant kullanılan neden olan bir `CReBar` nesnesi için çizilecek `CControlBar`-türetilmiş sınıf.

### <a name="remarks"></a>Açıklamalar

Etkilemez **WS_** (pencere stili) ayarlar.

##  <a name="setborders"></a>  CControlBar::SetBorders

Denetim çubuğunun kenarlık boyutunu ayarlamak için bu işlevi çağırın.

```
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*cxLeft*<br/>
Denetim çubuğunun sol kenarlık genişliğini (piksel cinsinden).

*cyTop*<br/>
Denetim çubuğunun üst kenarlık yüksekliği (piksel cinsinden).

*cxRight*<br/>
Denetim çubuğunun sağ kenarlık genişliğini (piksel cinsinden).

*cyBottom*<br/>
Denetim çubuğu alt kenarlık yüksekliği (piksel cinsinden).

*lpRect*<br/>
Bir işaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) her kenarlık denetim çubuğuna nesnesinin geçerli genişliğini (piksel cinsinden) içeren nesne.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, 5 piksel denetim çubuğunun üst ve alt kenarlıklarına ve sol ve sağ kenarlık 2 piksel olarak ayarlar:

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

##  <a name="setinplaceowner"></a>  CControlBar::SetInPlaceOwner

Denetim çubuğu yerinde sahibini değiştirir.

```
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Bir işaretçi bir `CWnd` nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CToolBar Sınıfı](../../mfc/reference/ctoolbar-class.md)<br/>
[CDialogBar Sınıfı](../../mfc/reference/cdialogbar-class.md)<br/>
[CStatusBar Sınıfı](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar Sınıfı](../../mfc/reference/crebar-class.md)
