---
title: CHeaderCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 430e4830cb41ebd229b25da426d7ddf482b9c90f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385540"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl sınıfı

Windows ortak üstbilgi denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Oluşturur bir `CHeaderCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Üstbilgi denetimi için tüm filtreleri kaldırır.|
|[CHeaderCtrl::ClearFilter](#clearfilter)|Üstbilgi denetimi için filtre temizler.|
|[CHeaderCtrl::Create](#create)|Üstbilgi denetimi oluşturur ve ona bağlanan bir `CHeaderCtrl` nesne.|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Üstbilgi denetimi içinde bir öğenin resminin saydam bir sürümü oluşturur.|
|[CHeaderCtrl::CreateEx](#createex)|Üstbilgi denetimi ile belirtilen Windows genişletilmiş stiller oluşturur ve ona ekler bir `CListCtrl` nesne.|
|[CHeaderCtrl::DeleteItem](#deleteitem)|Bir üst bilgi denetiminden bir öğeyi siler.|
|[CHeaderCtrl::DrawItem](#drawitem)|Üstbilgi denetimi belirtilen öğeyi çizer.|
|[CHeaderCtrl::EditFilter](#editfilter)|Belirtilen filtre bir üst bilgi denetiminin düzenleme başlatır.|
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Üstbilgi denetimindeki bir bit eşlem kenar genişliğini alır.|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Odaklanmış geçerli üstbilgi denetimindeki öğeyi tanımlayıcısını alır.|
|[CHeaderCtrl::GetImageList](#getimagelist)|Üstbilgi denetimindeki çizim üstbilgi öğeleri için kullanılan bir görüntü listesi tanıtıcısını alır.|
|[CHeaderCtrl::GetItem](#getitem)|Üstbilgi denetimindeki bir öğeyi hakkındaki bilgileri alır.|
|[CHeaderCtrl::GetItemCount](#getitemcount)|Üstbilgi denetimindeki öğeleri sayısını alır.|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Üstbilgi denetimindeki belirtilen açılan düğmeyi sınırlayıcı dikdörtgeni bilgilerini alır.|
|[CHeaderCtrl::GetItemRect](#getitemrect)|Üstbilgi denetimindeki belirli bir öğe için dikdörtgen alır.|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Üstbilgi denetimindeki öğeleri soldan sağa sırasını alır.|
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Taşma düğmesini sınırlayıcı dikdörtgenini için geçerli üst denetimi alır.|
|[CHeaderCtrl::HitTest](#hittest)|Hangi üstbilgi öğesi varsa, belirli bir noktada bulunduğunu belirler.|
|[CHeaderCtrl::InsertItem](#insertitem)|Üstbilgi denetimine yeni bir öğe ekler.|
|[CHeaderCtrl::Layout](#layout)|Boyutunu ve belirli bir dikdörtgen içindeki bir üst bilgi denetiminin konumunu alır.|
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Üstbilgi denetimi, sırayla göre bir öğe için dizin değerini alır.|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Üstbilgi denetimindeki bir bit eşlem kenar genişliğini belirler.|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Bir değişiklik filtre öznitelikleri yerinde geçen süreyi deftere arasındaki zaman aşımı aralığı ayarlar bir `HDN_FILTERCHANGE` bildirim.|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Geçerli başlığı denetiminde belirtilen üst öğesine odak noktası ayarlar.|
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Değişiklikleri el ile belirtmek için üstbilgi öğeleri arasındaki ayırıcının sürükleyin ve açılan bir üst öğesi.|
|[CHeaderCtrl::SetImageList](#setimagelist)|Görüntü listesi üst denetime atar.|
|[CHeaderCtrl::SetItem](#setitem)|Üstbilgi denetimindeki belirtilen öğenin öznitelikleri ayarlar.|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Üstbilgi denetimindeki öğeleri soldan sağa sırasını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Üstbilgi denetimi genellikle bir metin veya sayı sütunlarının kümesi üzerinde konumlandırılmış bir penceredir. Her sütun için bir başlık içerir ve parçalara ayrılabilir. Kullanıcı, her bir sütunun genişliğini ayarlamak için bölümleri ayrı Bölücü sürükleyebilirsiniz. Üstbilgi denetimi bir çizim için bkz [üstbilgi denetimleri](/windows/desktop/Controls/header-controls).

Bu denetimi (ve bu nedenle `CHeaderCtrl` sınıfı) ve üzeri, Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.

Windows 95/Internet Explorer 4.0 ortak denetimler için eklenen işlevler aşağıdakileri içerir:

- Üstbilgi öğesi özel sıralaması.

- Üstbilgi öğesi sürükleyip bırakın, üst öğelerinin yeniden sıralanmasını için. HDS_DRAGDROP stili oluşturduğunuzda kullanmak `CHeaderCtrl` nesne.

- Üst bilgi sütun metin sütunları yeniden boyutlandırma sırasında sürekli olarak görüntülenebilir. Oluşturduğunuz HDS_FULLDRAG stili kullanmak bir `CHeaderCtrl` nesne.

- İşaretçiyi üzerine gelindiğinde, üst öğe vurgular üstbilgi sıcak Takibi. Oluşturduğunuz HDS_HOTTRACK stili kullanmak `CHeaderCtrl` nesne.

- Görüntü listesi desteği. Üstbilgi öğeleri depolanan görüntüleri içerebilir bir `CImageList` nesne veya metin.

Kullanma hakkında daha fazla bilgi için `CHeaderCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CHeaderCtrl](../../mfc/using-cheaderctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="cheaderctrl"></a>  CHeaderCtrl::CHeaderCtrl

Oluşturur bir `CHeaderCtrl` nesne.

```
CHeaderCtrl();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

##  <a name="clearallfilters"></a>  CHeaderCtrl::ClearAllFilters

Üstbilgi denetimi için tüm filtreleri kaldırır.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Win32 iletisinin davranışı uygulayan [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter) -1, Windows SDK'yı açıklandığı bir sütun değerine sahip.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

##  <a name="clearfilter"></a>  CHeaderCtrl::ClearFilter

Üstbilgi denetimi için filtre temizler.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Parametreler

*nColumn*<br/>
Temizlemek için filtre uygulayan gösteren sütun değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Win32 iletisinin davranışı uygulayan [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

##  <a name="create"></a>  CHeaderCtrl::Create

Üstbilgi denetimi oluşturur ve ona bağlanan bir `CHeaderCtrl` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Üst bilgi denetiminin stilini belirtir. Üstbilgi denetim stilleri açıklaması için bkz: [üstbilgi denetim stilleri](/windows/desktop/Controls/header-control-styles) Windows SDK.

*Rect*<br/>
Üst bilgi denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı.

*pParentWnd*<br/>
Üst bilgi denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.

*nID*<br/>
Üst bilgi denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CHeaderCtrl` iki adımda nesne. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, üstbilgi denetimi oluşturur ve ona ekler `CHeaderCtrl` nesne.

Üstbilgi denetim stilleri ek olarak, aşağıdaki ortak denetim stilleri nasıl üstbilgi denetimi yerleştirir ve kendisini yeniden boyutlandırır belirlemek için kullanabilirsiniz (bkz [ortak denetim stilleri](/windows/desktop/Controls/common-control-styles) daha fazla bilgi için):

- CCS_BOTTOM, kendi ana pencerenin istemci alanının altındaki yerleştirmek denetim neden olur ve pencerenin genişliğini genişliğini üst ile aynı olacak şekilde ayarlar.

- CCS_NODIVIDER engeller iki piksel vurgulayın denetimin üstünde çizilmiş.

- CCS_NOMOVEY denetimi yeniden boyutlandırın ve kendisini yatay, ancak değil dikey WM_SIZE iletiye yanıt olarak taşımak neden olur. Bu stil CCS_NORESIZE stili kullanıldığında geçerli değildir. Üstbilgi denetimleriyle, varsayılan olarak bu stil sahiptir.

- CCS_NOPARENTALIGN denetimi üst veya ana pencerenin otomatik olarak taşınmasını engeller. Bunun yerine, denetimin içindeki değişiklikleri rağmen üst pencere konumuna üst pencere boyutuna tutar. CCS_TOP veya CCS_BOTTOM stili de kullanılıyorsa yüksekliği varsayılan olarak ayarlanır, ancak konumu ve genişlik değişmeden kalır.

- CCS_NORESIZE denetimin, varsayılan genişlik ve yükseklik ilk boyutu veya yeni bir boyut ayarlarken kullanmasını önler. Bunun yerine, denetimin genişliği ve yüksekliği istek oluşturma veya boyutlandırma için belirtilen kullanır.

- CCS_TOP, kendi ana pencerenin istemci alanının üstünde konumlandırmak denetim neden olur ve pencerenin genişliğini genişliğini üst ile aynı olacak şekilde ayarlar.

Aşağıdaki pencere stilleri bir üstbilgi denetimine uygulayabilirsiniz (bkz [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) daha fazla bilgi için):

- WS_CHILD bir alt pencere oluşturur. WS_POPUP stiliyle kullanılamaz.

- Ws_vısıble başlangıçta görünen bir pencere oluşturur.

- Ws_dısabled başlangıçta devre dışı olan bir pencere oluşturur.

- WS_GROUP hangi kullanıcının bir denetimden yanındaki ok tuşlarıyla taşıyabilirsiniz Denetim grubunun ilk denetimi belirtir. İlk kontrolden sonra aynı gruba WS_GROUP stiliyle tanımlanan tüm denetimler. WS_GROUP stili sonraki denetim stili grubun sona erer ve (sonraki başladığı diğer bir deyişle, bir grubun bittiği) sonraki grubu başlatır.

- WS_TABSTOP birini belirtir tüm denetimleri yoluyla kullanıcının TAB tuşunu kullanarak taşıyabilirsiniz. Sekme tuşunu kullanıcı WS_TABSTOP stili tarafından belirtilen sonraki denetime gider.

Genişletilmiş windows stilleri ile denetiminizi kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine `Create`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

##  <a name="createex"></a>  CHeaderCtrl::CreateEx

Bir denetimi (alt pencere) oluşturur ve bunu `CHeaderCtrl` nesne.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK.

*dwStyle*<br/>
Üst bilgi denetiminin stili. Üstbilgi denetim stilleri açıklaması için bkz: [üstbilgi denetim stilleri](/windows/desktop/Controls/header-control-styles) Windows SDK. Bkz: [Oluştur](#create) ek stilleri listesi.

*Rect*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.

*pParentWnd*<br/>
Denetimin ana penceresine bir işaretçi.

*nID*<br/>
Denetimin alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `CreateEx` yerine `Create` Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.

##  <a name="createdragimage"></a>  CHeaderCtrl::CreateDragImage

Üstbilgi denetimi içinde bir öğenin resminin saydam bir sürümü oluşturur.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Üstbilgi denetimindeki öğenin sıfır tabanlı dizini. Bu öğeye atanan görüntü saydam görüntü temelini oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesne başarılı; Aksi takdirde NULL. Döndürülen listeden tek bir görüntü içerir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_CREATEDRAGIMAGE](/windows/desktop/Controls/hdm-createdragimage)Windows SDK içinde açıklandığı gibi. Üstbilgi öğesi sürükle ve bırak desteği sunulur.

`CImageList` Nesne döndürülen ukazatel ukazuje geçici bir nesne ve sonraki boşta kalma süresi işlenmesinde silinir.

##  <a name="deleteitem"></a>  CHeaderCtrl::DeleteItem

Bir üst bilgi denetiminden bir öğeyi siler.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Silinecek öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

##  <a name="drawitem"></a>  CHeaderCtrl::DrawItem

Görsel bir özelliği bir özelleştirilmiş çizimli üstbilgi denetim değişiklikleri, framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Bir işaretçi bir [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) boyanacak öğesini açıklayan yapısı.

### <a name="remarks"></a>Açıklamalar

`itemAction` Üyesi `DRAWITEMSTRUCT` gerçekleştirilecek çizim eylemi yapısını tanımlar.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Sahip çizim için çizim uygulamak için bu üye işlevi geçersiz kılma `CHeaderCtrl` nesne.

Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* önce bu üye işlevi sonlandırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

##  <a name="editfilter"></a>  CHeaderCtrl::EditFilter

Üstbilgi denetimi belirtilen filtreyi düzenlemek başlar.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Parametreler

*nColumn*<br/>
Düzenlemek için sütun.

*bDiscardChanges*<br/>
Kullanıcı filtresi düzenleme sürecinde, kullanıcının ne yapılacağını belirten bir değeri düzenleme değişiklikleri zaman [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter) ileti gönderilir.

Belirtin, kullanıcı tarafından ya da yanlış kullanıcı tarafından yapılan değişiklikleri kabul etmek için yaptığınız değişiklikleri atmak için TRUE.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Win32 iletisinin davranışı uygulayan [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

##  <a name="getbitmapmargin"></a>  CHeaderCtrl::GetBitmapMargin

Üstbilgi denetimindeki bir bit eşlem kenar genişliğini alır.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem kenar boşluğunu piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_GETBITMAPMARGIN](/windows/desktop/Controls/hdm-getbitmapmargin)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

##  <a name="getfocuseditem"></a>  CHeaderCtrl::GetFocusedItem

Geçerli üst bilgi denetimi odağa sahip öğenin dizinini alır.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Odaklanmış üstbilgi öğesi sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [HDM_GETFOCUSEDITEM](/windows/desktop/Controls/hdm-getfocuseditem) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `SetFocusedItem` ve `GetFocusedItem` yöntemleri. Önceki kod bölümünde beş sütun başlığı denetimi oluşturduk. Ancak, böylece sütunu görünür değil. bir sütun ayırıcı sürükleyebilirsiniz. Aşağıdaki örnek, ayarlar ve ardından son sütun başlığının odak öğe olarak doğrular.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="getimagelist"></a>  CHeaderCtrl::GetImageList

Üstbilgi denetimindeki çizim üstbilgi öğeleri için kullanılan bir görüntü listesi tanıtıcısını alır.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_GETIMAGELIST](/windows/desktop/Controls/hdm-getimagelist)Windows SDK içinde açıklandığı gibi. `CImageList` Nesne döndürülen ukazatel ukazuje geçici bir nesne ve sonraki boşta kalma süresi işlenmesinde silinir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

