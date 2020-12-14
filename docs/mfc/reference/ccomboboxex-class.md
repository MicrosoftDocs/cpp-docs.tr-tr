---
description: 'Daha fazla bilgi edinin: CComboBoxEx sınıfı'
title: CComboBoxEx sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: 6d5b8a520fe62cbc60883370ec92abe4d978b5bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265525"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx sınıfı

Görüntü listeleri için destek sağlayarak Birleşik giriş kutusu denetimini genişletir.

## <a name="syntax"></a>Syntax

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComboBoxEx:: CComboBoxEx](#ccomboboxex)|Bir `CComboBoxEx` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComboBoxEx:: Create](#create)|Birleşik giriş kutusunu oluşturur ve `CComboBoxEx` nesneye ekler.|
|[CComboBoxEx:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle Birleşik giriş kutusu oluşturur ve bunu bir `ComboBoxEx` nesneye ekler.|
|[CComboBoxEx::D Eleteıtem](#deleteitem)|Denetimden bir öğeyi kaldırır `ComboBoxEx` .|
|[CComboBoxEx:: GetComboBoxCtrl](#getcomboboxctrl)|Alt Birleşik giriş kutusu denetimine bir işaretçi alır.|
|[CComboBoxEx:: GetEditCtrl](#geteditctrl)|Bir denetimin düzenleme denetim kısmına tanıtıcıyı alır `ComboBoxEx` .|
|[CComboBoxEx:: Getcdedstyle](#getextendedstyle)|Bir denetim için kullanımda olan Genişletilmiş stilleri alır `ComboBoxEx` .|
|[CComboBoxEx:: GetImageList](#getimagelist)|Denetime atanan görüntü listesine yönelik bir işaretçi alır `ComboBoxEx` .|
|[CComboBoxEx:: GetItem](#getitem)|Belirli bir öğe için öğe bilgilerini alır `ComboBoxEx` .|
|[CComboBoxEx:: HasEditChanged](#haseditchanged)|Kullanıcının düzenleme denetiminin içeriğini yazarak değiştirmeyeceğini belirler `ComboBoxEx` .|
|[CComboBoxEx:: InsertItem](#insertitem)|Denetime yeni bir öğe ekler `ComboBoxEx` .|
|[CComboBoxEx:: Setcdedstyle](#setextendedstyle)|Denetim içinde Genişletilmiş stilleri ayarlar `ComboBoxEx` .|
|[CComboBoxEx:: SetImageList](#setimagelist)|Denetim için bir görüntü listesi ayarlar `ComboBoxEx` .|
|[CComboBoxEx:: SetItem](#setitem)|Denetimdeki bir öğenin özniteliklerini ayarlar `ComboBoxEx` .|
|[CComboBoxEx:: SetWindowTheme](#setwindowtheme)|Genişletilmiş Birleşik giriş kutusu denetiminin görsel stilini ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CComboBoxEx`Birleşik giriş kutusu denetimleri oluşturmak için kullanarak, artık kendi resim çizim kodunuzu uygulamanız gerekmez. Bunun yerine, `CComboBoxEx` görüntü listesinden görüntülere erişmek için kullanın.

## <a name="image-list-support"></a>Görüntü listesi desteği

Standart bir açılan kutuda, Birleşik giriş kutusunun sahibi, Birleşik giriş kutusunu bir sahip çizim denetimi olarak oluşturarak bir resim çizmekten sorumludur. Kullandığınızda `CComboBoxEx` , CBS_OWNERDRAWFIXED ve CBS_HASSTRINGS çizim stillerini ayarlamanız gerekmez. Aksi takdirde, çizim işlemlerini gerçekleştirmek için kod yazmalısınız. Bir `CComboBoxEx` Denetim öğe başına en fazla üç görüntüyü destekler: biri seçili bir durum, bir diğeri seçilmemiş durum için ve bir kaplama görüntüsü için.

## <a name="styles"></a>Stiller

`CComboBoxEx` CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST ve WS_CHILD stilleri destekler. Pencereyi oluşturduğunuzda geçirilen diğer tüm stiller denetim tarafından yok sayılır. Pencere oluşturulduktan sonra, `CComboBoxEx` [Setil dedstyle](#setextendedstyle)üye işlevini çağırarak diğer Birleşik giriş kutusu stillerini sağlayabilirsiniz. Bu stillerle şunları yapabilirsiniz:

- Listedeki dize aramalarını büyük/küçük harfe duyarlı olacak şekilde ayarlayın.

- Eğik çizgi ('/'), ters eğik çizgi (' \\ ') ve nokta ('. ') karakterlerini sözcük sınırlayıcıları olarak kullanan bir Birleşik giriş kutusu denetimi oluşturun. Bu, kullanıcıların klavye kısayolunu CTRL + ok kullanarak Word 'e atlamasına izin verir.

- Birleşik giriş kutusu denetimini görüntü görüntüleme ya da görüntüleme olarak ayarlama. Resim görüntülenmiyorsa, Birleşik giriş kutusu görüntüye sahip olan metin girintisini kaldırabilir.

- Bir dar Birleşik giriş kutusu denetimi oluşturun, bu sayede, içerdiği geniş Birleşik giriş kutusunun boyutunu kırpar.

Bu stil bayrakları [CComboBoxEx kullanma](../../mfc/using-ccomboboxex.md)konusunda daha ayrıntılı olarak açıklanmıştır.

## <a name="item-retention-and-callback-item-attributes"></a>Öğe bekletme ve geri çağırma öğesi öznitelikleri

Öğelerin ve görüntülerin dizinleri, girintileme değerleri ve metin dizeleri gibi öğe bilgileri, Windows SDK bölümünde açıklandığı gibi Win32 yapısı [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)' da depolanır. Yapı, geri çağırma bayraklarına karşılık gelen üyeleri de içerir.

Ayrıntılı, kavramsal bir tartışma için bkz. [CComboBoxEx kullanma](../../mfc/using-ccomboboxex.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a> CComboBoxEx:: CComboBoxEx

Bir nesne oluşturmak için bu üye işlevini çağırın `CComboBoxEx` .

```
CComboBoxEx();
```

## <a name="ccomboboxexcreate"></a><a name="create"></a> CComboBoxEx:: Create

Birleşik giriş kutusunu oluşturur ve `CComboBoxEx` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Birleşik giriş kutusuna uygulanan Birleşik giriş kutusu stillerinin birleşimini belirtir. Stiller hakkında daha fazla bilgi **için aşağıdaki açıklamalara** bakın.

*Rect*<br/>
Birleşik giriş kutusunun konumu ve boyutu olan bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine veya [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Birleşik giriş kutusunun üst penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi (genellikle a `CDialog` ). NULL olmaması gerekir.

*NID*<br/>
Birleşik giriş kutusunun Denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CComboBoxEx`İki adımda bir nesne oluşturun:

1. Bir nesne oluşturmak için [CComboBoxEx](#ccomboboxex) öğesini çağırın `CComboBoxEx` .

1. Genişletilmiş Windows Birleşik giriş kutusunu oluşturan ve nesnesine ekleyen bu üye işlevini çağırın `CComboBoxEx` .

Çağırdığınızda `Create` , mfc ortak denetimleri başlatır.

Birleşik giriş kutusunu oluşturduğunuzda, aşağıdaki Birleşik giriş kutusu stillerinden herhangi birini veya tümünü belirtebilirsiniz:

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

Pencereyi oluşturduğunuzda geçirilen diğer tüm stiller yok sayılır. `ComboBoxEx`Denetim ayrıca ek özellikler sağlayan Genişletilmiş stilleri destekler. Bu stiller, Windows SDK [ComboBoxEx denetimi genişletilmiş stillerinde](/windows/win32/Controls/comboboxex-control-extended-styles)açıklanmıştır. [Setil Dedstyle](#setextendedstyle)öğesini çağırarak bu stilleri ayarlayın.

Denetimi ile genişletilmiş Windows stilleri kullanmak istiyorsanız, yerine [CreateEx](#createex) çağırın `Create` .

## <a name="ccomboboxexcreateex"></a><a name="createex"></a> CComboBoxEx:: CreateEx

Genişletilmiş Birleşik giriş kutusu denetimi (bir alt pencere) oluşturmak ve nesneyle ilişkilendirmek için bu işlevi çağırın `CComboBoxEx` .

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
Birleşik giriş kutusu denetiminin stili. Stil listesi için bkz. [oluşturma](#create) .

*Rect*<br/>
*PParentWnd* istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreateEx` `Create` Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için yerine kullanın.

`CreateEx`*dwExStyle* tarafından belirtilen Genişletilmiş Windows stilleriyle denetimi oluşturur. [Setil dedstyle](#setextendedstyle)kullanarak genişletilmiş bir Birleşik giriş kutusu denetimine özgü genişletilmiş stilleri ayarlamanız gerekir. Örneğin, `CreateEx` Bu tür stilleri ws_ex_contexthelp olarak ayarlamak için kullanın, ancak `SetExtendedStyle` Bu tür stilleri CBES_EX_CASESENSITIVE olarak ayarlamak için kullanın. Daha fazla bilgi için, Windows SDK [ComboBoxEx denetimi genişletilmiş stillerinde](/windows/win32/Controls/comboboxex-control-extended-styles) başlıklı konuda açıklanan stillere bakın.

## <a name="ccomboboxexdeleteitem"></a><a name="deleteitem"></a> CComboBoxEx::D Eleteıtem

Denetimden bir öğeyi kaldırır `ComboBoxEx` .

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
Kaldırılacak öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Denetimde kalan öğe sayısı. *IIndex* geçersizse, işlev cb_err döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)ileti işlevlerini uygular. DeleteItem öğesini çağırdığınızda, ana pencereye CBEN_DELETEITEM bildirimine sahip [WM_NOTIFY](/windows/win32/controls/wm-notify) bir ileti gönderilir.

## <a name="ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a> CComboBoxEx:: GetComboBoxCtrl

Bir nesne içindeki Birleşik giriş kutusu denetimine yönelik bir işaretçi almak için bu üye işlevi çağırın `CComboBoxEx` .

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CComboBox` nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

`CComboBoxEx`Denetim, bir üst pencereden oluşur `CComboBox` .

`CComboBox`Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a> CComboBoxEx:: GetEditCtrl

Birleşik giriş kutusu için düzenleme denetimine bir işaretçi almak için bu üye işlevi çağırın.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

[Cedıt](../../mfc/reference/cedit-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CComboBoxEx`Denetim, cbs_dropdown stiliyle oluşturulduğunda bir düzenleme kutusu kullanır.

`CEdit`Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a> CComboBoxEx:: Getcdedstyle

Bir denetim için kullanılan genişletilmiş stilleri almak için bu üye işlevi çağırın `CComboBoxEx` .

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusu denetimi için kullanılan genişletilmiş stilleri içeren DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Bu stiller hakkında daha fazla bilgi için, bkz. Windows SDK [ComboBoxEx denetimi genişletilmiş stilleri](/windows/win32/Controls/comboboxex-control-extended-styles) .

## <a name="ccomboboxexgetimagelist"></a><a name="getimagelist"></a> CComboBoxEx:: GetImageList

Bir denetim tarafından kullanılan görüntü listesine bir işaretçi almak için bu üye işlevi çağırın `CComboBoxEx` .

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi. Başarısız olursa, bu üye işlevi NULL döndürür.

### <a name="remarks"></a>Açıklamalar

`CImageList`Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexgetitem"></a><a name="getitem"></a> CComboBoxEx:: GetItem

Belirli bir öğe için öğe bilgilerini alır `ComboBoxEx` .

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametreler

*pCBItem*<br/>
Öğe bilgilerini alacak bir [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)ileti işlevlerini uygular.

## <a name="ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a> CComboBoxEx:: HasEditChanged

Kullanıcının düzenleme denetiminin içeriğini yazarak değiştirmeyeceğini belirler `ComboBoxEx` .

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı denetimin düzenleme kutusuna yazmışsa sıfır dışında. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)ileti işlevlerini uygular.

## <a name="ccomboboxexinsertitem"></a><a name="insertitem"></a> CComboBoxEx:: InsertItem

Denetime yeni bir öğe ekler `ComboBoxEx` .

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametreler

*pCBItem*<br/>
Öğe bilgilerini alacak bir [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısına yönelik işaretçi. Bu yapı öğe için geri çağırma bayrağı değerlerini içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni öğenin eklendiği Dizin; Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

`InsertItem`' İ çağırdığınızda, ana pencereye [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) bildirimine sahip bir [WM_NOTIFY](/windows/win32/controls/wm-notify) iletisi gönderilir.

## <a name="ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a> CComboBoxEx:: Setcdedstyle

Birleşik giriş kutusu genişletilmiş denetimi için kullanılan genişletilmiş stilleri ayarlamak için bu üye işlevini çağırın.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>Parametreler

*dwExMask*<br/>
*DwExStyles* içindeki hangi stillerin etkileneceğini BELIRTEN bir DWORD değeri. Yalnızca *dwExMask* içindeki genişletilmiş stiller değiştirilecek. Diğer tüm stiller olduğu gibi korunur. Bu parametre sıfırsa, *dwExStyles* içindeki tüm stiller etkilenecektir.

*dwExStyles*<br/>
Denetim için ayarlanacak Genişletilmiş stilleri denetim kutusu içeren bir DWORD değeri.

### <a name="return-value"></a>Dönüş Değeri

Daha önce denetim için kullanılan genişletilmiş stilleri içeren bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Bu stiller hakkında daha fazla bilgi için, bkz. Windows SDK [ComboBoxEx denetimi genişletilmiş stilleri](/windows/win32/Controls/comboboxex-control-extended-styles) .

Genişletilmiş Windows stilleriyle Birleşik giriş kutusu genişletilmiş denetimi oluşturmak için [CreateEx](#createex)kullanın.

## <a name="ccomboboxexsetimagelist"></a><a name="setimagelist"></a> CComboBoxEx:: SetImageList

Denetim için bir görüntü listesi ayarlar `ComboBoxEx` .

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
`CImageList`Denetimle birlikte kullanılacak görüntüleri içeren bir nesne işaretçisi `CComboBoxEx` .

### <a name="return-value"></a>Dönüş Değeri

Daha önce denetim tarafından kullanılan görüntüleri içeren bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi `CComboBoxEx` . Daha önce ayarlanmış bir görüntü listesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)ileti işlevlerini uygular. Varsayılan düzenleme denetiminin yüksekliğini değiştirirseniz, çağrısından sonra denetiminizi yeniden boyutlandırmak için [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) Win32 işlevini çağırın `SetImageList` veya düzgün şekilde gösterilmez.

`CImageList`Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexsetitem"></a><a name="setitem"></a> CComboBoxEx:: SetItem

Denetimdeki bir öğenin özniteliklerini ayarlar `ComboBoxEx` .

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametreler

*pCBItem*<br/>
Öğe bilgilerini alacak bir [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)ileti işlevlerini uygular.

## <a name="ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a> CComboBoxEx:: SetWindowTheme

Genişletilmiş Birleşik giriş kutusu denetiminin görsel stilini ayarlar.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametreler

*Pszalt Ppname*<br/>
Ayarlanacak Genişletilmiş Birleşik giriş kutusu görsel stilini içeren bir Unicode dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklandığı gibi [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) iletisinin işlevselliğine öykünür.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MFCıE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)
