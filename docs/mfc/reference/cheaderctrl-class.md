---
title: CHeaderCtrl Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 6b5088526ad2c1f94fdc95ec3b84ab7cf64b59e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366864"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl Sınıfı

Windows ortak üstbilgi denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Bir `CHeaderCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFiltreler](#clearallfilters)|Üstbilgi denetimi için tüm filtreleri temizler.|
|[CHeaderCtrl::ClearFilter](#clearfilter)|Üstbilgi denetimi için filtreyi temizler.|
|[CHeaderCtrl::Oluştur](#create)|Üstbilgi denetimi oluşturur ve nesneye `CHeaderCtrl` bağlar.|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Üstbilgi denetiminde öğenin görüntüsünün saydam bir sürümünü oluşturur.|
|[CHeaderCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir üstbilgi denetimi oluşturur `CListCtrl` ve bir nesneye bağlar.|
|[CHeaderCtrl::DeleteItem](#deleteitem)|Bir öğeyi üstbilgi denetiminden siler.|
|[CHeaderCtrl::DrawItem](#drawitem)|Üstbilgi denetiminin belirtilen öğesini çizer.|
|[CHeaderCtrl::EditFilter](#editfilter)|Üstbilgi denetiminin belirtilen filtresini düzenlemeye başlar.|
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Üstbilgi denetiminde bir bit eşanlığı kenar boşluğunun genişliğini alır.|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Odak noktası olan geçerli üstbilgi denetiminde öğenin tanımlayıcısını alır.|
|[CHeaderCtrl::GetImageList](#getimagelist)|Üstbilgi denetiminde üstbilgi öğeleri çizmek için kullanılan bir resim listesinin tutamacını alır.|
|[CHeaderCtrl::GetItem](#getitem)|Üstbilgi denetimindeki bir öğe yle ilgili bilgileri alır.|
|[CHeaderCtrl::GetItemCount](#getitemcount)|Üstbilgi denetimindeki öğelerin sayısını alır.|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Üstbilgi denetiminde belirtilen açılır açma düğmesinin sınırlayıcı dikdörtgen bilgilerini alır.|
|[CHeaderCtrl::GetItemRect](#getitemrect)|Üstbilgi denetiminde belirli bir öğe için sınırlayıcı dikdörtgeni alır.|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Üstbilgi denetimindeki öğelerin soldan sağa sırasını alır.|
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Geçerli üstbilgi denetimi için taşma düğmesinin sınırlayıcı dikdörtgenini alır.|
|[CHeaderCtrl::HitTest](#hittest)|Varsa hangi üstbilgi öğesinin belirli bir noktada bulunduğunu belirler.|
|[CHeaderCtrl::InsertItem](#insertitem)|Üstbilgi denetimine yeni bir öğe ekler.|
|[CHeaderCtrl::Düzen](#layout)|Belirli bir dikdörtgen içinde üstbilgi denetiminin boyutunu ve konumunu alır.|
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Üstbilgi denetimindeki siparişini temel alan bir maddenin dizin değerini alır.|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Üstbilgi denetiminde bit eşlemi kenar boşluğunun genişliğini ayarlar.|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Filtre özniteliklerinde değişikliğin gerçekleştiği saat ile bildirimin `HDN_FILTERCHANGE` deftere nakli arasındaki zaman aralığını ayarlar.|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Odak noktasını geçerli üstbilgi denetiminde belirli bir üstbilgi öğesine ayarlar.|
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Üstbilgi öğesinin el ile sürükle ve düşüşünü belirtmek için üstbilgi öğeleri arasındaki bölücüyü değiştirir.|
|[CHeaderCtrl::SetImageList](#setimagelist)|Üstbilgi denetimine bir resim listesi atar.|
|[CHeaderCtrl::SetItem](#setitem)|Üstbilgi denetiminde belirtilen öğenin özniteliklerini ayarlar.|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Üstbilgi denetiminde öğelerin soldan sağa sırasını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Üstbilgi denetimi, genellikle metin veya sayı sütunlarının üzerine konumlandırılmış bir penceredir. Her sütun için bir başlık içerir ve parçalara ayrılabilir. Kullanıcı, her sütunun genişliğini ayarlamak için parçaları ayıran bölücüleri sürükleyebilir. Üstbilgi denetiminin bir örneği için [bkz.](/windows/win32/Controls/header-controls)

Bu denetim (ve `CHeaderCtrl` bu nedenle sınıf) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Windows 95/Internet Explorer 4.0 ortak denetimleri için eklenen işlevler şunlardır:

- Üstbilgi öğesi özel sıralama.

- Üstbilgi öğesi sürükle ve bırak, üstbilgi öğelerinin yeniden sıralanması için. Nesneyi oluştururken HDS_DRAGDROP `CHeaderCtrl` stilini kullanın.

- Üstbilgi sütun metni sütun yeniden boyutlandırma sırasında sürekli olarak görüntülenebilir. Nesne `CHeaderCtrl` oluştururken HDS_FULLDRAG stilini kullanın.

- Üstbilgi sıcak izleme, işaretçi üzerinde gezinirken üstbilgi öğesini vurgular. Nesneyi oluştururken HDS_HOTTRACK `CHeaderCtrl` stilini kullanın.

- Resim listesi desteği. Üstbilgi öğeleri, bir `CImageList` nesne veya metinde depolanan görüntüleri içerebilir.

Kullanma `CHeaderCtrl`hakkında daha fazla bilgi için, [Bkz. Denetimler](../../mfc/controls-mfc.md) ve [CHeaderCtrl kullanma.](../../mfc/using-cheaderctrl.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl

Bir `CHeaderCtrl` nesne inşa eder.

```
CHeaderCtrl();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