##  <a name="getitem"></a>  CHeaderCtrl::GetItem

Üstbilgi denetim öğesi hakkındaki bilgileri alır.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Alınacak öğenin sıfır tabanlı dizinini belirtir.

*pHeaderItem*<br/>
İşaretçi bir [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) yeni öğe alan yapısı. Bu yapı kullanılır `InsertItem` ve `SetItem` üye işlevleri. Bayrakları kümesinde `mask` öğenin karşılık gelen öğelerle değerleri düzgün bir şekilde dönüş doldurulduğundan olduğundan emin olun. Varsa `mask` öğesi sıfır olarak ayarlandığında, bir yapı öğeleri değerler anlamsız.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

##  <a name="getitemcount"></a>  CHeaderCtrl::GetItemCount

Üstbilgi denetimindeki öğeleri sayısını alır.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üstbilgi denetim öğeleri başarılı olursa sayısı; Aksi takdirde - 1.

### <a name="example"></a>Örnek

  Örneğin bakın [CHeaderCtrl::DeleteItem](#deleteitem).

##  <a name="getitemdropdownrect"></a>  CHeaderCtrl::GetItemDropDownRect

Geçerli üstbilgi denetimindeki üstbilgi öğesi için açılan düğmeyi sınırlayıcı dikdörtgenini alır.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iItem*|[in] Stilini HDF_SPLITBUTTON olduğu başlık öğesinin sıfır tabanlı dizini. Daha fazla bilgi için `fmt` üyesi [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) yapısı.|
|*lpRect*|[out] İşaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı sınırlayıcı bir dikdörtgen bilgileri almak için.|

### <a name="return-value"></a>Dönüş Değeri

Bu işlev başarılı ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [HDM_GETITEMDROPDOWNRECT](/windows/desktop/Controls/hdm-getitemdropdownrect) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `GetItemDropDownRect` yöntemi. Önceki kod bölümünde beş sütun başlığı denetimi oluşturduk. Aşağıdaki kod örneği için üst bilgi açılan düğmeyi ayrılmış ilk sütununda konum etrafındaki 3B bir dikdörtgen çizer.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

##  <a name="getitemrect"></a>  CHeaderCtrl::GetItemRect

Üstbilgi denetimindeki belirli bir öğe için dikdörtgen alır.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Üstbilgi denetim öğesi sıfır tabanlı dizini.

*lpRect*<br/>
Adresine bir işaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) sınırlayıcı dikdörtgeni bilgileri alan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Win32 iletisinin davranışı uygulayan [HDM_GETITEMRECT](/windows/desktop/Controls/hdm-getitemrect)Windows SDK içinde açıklandığı gibi.

