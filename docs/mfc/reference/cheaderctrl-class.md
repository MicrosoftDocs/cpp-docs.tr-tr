---
title: CHeaderCtrl sınıfı
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
ms.openlocfilehash: f225d406ab1560b4308a468ebd71b3dfd88cfa2a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562180"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl sınıfı

Windows ortak üstbilgi denetimi işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHeaderCtrl:: CHeaderCtrl](#cheaderctrl)|Bir `CHeaderCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHeaderCtrl:: ClearAllFilters](#clearallfilters)|Üst bilgi denetimi için tüm filtreleri temizler.|
|[CHeaderCtrl:: ClearFilter](#clearfilter)|Üst bilgi denetimi için filtreyi temizler.|
|[CHeaderCtrl:: Create](#create)|Bir üst bilgi denetimi oluşturur ve bunu bir `CHeaderCtrl` nesneye ekler.|
|[CHeaderCtrl:: CreateDragImage](#createdragimage)|Üst bilgi denetimindeki bir öğenin resminin saydam bir sürümünü oluşturur.|
|[CHeaderCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir üst bilgi denetimi oluşturur ve bunu bir `CListCtrl` nesneye ekler.|
|[CHeaderCtrl::D Eleteıtem](#deleteitem)|Üst bilgi denetiminden bir öğeyi siler.|
|[CHeaderCtrl::D rawItem](#drawitem)|Üst bilgi denetiminin belirtilen öğesini çizer.|
|[CHeaderCtrl:: EditFilter](#editfilter)|, Bir üst bilgi denetiminin belirtilen filtresini düzenlemesine başlar.|
|[CHeaderCtrl:: GetBitmapMargin](#getbitmapmargin)|Üst bilgi denetimindeki bir bit eşlemin kenar boşluğunun genişliğini alır.|
|[CHeaderCtrl:: GetFocusedItem](#getfocuseditem)|Geçerli üstbilgi denetimindeki, odağa sahip olan öğenin tanımlayıcısını alır.|
|[CHeaderCtrl:: GetImageList](#getimagelist)|Üst bilgi denetiminde üstbilgi öğelerini çizmek için kullanılan bir görüntü listesinin tanıtıcısını alır.|
|[CHeaderCtrl:: GetItem](#getitem)|Üstbilgi denetimindeki bir öğe hakkında bilgi alır.|
|[CHeaderCtrl:: GetItemCount](#getitemcount)|Üst bilgi denetimindeki öğelerin sayısını alır.|
|[CHeaderCtrl:: GetItemDropDownRect](#getitemdropdownrect)|Üst bilgi denetimindeki belirtilen açılan düğme için sınırlayıcı dikdörtgen bilgilerini alır.|
|[CHeaderCtrl:: GetItemRect](#getitemrect)|Üst bilgi denetimindeki belirli bir öğe için sınırlayıcı dikdörtgeni alır.|
|[CHeaderCtrl:: GetOrderArray](#getorderarray)|Üst bilgi denetimindeki öğelerin soldan sağa sırasını alır.|
|[CHeaderCtrl:: GetOverflowRect](#getoverflowrect)|Geçerli üst bilgi denetimi için taşma düğmesinin sınırlayıcı dikdörtgenini alır.|
|[CHeaderCtrl:: HitTest](#hittest)|Hangi başlık öğesinin (varsa) belirtilen bir noktada olduğunu belirler.|
|[CHeaderCtrl:: InsertItem](#insertitem)|Üstbilgi denetimine yeni bir öğe ekler.|
|[CHeaderCtrl:: Layout](#layout)|Belirli bir dikdörtgen içindeki üst bilgi denetiminin boyutunu ve konumunu alır.|
|[CHeaderCtrl:: OrderToIndex](#ordertoindex)|Üst bilgi denetimindeki sırası temelinde bir öğenin dizin değerini alır.|
|[CHeaderCtrl:: SetBitmapMargin](#setbitmapmargin)|Üst bilgi denetimindeki bir bit eşlemin kenar boşluğunun genişliğini ayarlar.|
|[CHeaderCtrl:: SetFilterChangeTimeout](#setfilterchangetimeout)|Filtre özniteliklerinde ve bir bildirimin nakliyle bir değişikliğin gerçekleştiği zaman arasındaki zaman aşımı aralığını ayarlar `HDN_FILTERCHANGE` .|
|[CHeaderCtrl:: SetFocusedItem](#setfocuseditem)|Odağı geçerli üstbilgi denetimindeki belirtilen üstbilgi öğesine ayarlar.|
|[CHeaderCtrl:: Sethotayırıcı](#sethotdivider)|Üst bilgi öğesinin el ile sürükleyip sürüklemeyeceğini göstermek için üst bilgi öğeleri arasındaki ayırıcıyı değiştirir.|
|[CHeaderCtrl:: SetImageList](#setimagelist)|Üstbilgi denetimine bir görüntü listesi atar.|
|[CHeaderCtrl:: SetItem](#setitem)|Üst bilgi denetimindeki belirtilen öğenin özniteliklerini ayarlar.|
|[CHeaderCtrl:: SetOrderArray](#setorderarray)|Üst bilgi denetimindeki öğelerin soldan sağa sırasını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Üst bilgi denetimi, genellikle metin veya sayı sütunlarının bir kümesinin üzerine yerleştirilmiş bir penceredir. Her sütun için bir başlık içerir ve bölümlere ayrılabilir. Kullanıcı, her sütunun genişliğini ayarlamak için parçaları ayıran bölücüleri sürükleyebilir. Üst bilgi denetimi çizimi için bkz. [üst bilgi denetimleri](/windows/win32/Controls/header-controls).

Bu denetim (ve bu nedenle `CHeaderCtrl` sınıfı) yalnızca windows 95/98 ve WINDOWS NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Windows 95/Internet Explorer 4,0 ortak denetimleri için eklenen işlevler şunları içerir:

- Üst bilgi öğesi özel sıralaması.

- Üstbilgi öğelerinin yeniden sıralanması için üst bilgi öğesi sürükle ve bırak. Nesneyi oluştururken HDS_DRAGDROP stilini kullanın `CHeaderCtrl` .

- Sütun yeniden boyutlandırılırken sürekli olarak görüntülenebilir üstbilgi sütunu metni. Bir nesne oluştururken HDS_FULLDRAG stilini kullanın `CHeaderCtrl` .

- Üst bilgi öğesini işaretçinin üzerine getirildiğinde üst bilgi öğesini vurgular. Nesneyi oluştururken HDS_HOTTRACK stilini kullanın `CHeaderCtrl` .

- Görüntü listesi desteği. Üst bilgi öğeleri, bir nesne veya metin içinde depolanan görüntüleri içerebilir `CImageList` .

Kullanma hakkında daha fazla bilgi için `CHeaderCtrl` bkz. [denetimler](../../mfc/controls-mfc.md) ve [CHeaderCtrl kullanma](../../mfc/using-cheaderctrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a> CHeaderCtrl:: CHeaderCtrl

Bir `CHeaderCtrl` nesnesi oluşturur.

```
CHeaderCtrl();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

## <a name="cheaderctrlclearallfilters"></a><a name="clearallfilters"></a> CHeaderCtrl:: ClearAllFilters

Üst bilgi denetimi için tüm filtreleri temizler.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklandığı gibi, Win32 ileti [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter) ,-1 sütun değeri ile uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

## <a name="cheaderctrlclearfilter"></a><a name="clearfilter"></a> CHeaderCtrl:: ClearFilter

Üst bilgi denetimi için filtreyi temizler.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
Hangi filtrenin temizleneceğini gösteren sütun değeri.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklandığı gibi Win32 ileti [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

## <a name="cheaderctrlcreate"></a><a name="create"></a> CHeaderCtrl:: Create

Bir üst bilgi denetimi oluşturur ve bunu bir `CHeaderCtrl` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Üst bilgi denetiminin stilini belirtir. Üst bilgi denetim stillerinin açıklaması için Windows SDK [üst bilgi denetim stillerine](/windows/win32/Controls/header-control-styles) bakın.

*Rect*<br/>
Üst bilgi denetiminin boyutunu ve konumunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Üst bilgi denetiminin üst penceresini (genellikle a) belirtir `CDialog` . NULL olmaması gerekir.

*NID*<br/>
Üst bilgi denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

`CHeaderCtrl`İki adımda bir nesne oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve sonra `Create` başlık denetimini oluşturan ve bunu nesnesine bağlayan çağırın `CHeaderCtrl` .

Üst bilgi denetim stillerine ek olarak, üst bilgi denetiminin konumunu ve yeniden boyutlandırılacağını anlamak için aşağıdaki ortak denetim stillerini kullanabilirsiniz (daha fazla bilgi için bkz. [ortak denetim stilleri](/windows/win32/Controls/common-control-styles) ):

- CCS_BOTTOM, denetimin kendisini üst pencerenin istemci alanının altına konumlandırmasına ve genişliği üst pencerenin genişliğiyle aynı olacak şekilde ayarlıyor.

- CCS_NODIVIDER, iki piksellik bir vurgulamanın denetimin en üstünde çizilmesini önler.

- CCS_NOMOVEY, bir WM_SIZE iletisine yanıt olarak denetimin kendisini yatay olarak yeniden boyutlandırmasına ve taşımasına neden olur. CCS_NORESIZE stil kullanılırsa, bu stil uygulanmaz. Üstbilgi denetimlerinde bu stil varsayılan olarak vardır.

- CCS_NOPARENTALIGN, denetimin üst pencerenin üst veya alt kısmına otomatik olarak taşınmasını önler. Bunun yerine denetim, üst pencerenin boyutunda değişikliğe karşın konumunu üst pencere içinde tutar. CCS_TOP veya CCS_BOTTOM stili de kullanılıyorsa, yükseklik varsayılana ayarlanır, ancak konum ve genişlik değişmeden kalır.

- CCS_NORESIZE, denetimin ilk boyutunu veya yeni bir boyutu ayarlarken varsayılan genişlik ve yükseklik kullanmasını önler. Bunun yerine denetim, oluşturma veya boyutlandırma isteğinde belirtilen genişlik ve yüksekliği kullanır.

- CCS_TOP, denetimin kendisini üst pencerenin istemci alanının üstüne konumlandırmasına ve genişliği üst pencerenin genişliğiyle aynı olacak şekilde ayarlıyor.

Ayrıca, bir üstbilgi denetimine aşağıdaki pencere stillerini uygulayabilirsiniz (daha fazla bilgi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ):

- WS_CHILD bir alt pencere oluşturur. WS_POPUP stille birlikte kullanılamaz.

- WS_VISIBLE Başlangıçta görünür olan bir pencere oluşturur.

- WS_DISABLED başlangıçta devre dışı olan bir pencere oluşturur.

- WS_GROUP, kullanıcının ok tuşlarıyla bir denetimden diğerine taşıyabileceği bir denetim grubunun ilk denetimini belirtir. İlk denetimden sonra WS_GROUP stili ile tanımlanmış tüm denetimler aynı gruba aittir. WS_GROUP stili olan bir sonraki denetim stil grubunu sonlandırır ve sonraki grubu başlatır (yani, bir grup bir sonraki başladığı yerde sona erer).

- WS_TABSTOP, kullanıcının TAB tuşunu kullanarak taşıyabileceği birçok denetimden birini belirtir. TAB tuşu, Kullanıcı WS_TABSTOP stili tarafından belirtilen sonraki denetime taşınıyor.

Denetimi ile genişletilmiş Windows stilleri kullanmak istiyorsanız, yerine [CreateEx](#createex) çağırın `Create` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

## <a name="cheaderctrlcreateex"></a><a name="createex"></a> CHeaderCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CHeaderCtrl` nesneyle ilişkilendirir.

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
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

*dwStyle*<br/>
Üst bilgi denetiminin stili. Üst bilgi denetim stillerinin açıklaması için Windows SDK [üst bilgi denetim stillerine](/windows/win32/Controls/header-control-styles) bakın. Ek stillerin listesi için bkz. [oluşturma](#create) .

*Rect*<br/>
*PParentWnd*istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreateEx` `Create` Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için yerine kullanın.

## <a name="cheaderctrlcreatedragimage"></a><a name="createdragimage"></a> CHeaderCtrl:: CreateDragImage

Üst bilgi denetimindeki bir öğenin resminin saydam bir sürümünü oluşturur.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Üst bilgi denetimindeki öğenin sıfır tabanlı dizini. Bu öğeye atanan görüntü, saydam görüntünün temelini oluşturur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir [Ciımagelist](../../mfc/reference/cimagelist-class.md) nesnesine bir işaretçi; Aksi takdirde NULL. Döndürülen liste yalnızca bir görüntü içeriyor.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_CREATEDRAGIMAGE](/windows/win32/Controls/hdm-createdragimage)davranışını uygular. Başlık öğesi sürükle ve bırak desteği için verilmiştir.

`CImageList`Döndürülen işaretçinin işaret ettiği nesne, geçici bir nesne ve sonraki boş zamanlı işleme içinde silinir.

## <a name="cheaderctrldeleteitem"></a><a name="deleteitem"></a> CHeaderCtrl::D Eleteıtem

Üst bilgi denetiminden bir öğeyi siler.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Silinecek öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

## <a name="cheaderctrldrawitem"></a><a name="drawitem"></a> CHeaderCtrl::D rawItem

Sahip çizim üst bilgi denetiminin görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Boyanmış öğeyi açıklayan [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`itemAction` `DRAWITEMSTRUCT` Yapının üyesi gerçekleştirilecek çizim eylemini tanımlar.

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bir sahip çizim nesnesi için çizimi uygulamak üzere bu üye işlevini geçersiz kılın `CHeaderCtrl` .

Uygulamanın, bu üye işlevi sonlandırılmadan önce *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

## <a name="cheaderctrleditfilter"></a><a name="editfilter"></a> CHeaderCtrl:: EditFilter

Üst bilgi denetiminin belirtilen filtresini düzenlemeye başlar.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
Düzenlenecek sütun.

*bDiscardChanges*<br/>
Kullanıcı, [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter) ileti gönderildiğinde filtreyi düzenlemekte olduğunuz durumlarda kullanıcının düzenlenme değişikliklerinin nasıl işleneceğini belirten bir değer.

Kullanıcı tarafından yapılan değişiklikleri atmak için TRUE, veya Kullanıcı tarafından yapılan değişiklikleri kabul etmek için FALSE değerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklandığı gibi Win32 ileti [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

## <a name="cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a> CHeaderCtrl:: GetBitmapMargin

Üst bilgi denetimindeki bir bit eşlemin kenar boşluğunun genişliğini alır.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem kenar boşluğunun piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_GETBITMAPMARGIN](/windows/win32/Controls/hdm-getbitmapmargin)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

## <a name="cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a> CHeaderCtrl:: GetFocusedItem

Geçerli üstbilgi denetiminde odağa sahip olan öğenin dizinini alır.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Odağa sahip olan üst bilgi öğesinin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl` geçerli üst bilgi denetimine erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `SetFocusedItem` ve `GetFocusedItem` yöntemlerini gösterir. Kodun önceki bir bölümünde beş sütunlu bir başlık denetimi oluşturduk. Ancak, sütunun görünür olmaması için bir sütun ayırıcısını sürükleyebilirsiniz. Aşağıdaki örnek, son sütun başlığını odak öğesi olarak ayarlar ve onaylar.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlgetimagelist"></a><a name="getimagelist"></a> CHeaderCtrl:: GetImageList

Üst bilgi denetiminde üstbilgi öğelerini çizmek için kullanılan bir görüntü listesinin tanıtıcısını alır.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_GETIMAGELIST](/windows/win32/Controls/hdm-getimagelist)davranışını uygular. `CImageList`Döndürülen işaretçinin işaret ettiği nesne, geçici bir nesne ve sonraki boş zamanlı işleme içinde silinir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

## <a name="cheaderctrlgetitem"></a><a name="getitem"></a> CHeaderCtrl:: GetItem

Bir üstbilgi denetim öğesi hakkında bilgi alır.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Alınacak öğenin sıfır tabanlı dizinini belirtir.

*Pheaderıtem*<br/>
Yeni öğeyi alan [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısına yönelik işaretçi. Bu yapı `InsertItem` ve üye işlevleriyle birlikte kullanılır `SetItem` . Öğesinde ayarlanan tüm bayraklar `mask` , karşılık gelen öğelerdeki değerlerin geri dönüş sonrasında doğru doldurulduğundan emin olun. `mask`Öğe sıfır olarak ayarlandıysa, diğer yapı öğelerindeki değerler anlamsız olur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

## <a name="cheaderctrlgetitemcount"></a><a name="getitemcount"></a> CHeaderCtrl:: GetItemCount

Üst bilgi denetimindeki öğelerin sayısını alır.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa üstbilgi denetim öğelerinin sayısı; Aksi takdirde-1.

### <a name="example"></a>Örnek

  [CHeaderCtrl::D eleteItem](#deleteitem)örneğine bakın.

## <a name="cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a> CHeaderCtrl:: GetItemDropDownRect

Geçerli üstbilgi denetimindeki bir üstbilgi öğesi için aşağı açılan düğmenin sınırlayıcı dikdörtgenini alır.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*IItem*\
'ndaki Stili HDF_SPLITBUTTON olan üst bilgi öğesinin sıfır tabanlı dizini. Daha fazla bilgi için bkz `fmt` . [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısı üyesi.

*lpRect*\
dışı Sınırlayıcı dikdörtgen bilgilerini almak için bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu işlev başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl` geçerli üst bilgi denetimine erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `GetItemDropDownRect` yöntemini gösterir. Kodun önceki bir bölümünde beş sütunlu bir başlık denetimi oluşturduk. Aşağıdaki kod örneği, üst bilgi açılan düğmesi için ayrılan ilk sütundaki konumun etrafında 3B bir dikdörtgen çizer.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

## <a name="cheaderctrlgetitemrect"></a><a name="getitemrect"></a> CHeaderCtrl:: GetItemRect

Üst bilgi denetimindeki belirli bir öğe için sınırlayıcı dikdörtgeni alır.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Üst bilgi denetim öğesinin sıfır tabanlı dizini.

*lpRect*<br/>
Sınırlayıcı dikdörtgen bilgilerini alan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısının adresine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklandığı gibi Win32 ileti [HDM_GETITEMRECT](/windows/win32/Controls/hdm-getitemrect)davranışını uygular.

## <a name="cheaderctrlgetorderarray"></a><a name="getorderarray"></a> CHeaderCtrl:: GetOrderArray

Üst bilgi denetimindeki öğelerin soldan sağa sırasını alır.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>Parametreler

*piArray*<br/>
Üst bilgi denetimindeki öğelerin dizin değerlerini soldan sağa göründükleri sırada alan bir arabelleğin adresine yönelik bir işaretçi.

*ıyeniden bağlama*<br/>
Üst bilgi denetim öğesi sayısı. Negatif olmayan bir değer olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_GETORDERARRAY](/windows/win32/Controls/hdm-getorderarray)davranışını uygular. Başlık öğesi sıralamasını desteklemek için verilmiştir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

## <a name="cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a> CHeaderCtrl:: GetOverflowRect

Geçerli üst bilgi denetiminin taşma düğmesinin sınırlayıcı dikdörtgenini alır.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*\
dışı Sınırlayıcı dikdörtgen bilgilerini alan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu işlev başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Üstbilgi denetimi aynı anda görüntülenebileceğinden daha fazla öğe içeriyorsa, denetim görünür olmayan öğelere kayan bir taşma düğmesi görüntüleyebilir. Üst bilgi denetiminde, taşma düğmesini göstermek için HDS_OVERFLOW ve HDF_SPLITBUTTON stilleri olmalıdır. Sınırlayıcı dikdörtgen taşma düğmesini barındırır ve yalnızca taşma düğmesi görüntülenirken bulunur. Daha fazla bilgi için bkz. [üstbilgi denetim stilleri](/windows/win32/Controls/header-control-styles).

Bu yöntem, Windows SDK açıklanan [HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl` geçerli üst bilgi denetimine erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `GetOverflowRect` yöntemini gösterir. Kodun önceki bir bölümünde beş sütunlu bir başlık denetimi oluşturduk. Ancak, sütunun görünür olmaması için bir sütun ayırıcısını sürükleyebilirsiniz. Bazı sütunlar görünür değilse, üst bilgi denetimi bir taşma düğmesi çizer. Aşağıdaki kod örneği, taşma düğmesinin konumunun etrafında bir 3B dikdörtgen çizer.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

## <a name="cheaderctrlhittest"></a><a name="hittest"></a> CHeaderCtrl:: HitTest

Hangi başlık öğesinin (varsa) belirtilen bir noktada olduğunu belirler.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>Parametreler

*phdhtı*\
[in, out] Testin sonuçlarını test etmek ve almak için noktayı belirten bir [Hdhittestınfo](/windows/win32/api/commctrl/ns-commctrl-hdhittestinfo) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Üst bilgi öğesinin, varsa, belirtilen konumdaki sıfır tabanlı dizini; Aksi takdirde,-1.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [HDM_HITTEST](/windows/win32/Controls/hdm-hittest) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl` geçerli üst bilgi denetimine erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `HitTest` yöntemini gösterir. Bu kod örneği daha önceki bir bölümünde beş sütunlu bir başlık denetimi oluşturduk. Ancak, sütunun görünür olmaması için bir sütun ayırıcısını sürükleyebilirsiniz. Bu örnek, görünür durumdaysa sütunun dizinini bildirir ve sütun görünür değilse-1 ' dir.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

## <a name="cheaderctrlinsertitem"></a><a name="insertitem"></a> CHeaderCtrl:: InsertItem

Belirtilen dizinde üstbilgi denetimine yeni bir öğe ekler.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Eklenecek öğenin sıfır tabanlı dizini. Değer sıfırsa, öğe üst bilgi denetiminin başına eklenir. Değer en büyük değerden büyükse, öğe üst bilgi denetiminin sonuna eklenir.

*phdi*<br/>
Eklenecek öğe hakkında bilgi içeren bir [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni öğenin dizini; Aksi takdirde-1.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

## <a name="cheaderctrllayout"></a><a name="layout"></a> CHeaderCtrl:: Layout

Belirli bir dikdörtgen içindeki üst bilgi denetiminin boyutunu ve konumunu alır.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>Parametreler

*pHeaderLayout*<br/>
Bir üst bilgi denetiminin boyutunu ve konumunu ayarlamak için kullanılan bilgileri içeren bir [hdlayout](/windows/win32/api/commctrl/ns-commctrl-hdlayout) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, verilen dikdörtgenin kaplayacağı yeni bir üst bilgi denetimi için uygun boyutları belirlemekte kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

## <a name="cheaderctrlordertoindex"></a><a name="ordertoindex"></a> CHeaderCtrl:: OrderToIndex

Üst bilgi denetimindeki sırası temelinde bir öğenin dizin değerini alır.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>Parametreler

*nOrder*<br/>
Öğenin üst bilgi denetiminde, soldan sağa göründüğü sıfır tabanlı sıra.

### <a name="return-value"></a>Dönüş Değeri

Üst bilgi denetimindeki sırasına göre öğenin dizini. Dizin, soldan sağa, 0 ile başlayarak sayılır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 makro [HDM_ORDERTOINDEX](/windows/win32/controls/hdm-ordertoindex)davranışını uygular. Başlık öğesi sıralamasını desteklemek için verilmiştir.

## <a name="cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a> CHeaderCtrl:: SetBitmapMargin

Üst bilgi denetimindeki bir bit eşlemin kenar boşluğunun genişliğini ayarlar.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Varolan bir üst bilgi denetimindeki bir bit eşlemi çevreleyen kenar boşluğunun piksel cinsinden belirtilen genişliği.

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem kenar boşluğunun piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_SETBITMAPMARGIN](/windows/win32/Controls/hdm-setbitmapmargin)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

## <a name="cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a> CHeaderCtrl:: SetFilterChangeTimeout

Filtre özniteliklerinde bir değişikliğin gerçekleştiği saat ile [HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange) bildiriminin nakledilme arasındaki zaman aşımı aralığını ayarlar.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>Parametreler

*dwTimeOut*<br/>
Milisaniye cinsinden zaman aşımı değeri.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilmekte olan filtre denetiminin dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_SETFILTERCHANGETIMEOUT](/windows/win32/Controls/hdm-setfilterchangetimeout)davranışını uygular.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

## <a name="cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a> CHeaderCtrl:: SetFocusedItem

Odağı geçerli üstbilgi denetimindeki belirtilen üstbilgi öğesine ayarlar.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>Parametreler

*IItem*\
'ndaki Üst bilgi öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_headerCtrl` geçerli üst bilgi denetimine erişmek için kullanılan değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği `SetFocusedItem` ve `GetFocusedItem` yöntemlerini gösterir. Kodun önceki bir bölümünde beş sütunlu bir başlık denetimi oluşturduk. Ancak, sütunun görünür olmaması için bir sütun ayırıcısını sürükleyebilirsiniz. Aşağıdaki örnek, son sütun başlığını odak öğesi olarak ayarlar ve onaylar.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlsethotdivider"></a><a name="sethotdivider"></a> CHeaderCtrl:: Sethotayırıcı

Üst bilgi öğesinin el ile sürükleyip sürüklemeyeceğini göstermek için üst bilgi öğeleri arasındaki ayırıcıyı değiştirir.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
İşaretçinin konumu. Üst bilgi denetimi, işaretçinin konumuna göre uygun ayırıcıyı vurgular.

*nDizin*<br/>
Vurgulanan ayırıcının dizini.

### <a name="return-value"></a>Dönüş Değeri

Vurgulanan ayırıcının dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_SETHOTDIVIDER](/windows/win32/Controls/hdm-sethotdivider)davranışını uygular. Başlık öğesi sürükle ve bırak desteği için verilmiştir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

## <a name="cheaderctrlsetimagelist"></a><a name="setimagelist"></a> CHeaderCtrl:: SetImageList

Üstbilgi denetimine bir görüntü listesi atar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
`CImageList`Üst bilgi denetimine Atanacak görüntü listesini içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Daha önce üst bilgi denetimine atanan [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 ileti [HDM_SETIMAGELIST](/windows/win32/Controls/hdm-setimagelist)davranışını uygular. `CImageList`Döndürülen işaretçinin işaret ettiği nesne, geçici bir nesne ve sonraki boş zamanlı işleme içinde silinir.

### <a name="example"></a>Örnek

  [CHeaderCtrl:: GetImageList](#getimagelist)için örneğe bakın.

## <a name="cheaderctrlsetitem"></a><a name="setitem"></a> CHeaderCtrl:: SetItem

Üst bilgi denetimindeki belirtilen öğenin özniteliklerini ayarlar.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Değiştirilecek öğenin sıfır tabanlı dizini.

*Pheaderıtem*<br/>
Yeni öğe hakkında bilgi içeren bir [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

  [CHeaderCtrl:: GetItem](#getitem)için örneğe bakın.

## <a name="cheaderctrlsetorderarray"></a><a name="setorderarray"></a> CHeaderCtrl:: SetOrderArray

Üst bilgi denetimindeki öğelerin soldan sağa sırasını ayarlar.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>Parametreler

*ıyeniden bağlama*<br/>
Üst bilgi denetim öğesi sayısı.

*piArray*<br/>
Üst bilgi denetimindeki öğelerin dizin değerlerini soldan sağa göründükleri sırada alan bir arabelleğin adresine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi Win32 makro [HDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray)davranışını uygular. Başlık öğesi sıralamasını desteklemek için verilmiştir.

### <a name="example"></a>Örnek

  [CHeaderCtrl:: GetOrderArray](#getorderarray)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl sınıfı](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList sınıfı](../../mfc/reference/cimagelist-class.md)