## <a name="cheaderctrlclearallfilters"></a><a name="clearallfilters"></a>CHeaderCtrl::ClearAllFiltreler

Üstbilgi denetimi için tüm filtreleri temizler.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklandığı gibi -1 sütun değerine sahip Win32 [iletiHDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter) davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

## <a name="cheaderctrlclearfilter"></a><a name="clearfilter"></a>CHeaderCtrl::ClearFilter

Üstbilgi denetimi için filtreyi temizler.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Parametreler

*nSütun*<br/>
Hangi filtrenin temizlendiğini gösteren sütun değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

## <a name="cheaderctrlcreate"></a><a name="create"></a>CHeaderCtrl::Oluştur

Üstbilgi denetimi oluşturur ve nesneye `CHeaderCtrl` bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Üstbilgi denetiminin stilini belirtir. Üstbilgi denetim stillerinin açıklaması için Windows SDK'daki [Üstbilgi Denetim Stilleri'ne](/windows/win32/Controls/header-control-styles) bakın.

*Rect*<br/>
Üstbilgi denetiminin boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı olabilir.

*pParentWnd*<br/>
Üstbilgi denetiminin üstbilgi denetiminin üst `CDialog`penceresini belirtir, genellikle bir . NULL olmamalıdır.

*Nıd*<br/>
Üstbilgi denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olduysa sıfırsız; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CHeaderCtrl` iki adımda inşa ee. İlk olarak, oluşturucuyu `Create`çağırın ve ardından üstbilgi denetimini `CHeaderCtrl` oluşturan ve nesneye iliştiren , çağırın.

Üstbilgi denetim stillerine ek olarak, üstbilginin konumları nasıl konumlandırdığını ve kendisini nasıl yeniden boyutlandırdığını belirlemek için aşağıdaki ortak denetim stillerini kullanabilirsiniz (daha fazla bilgi için [Ortak Denetim Stilleri'ne](/windows/win32/Controls/common-control-styles) bakın):

- CCS_BOTTOM Denetimin kendisini üst pencerenin istemci alanının altında konumlandırmasına neden olur ve genişliği üst pencerenin genişliğiyle aynı olacak şekilde ayarlar.

- CCS_NODIVIDER Denetimin üst kısmında iki pikselvurgunun çizilmesiengellenir.

- CCS_NOMOVEY Denetimin WM_SIZE bir iletiye yanıt olarak kendisini yatay olarak değil, dikey olarak yeniden boyutlandırmasına ve taşımasına neden olur. CCS_NORESIZE stili kullanılırsa, bu stil geçerli değildir. Üstbilgi denetimleri varsayılan olarak bu stili gösterir.

- CCS_NOPARENTALIGN Denetimin ana pencerenin üst veya alt bölümüne otomatik olarak taşınmasını önler. Bunun yerine, denetim üst pencerenin boyutundaki değişikliklere rağmen üst pencereiçindeki konumunu korur. CCS_TOP veya CCS_BOTTOM stili de kullanılırsa, yükseklik varsayılana ayarlanır, ancak konum ve genişlik değişmeden kalır.

- CCS_NORESIZE İlk boyutunu veya yeni boyutunu ayarlarken denetimin varsayılan genişliği ve yüksekliği kullanmasını engeller. Denetim bunun yerine, oluşturma veya boyutlandırma isteğinde belirtilen genişlik ve yüksekliği kullanır.

- CCS_TOP Denetimin kendisini üst pencerenin istemci alanının en üstünde konumlandırmasına neden olur ve genişliği üst pencerenin genişliğiyle aynı olacak şekilde ayarlar.

Üstbilgi denetimine aşağıdaki pencere stillerini de uygulayabilirsiniz (daha fazla bilgi için [Pencere Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#window-styles) bakın):

- WS_CHILD Bir alt pencere oluşturur. WS_POPUP stili ile kullanılamaz.

- WS_VISIBLE Başlangıçta görünür bir pencere oluşturur.

- WS_DISABLED Başlangıçta devre dışı bırakılmış bir pencere oluşturur.

- WS_GROUP Kullanıcının ok tuşları yla bir denetimden diğerine geçebileceği bir denetim grubunun ilk denetimini belirtir. İlk denetimden sonra WS_GROUP stili ile tanımlanan tüm denetimler aynı gruba aittir. stil WS_GROUP sonraki denetim stil grubunu sona erdirer ve bir sonraki grubu başlatır (diğer bir grup bir sonrakinin başladığı yerde biter).

- WS_TABSTOP Kullanıcının TAB tuşunu kullanarak hareket edebileceği herhangi bir sayıdadenetimden birini belirtir. TAB tuşu kullanıcıyı WS_TABSTOP stili tarafından belirtilen bir sonraki denetime taşır.

Genişletilmiş windows stillerini denetiminiz ile kullanmak istiyorsanız, `Create`'' yerine [CreateEx'i](#createex) arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

## <a name="cheaderctrlcreateex"></a><a name="createex"></a>CHeaderCtrl::CreateEx

Denetim (alt pencere) oluşturur ve nesneyle `CHeaderCtrl` ilişkilendirin.

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
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
Üstbilgi denetiminin stili. Üstbilgi denetim stillerinin açıklaması için Windows SDK'daki [Üstbilgi Denetim Stilleri'ne](/windows/win32/Controls/header-control-styles) bakın. Ek stillerin listesi için [oluştur'a](#create) bakın.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş `Create` stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak yerine kullanın.

## <a name="cheaderctrlcreatedragimage"></a><a name="createdragimage"></a>CHeaderCtrl::CreateDragImage

Üstbilgi denetiminde öğenin görüntüsünün saydam bir sürümünü oluşturur.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Üstbilgi denetiminde öğenin sıfır tabanlı dizin. Bu öğeye atanan görüntü saydam görüntünün temelini oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi; aksi takdirde NULL. Döndürülen listede yalnızca bir resim içerir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_CREATEDRAGIMAGE](/windows/win32/Controls/hdm-createdragimage)davranışını uygular. Üstbilgi öğesi sürükle ve bırak'ı desteklemek için sağlanır.

Döndürülen işaretçinin işaret ettiği `CImageList` nesne geçici bir nesnedir ve bir sonraki boşta zaman işleminde silinir.

## <a name="cheaderctrldeleteitem"></a><a name="deleteitem"></a>CHeaderCtrl::DeleteItem

Bir öğeyi üstbilgi denetiminden siler.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Silmek için öğenin sıfır tabanlı dizin belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

## <a name="cheaderctrldrawitem"></a><a name="drawitem"></a>CHeaderCtrl::DrawItem

Bir sahibi-beraberlik üstbilgi denetiminin görsel bir yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Boyanacak öğeyi açıklayan [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının `itemAction` `DRAWITEMSTRUCT` üyesi, gerçekleştirilecek çizim eylemini tanımlar.

Varsayılan olarak, bu üye işlev hiçbir şey yapmaz. Bir sahip çizim `CHeaderCtrl` nesnesi için çizim uygulamak için bu üye işlevi geçersiz kılın.

Uygulama, bu üye işlev sona erdirilmeden önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

## <a name="cheaderctrleditfilter"></a><a name="editfilter"></a>CHeaderCtrl::EditFilter

Üstbilgi denetiminin belirtilen filtresini atmaya başlar.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Parametreler

*nSütun*<br/>
Dolanacak sütun.

*bDiscardDeğişiklikler*<br/>
[Kullanıcı, HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter) iletisi gönderildiğinde filtreyi düzenleme sürecindeyse, kullanıcının düzenleme değişikliklerinin nasıl işleyeceğini belirten bir değer.

Kullanıcı tarafından yapılan değişiklikleri atmak için TRUE veya kullanıcı tarafından yapılan değişiklikleri kabul etmek için FALSE'u belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

## <a name="cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin

Üstbilgi denetiminde bir bit eşanlığı kenar boşluğunun genişliğini alır.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksellerde bit eşkenar boşluğugenişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_GETBITMAPMARGIN](/windows/win32/Controls/hdm-getbitmapmargin)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

## <a name="cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem

Geçerli üstbilgi denetiminde odağı olan öğenin dizinini alır.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Odak noktası olan üstbilgi öğesinin sıfır tabanlı dizin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl`geçerli üstbilgi denetimine erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği ve `SetFocusedItem` `GetFocusedItem` yöntemleri gösterir. Kodun önceki bir bölümünde, beş sütunlu bir üstbilgi denetimi oluşturduk. Ancak, sütun ayırıcısını sütunun görünmemesi için sürükleyebilirsiniz. Aşağıdaki örnek, son sütun üstbilgisini odak öğesi olarak ayarlar ve onaylar.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlgetimagelist"></a><a name="getimagelist"></a>CHeaderCtrl::GetImageList