##  <a name="getorderarray"></a>  CHeaderCtrl::GetOrderArray

Üstbilgi denetimindeki öğeleri soldan sağa sırasını alır.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Parametreler

*piArray*<br/>
Üstbilgi denetimindeki soldan sağa doğru göründükleri sırada öğelerin dizini değerini alan arabellek adresi için bir işaretçi.

*iCount*<br/>
Üstbilgi denetimine öğe sayısı. Negatif olmayan olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_GETORDERARRAY](/windows/desktop/Controls/hdm-getorderarray)Windows SDK içinde açıklandığı gibi. Üstbilgi öğesi sıralama desteği sunulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

##  <a name="getoverflowrect"></a>  CHeaderCtrl::GetOverflowRect

Geçerli üst bilgi denetiminin taşma düğmesini sınırlayıcı dikdörtgenini alır.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpRect*|[out] İşaretçi bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) sınırlayıcı dikdörtgeni bilgileri alan yapısı.|

### <a name="return-value"></a>Dönüş Değeri

Bu işlev başarılı ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Üstbilgi denetimi aynı anda görüntülenebilecek olandan daha fazla öğe içeriyorsa, Denetim, kaydırılabilen taşma düğmesini görünür olmayan öğeleri görüntüleyebilirsiniz. Üstbilgi denetimi taşma düğmesini görüntülenecek HDS_OVERFLOW ve HDF_SPLITBUTTON stilleri olması gerekir. Dikdörtgen taşma düğmesini alır ve yalnızca taşma düğmesini görüntülendiğinde bulunmaktadır. Daha fazla bilgi için [üstbilgi denetim stilleri](/windows/desktop/Controls/header-control-styles).

Bu yöntem gönderir [HDM_GETOVERFLOWRECT](/windows/desktop/Controls/hdm-getoverflowrect) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `GetOverflowRect` yöntemi. Önceki kod bölümünde beş sütun başlığı denetimi oluşturduk. Ancak, böylece sütunu görünür değil. bir sütun ayırıcı sürükleyebilirsiniz. Bazı sütunlar görünür değilse, üstbilgi denetimi taşma düğmesini çizer. Aşağıdaki kod örneği, taşma düğmesini konum etrafındaki 3B bir dikdörtgen çizer.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

##  <a name="hittest"></a>  CHeaderCtrl::HitTest

Hangi üstbilgi öğesi varsa, belirli bir noktada bulunduğunu belirler.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*phdhti*|[out içinde] İşaretçi bir [HDHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_hd_hittestinfo) test etmek için noktasını belirtir ve test sonuçlarını alan yapısı.|

### <a name="return-value"></a>Dönüş Değeri

Üstbilgi öğesi, varsa, belirli bir konumda sıfır tabanlı dizini; Aksi durumda, -1.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [HDM_HITTEST](/windows/desktop/Controls/hdm-hittest) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `HitTest` yöntemi. Bu kod örneği önceki bölümünde, beş sütun başlığı denetimi oluşturduk. Ancak, böylece sütunu görünür değil. bir sütun ayırıcı sürükleyebilirsiniz. Görünür durumdaysa bu örnek sütun dizini raporları ve sütun görünmüyorsa -1.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