Üstbilgi denetiminde üstbilgi öğeleri çizmek için kullanılan bir resim listesinin tutamacını alır.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_GETIMAGELIST](/windows/win32/Controls/hdm-getimagelist)davranışını uygular. Döndürülen işaretçinin işaret ettiği `CImageList` nesne geçici bir nesnedir ve bir sonraki boşta zaman işleminde silinir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

## <a name="cheaderctrlgetitem"></a><a name="getitem"></a>CHeaderCtrl::GetItem

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
Yeni öğeyi alan bir [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısıiçin işaretçi. Bu yapı `InsertItem` ve `SetItem` üye işlevler ile kullanılır. `mask` Öğeye ayarlanan bayraklar, döndükten sonra ilgili öğelerdeki değerlerin düzgün şekilde doldurulmasını sağlar. `mask` Öğe sıfıra ayarlanırsa, diğer yapı öğelerindeki değerler anlamsızdır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

## <a name="cheaderctrlgetitemcount"></a><a name="getitemcount"></a>CHeaderCtrl::GetItemCount

Üstbilgi denetimindeki öğelerin sayısını alır.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa üstbilgi denetim öğesi sayısı; aksi takdirde - 1.

### <a name="example"></a>Örnek

  [CHeaderCtrl::DeleteItem](#deleteitem)için örneğe bakın.

## <a name="cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect

Geçerli üstbilgi denetimindeki bir üstbilgi öğesi için açılır açma düğmesinin sınırlayıcı dikdörtgenini alır.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iÖğe*|[içinde] Stili HDF_SPLITBUTTON bir üstbilgi öğesinin sıfır tabanlı dizin. Daha fazla bilgi `fmt` için [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısının üyesine bakın.|
|*Lprect*|[çıkış] Sınırlayıcı dikdörtgen bilgilerini almak için [BIR RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu işlev başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl`geçerli üstbilgi denetimine erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `GetItemDropDownRect` yöntemi gösterir. Kodun önceki bir bölümünde, beş sütunlu bir üstbilgi denetimi oluşturduk. Aşağıdaki kod örneği, üstbilgi açılır düğmesi için ayrılmış ilk sütundaki konumun etrafına 3B dikdörtgen çizer.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

## <a name="cheaderctrlgetitemrect"></a><a name="getitemrect"></a>CHeaderCtrl::GetItemRect

Üstbilgi denetiminde belirli bir öğe için sınırlayıcı dikdörtgeni alır.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Üstbilgi denetim öğesinin sıfır tabanlı dizin.

*Lprect*<br/>
Sınırlayıcı dikdörtgen bilgilerini alan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısının adresine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_GETITEMRECT](/windows/win32/Controls/hdm-getitemrect)davranışını uygular.

## <a name="cheaderctrlgetorderarray"></a><a name="getorderarray"></a>CHeaderCtrl::GetOrderArray

Üstbilgi denetimindeki öğelerin soldan sağa sırasını alır.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Parametreler

*piArray*<br/>
Üstbilgi denetimindeki öğelerin dizin değerlerini soldan sağa doğru görünme sırasına göre alan arabelleğin adresine işaretçi.

*iSay*<br/>
Üstbilgi denetim öğelerinin sayısı. Negatif olmayan olmalı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_GETORDERARRAY](/windows/win32/Controls/hdm-getorderarray)davranışını uygular. Üstbilgi madde siparişini desteklemek için sağlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

## <a name="cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect

Geçerli üstbilgi denetiminin taşma düğmesinin sınırlayıcı dikdörtgenini alır.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Lprect*|[çıkış] Sınırlayıcı dikdörtgen bilgilerini alan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu işlev başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Üstbilgi denetimi aynı anda görüntülenebilen daha fazla öğe içeriyorsa, denetim görünmeyen öğelere kaydırılan bir taşma düğmesi görüntüleyebilir. Üstbilgi denetimi, taşma düğmesini görüntülemek için HDS_OVERFLOW ve HDF_SPLITBUTTON stillerine sahip olmalıdır. Sınırlayan dikdörtgen, taşma düğmesini içine çeker ve yalnızca taşma düğmesi görüntülendiğinde bulunur. Daha fazla bilgi için [bkz.](/windows/win32/Controls/header-control-styles)

Bu yöntem, Windows SDK'da açıklanan [HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl`geçerli üstbilgi denetimine erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `GetOverflowRect` yöntemi gösterir. Kodun önceki bir bölümünde, beş sütunlu bir üstbilgi denetimi oluşturduk. Ancak, sütun ayırıcısını sütunun görünmemesi için sürükleyebilirsiniz. Bazı sütunlar görünmüyorsa, üstbilgi denetimi bir taşma düğmesi çizer. Aşağıdaki kod örneği, taşma düğmesinin konumu etrafında bir 3B dikdörtgen çizer.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

## <a name="cheaderctrlhittest"></a><a name="hittest"></a>CHeaderCtrl::HitTest

Varsa hangi üstbilgi öğesinin belirli bir noktada bulunduğunu belirler.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*phdhti*|[içinde, dışarı] Test etmek için noktayı belirten ve test sonuçlarını alan bir [HDHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-hdhittestinfo) yapısına işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Üstbilgi öğesinin sıfır tabanlı dizini, varsa, belirtilen konumda; aksi takdirde, -1.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [HDM_HITTEST](/windows/win32/Controls/hdm-hittest) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl`geçerli üstbilgi denetimine erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `HitTest` yöntemi gösterir. Bu kod örneğinin önceki bir bölümünde, beş sütunlu bir üstbilgi denetimi oluşturduk. Ancak, sütun ayırıcısını sütunun görünmemesi için sürükleyebilirsiniz. Bu örnek, görünür ise sütundizini ve -1 sütun görünmüyorsa bildirir.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

## <a name="cheaderctrlinsertitem"></a><a name="insertitem"></a>CHeaderCtrl::InsertItem

Belirtilen dizinbir üstbilgi denetimine yeni bir öğe ekler.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Eklenecek öğenin sıfır tabanlı dizin. Değer sıfır ise, öğe üstbilgi denetiminin başına eklenir. Değer maksimum değerden büyükse, öğe üstbilgi denetiminin sonuna eklenir.

*phdi*<br/>
Eklenecek öğe hakkında bilgi içeren bir [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısını işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni öğenin dizini; aksi takdirde - 1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

## <a name="cheaderctrllayout"></a><a name="layout"></a>CHeaderCtrl::Düzen

Belirli bir dikdörtgen içinde üstbilgi denetiminin boyutunu ve konumunu alır.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Parametreler

*pHeaderDüzeni*<br/>
Üstbilgi denetiminin boyutunu ve konumunu ayarlamak için kullanılan bilgileri içeren [bir HDLAYOUT](/windows/win32/api/commctrl/ns-commctrl-hdlayout) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verilen dikdörtgeni işgal etmek olan yeni bir üstbilgi denetimi için uygun boyutları belirlemek için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

## <a name="cheaderctrlordertoindex"></a><a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex

Üstbilgi denetimindeki siparişini temel alan bir maddenin dizin değerini alır.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Parametreler

*nSipariş*<br/>
Öğenin üstbilgi denetiminde soldan sağa doğru görüntülenebilen sıfır tabanlı sıra.

### <a name="return-value"></a>Dönüş Değeri

Üstbilgi denetimindeki sırasına göre maddenin dizini. Dizin soldan sağa doğru, 0 ile başlar.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 makro [HDM_ORDERTOINDEX](/windows/win32/controls/hdm-ordertoindex)davranışını uygular. Üstbilgi madde siparişini desteklemek için sağlanır.

## <a name="cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin

Üstbilgi denetiminde bit eşlemi kenar boşluğunun genişliğini ayarlar.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Parametreler

*Nwidth*<br/>
Varolan bir üstbilgi denetimi içinde bit eşlemi çevreleyen kenar boşluğunun pikselcinsinden belirtilen genişliği.

### <a name="return-value"></a>Dönüş Değeri

Piksellerde bit eşkenar boşluğugenişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_SETBITMAPMARGIN](/windows/win32/Controls/hdm-setbitmapmargin)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

## <a name="cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout

Filtre özniteliklerinde değişikliğin gerçekleştiği saat ile [HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange) bildiriminin gönderilmesi arasındaki zaman aralığını ayarlar.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Zaman kaybı değeri, milisaniye cinsinden.

### <a name="return-value"></a>Dönüş Değeri

Filtre denetiminin dizin değiştiriliyor.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [Win32](/windows/win32/Controls/hdm-setfilterchangetimeout)iletisinin HDM_SETFILTERCHANGETIMEOUT davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

## <a name="cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem

Odak noktasını geçerli üstbilgi denetiminde belirli bir üstbilgi öğesine ayarlar.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*iÖğe*|[içinde] Üstbilgi öğesinin sıfır tabanlı dizin.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl`geçerli üstbilgi denetimine erişmek için kullanılan değişkeni tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği ve `SetFocusedItem` `GetFocusedItem` yöntemleri gösterir. Kodun önceki bir bölümünde, beş sütunlu bir üstbilgi denetimi oluşturduk. Ancak, sütun ayırıcısını sütunun görünmemesi için sürükleyebilirsiniz. Aşağıdaki örnek, son sütun üstbilgisini odak öğesi olarak ayarlar ve onaylar.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlsethotdivider"></a><a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider

Üstbilgi öğesinin el ile sürükle ve düşüşünü belirtmek için üstbilgi öğeleri arasındaki bölücüyü değiştirir.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
İşaretçinin konumu. Üstbilgi denetimi, işaretçinin konumuna göre uygun bölücüyü vurgular.

*Nındex*<br/>
Vurgulanan bölücü dizini.

### <a name="return-value"></a>Dönüş Değeri

Vurgulanan bölücü dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_SETHOTDIVIDER](/windows/win32/Controls/hdm-sethotdivider)davranışını uygular. Üstbilgi öğesi sürükle ve bırak'ı desteklemek için sağlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

## <a name="cheaderctrlsetimagelist"></a><a name="setimagelist"></a>CHeaderCtrl::SetImageList

Üstbilgi denetimine bir resim listesi atar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Üstbilgi denetimine atanacak görüntü listesini içeren bir `CImageList` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Daha önce üstbilgi denetimine atanan [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisinin [HDM_SETIMAGELIST](/windows/win32/Controls/hdm-setimagelist)davranışını uygular. Döndürülen işaretçinin işaret ettiği `CImageList` nesne geçici bir nesnedir ve bir sonraki boşta zaman işleminde silinir.

### <a name="example"></a>Örnek

  [CHeaderCtrl örneğine bakın:GetImageList](#getimagelist).

## <a name="cheaderctrlsetitem"></a><a name="setitem"></a>CHeaderCtrl::SetItem

Üstbilgi denetiminde belirtilen öğenin özniteliklerini ayarlar.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kullanılacak öğenin sıfır tabanlı dizin.

*pHeaderItem*<br/>
Yeni öğe hakkında bilgi içeren bir [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısıiçin işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

  [CHeaderCtrl örneğine bakın:GetItem](#getitem).

## <a name="cheaderctrlsetorderarray"></a><a name="setorderarray"></a>CHeaderCtrl::SetOrderArray

Üstbilgi denetiminde öğelerin soldan sağa sırasını ayarlar.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Parametreler

*iSay*<br/>
Üstbilgi denetim öğelerinin sayısı.

*piArray*<br/>
Üstbilgi denetimindeki öğelerin dizin değerlerini soldan sağa doğru görünme sırasına göre alan arabelleğin adresine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 makro [HDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray)davranışını uygular. Üstbilgi madde siparişini desteklemek için sağlanır.

### <a name="example"></a>Örnek

  [CHeaderCtrl örneğine bakın:GetOrderArray](#getorderarray).

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl Sınıfı](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList Sınıfı](../../mfc/reference/cimagelist-class.md)