##  <a name="insertitem"></a>  CHeaderCtrl::InsertItem

Belirtilen dizindeki bir üstbilgi denetimine yeni bir öğe ekler.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Eklenecek öğenin sıfır tabanlı dizini. Değer sıfır ise öğe üstbilgi denetimi başında eklenir. Değer en yüksek değerden büyük olduğunda, öğe üstbilgi denetimi sonunda eklenir.

*phdi*<br/>
İşaretçi bir [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) eklenecek öğe hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni öğenin dizini; Aksi takdirde - 1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

##  <a name="layout"></a>  CHeaderCtrl::Layout

Boyutunu ve belirli bir dikdörtgen içindeki bir üst bilgi denetiminin konumunu alır.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Parametreler

*pHeaderLayout*<br/>
İşaretçi bir [HDLAYOUT](/windows/desktop/api/commctrl/ns-commctrl-_hd_layout) yapısı, üstbilgi denetimi konumunu ve boyutunu ayarlamak için kullanılan bilgileri içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirtilen dikdörtgen kaplaması için yeni bir üstbilgi denetimi için uygun boyutları belirlemek için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

##  <a name="ordertoindex"></a>  CHeaderCtrl::OrderToIndex

Üstbilgi denetimi, sırayla göre bir öğe için dizin değerini alır.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Parametreler

*nOrder*<br/>
Soldan sağa doğru üstbilgi denetimindeki öğeyi göründüğü sıfır tabanlı sıra.

### <a name="return-value"></a>Dönüş Değeri

Üstbilgi denetimi, sırayla göre öğenin dizini. Dizin soldan sağa, 0 ile başlayan sayar.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 makrosu davranışını uygulayan [HDM_ORDERTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb775355)Windows SDK içinde açıklandığı gibi. Üstbilgi öğesi sıralama desteği sunulur.

##  <a name="setbitmapmargin"></a>  CHeaderCtrl::SetBitmapMargin

Üstbilgi denetimindeki bir bit eşlem kenar genişliğini belirler.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Belirtilen mevcut bir üstbilgi denetimi içinde bir bit eşlem çevreleyen kenar boşluğunun piksel cinsinden genişlik.

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem kenar boşluğunu piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_SETBITMAPMARGIN](/windows/desktop/Controls/hdm-setbitmapmargin)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

##  <a name="setfilterchangetimeout"></a>  CHeaderCtrl::SetFilterChangeTimeout

Bir değişiklik filtre öznitelikleri yerinde geçen süreyi deftere arasındaki zaman aşımı aralığı ayarlar bir [HDN_FILTERCHANGE](/windows/desktop/Controls/hdn-filterchange) bildirim.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Milisaniye cinsinden zaman aşımı değeri.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen filtre denetimi dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_SETFILTERCHANGETIMEOUT](/windows/desktop/Controls/hdm-setfilterchangetimeout)Windows SDK içinde açıklandığı gibi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

##  <a name="setfocuseditem"></a>  CHeaderCtrl::SetFocusedItem

Geçerli başlığı denetiminde belirtilen üst öğesine odak noktası ayarlar.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iItem*|[in] Başlık öğesinin sıfır tabanlı dizini.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [HDM_SETFOCUSEDITEM](/windows/desktop/Controls/hdm-setfocuseditem) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_headerCtrl`, yani geçerli üstbilgi denetimi erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneğinde `SetFocusedItem` ve `GetFocusedItem` yöntemleri. Önceki kod bölümünde beş sütun başlığı denetimi oluşturduk. Ancak, böylece sütunu görünür değil. bir sütun ayırıcı sürükleyebilirsiniz. Aşağıdaki örnek, ayarlar ve ardından son sütun başlığının odak öğe olarak doğrular.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="sethotdivider"></a>  CHeaderCtrl::SetHotDivider

Değişiklikleri el ile belirtmek için üstbilgi öğeleri arasındaki ayırıcının sürükleyin ve açılan bir üst öğesi.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
İşaretçi konumu. Üstbilgi denetimi işaretçisi konumuna göre uygun ayırıcı vurgular.

*nIndex*<br/>
Vurgulanan ayırıcı dizini.

### <a name="return-value"></a>Dönüş Değeri

Vurgulanan ayırıcı dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_SETHOTDIVIDER](/windows/desktop/Controls/hdm-sethotdivider)Windows SDK içinde açıklandığı gibi. Üstbilgi öğesi sürükle ve bırak desteği sunulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

##  <a name="setimagelist"></a>  CHeaderCtrl::SetImageList

Görüntü listesi üst denetime atar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Bir işaretçi bir `CImageList` üstbilgi denetimine atanan görüntü listesi içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [Cımagelist](../../mfc/reference/cimagelist-class.md) üstbilgi denetimine daha önce atanan nesne.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [HDM_SETIMAGELIST](/windows/desktop/Controls/hdm-setimagelist)Windows SDK içinde açıklandığı gibi. `CImageList` Nesne döndürülen ukazatel ukazuje geçici bir nesne ve sonraki boşta kalma süresi işlenmesinde silinir.

### <a name="example"></a>Örnek

  Örneğin bakın [CHeaderCtrl::GetImageList](#getimagelist).

##  <a name="setitem"></a>  CHeaderCtrl::SetItem

Üstbilgi denetimindeki belirtilen öğenin öznitelikleri ayarlar.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Yönetilebilmesini öğenin sıfır tabanlı dizini.

*pHeaderItem*<br/>
İşaretçi bir [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) yeni öğe hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

  Örneğin bakın [CHeaderCtrl::GetItem](#getitem).

##  <a name="setorderarray"></a>  CHeaderCtrl::SetOrderArray

Üstbilgi denetimindeki öğeleri soldan sağa sırasını ayarlar.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Parametreler

*iCount*<br/>
Üstbilgi denetimine öğe sayısı.

*piArray*<br/>
Üstbilgi denetimindeki soldan sağa doğru göründükleri sırada öğelerin dizini değerini alan arabellek adresi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 makrosu davranışını uygulayan [HDM_SETORDERARRAY](/windows/desktop/Controls/hdm-setorderarray)Windows SDK içinde açıklandığı gibi. Üstbilgi öğesi sıralama desteği sunulur.

### <a name="example"></a>Örnek

  Örneğin bakın [CHeaderCtrl::GetOrderArray](#getorderarray).

## <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl Sınıfı](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList Sınıfı](../../mfc/reference/cimagelist-class.md)
