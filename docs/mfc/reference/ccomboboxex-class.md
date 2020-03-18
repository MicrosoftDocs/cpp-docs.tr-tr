---
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
ms.openlocfilehash: 7d46f175a62cda7f1ff08327830f1dffe2967727
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420514"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx sınıfı

Görüntü listeleri için destek sağlayarak Birleşik giriş kutusu denetimini genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CComboBoxEx:: CComboBoxEx](#ccomboboxex)|`CComboBoxEx` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CComboBoxEx:: Create](#create)|Birleşik giriş kutusunu oluşturur ve `CComboBoxEx` nesnesine iliştirir.|
|[CComboBoxEx:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle Birleşik giriş kutusu oluşturur ve bir `ComboBoxEx` nesnesine ekler.|
|[CComboBoxEx::D Eleteıtem](#deleteitem)|`ComboBoxEx` denetiminden bir öğeyi kaldırır.|
|[CComboBoxEx:: GetComboBoxCtrl](#getcomboboxctrl)|Alt Birleşik giriş kutusu denetimine bir işaretçi alır.|
|[CComboBoxEx:: GetEditCtrl](#geteditctrl)|`ComboBoxEx` denetiminin düzenleme denetim kısmına tanıtıcıyı alır.|
|[CComboBoxEx:: Getcdedstyle](#getextendedstyle)|`ComboBoxEx` denetimi için kullanımda olan Genişletilmiş stilleri alır.|
|[CComboBoxEx:: GetImageList](#getimagelist)|`ComboBoxEx` denetimine atanan görüntü listesine yönelik bir işaretçi alır.|
|[CComboBoxEx:: GetItem](#getitem)|Belirli bir `ComboBoxEx` öğesi için öğe bilgilerini alır.|
|[CComboBoxEx:: HasEditChanged](#haseditchanged)|Kullanıcının `ComboBoxEx` düzenleme denetiminin içeriğini yazarak değiştirmeyeceğini belirler.|
|[CComboBoxEx:: InsertItem](#insertitem)|`ComboBoxEx` denetimine yeni bir öğe ekler.|
|[CComboBoxEx:: Setcdedstyle](#setextendedstyle)|`ComboBoxEx` denetimi içinde Genişletilmiş stilleri ayarlar.|
|[CComboBoxEx:: SetImageList](#setimagelist)|`ComboBoxEx` denetimi için bir görüntü listesi ayarlar.|
|[CComboBoxEx:: SetItem](#setitem)|`ComboBoxEx` denetimindeki bir öğenin özniteliklerini ayarlar.|
|[CComboBoxEx:: SetWindowTheme](#setwindowtheme)|Genişletilmiş Birleşik giriş kutusu denetiminin görsel stilini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Birleşik giriş kutusu denetimleri oluşturmak için `CComboBoxEx` kullanarak, artık kendi resim çizim kodunuzu uygulamanız gerekmez. Bunun yerine, görüntü listesinden görüntülere erişmek için `CComboBoxEx` kullanın.

## <a name="image-list-support"></a>Görüntü listesi desteği

Standart bir açılan kutuda, Birleşik giriş kutusunun sahibi, Birleşik giriş kutusunu bir sahip çizim denetimi olarak oluşturarak bir resim çizmekten sorumludur. `CComboBoxEx`kullandığınızda, CBS_OWNERDRAWFIXED ve CBS_HASSTRINGS çizim stillerini ayarlamanız gerekmez. Aksi takdirde, çizim işlemlerini gerçekleştirmek için kod yazmalısınız. `CComboBoxEx` denetim öğe başına en fazla üç görüntü destekler: biri seçili bir durum, bir diğeri seçilmemiş durum ve bir kaplama görüntüsü için.

## <a name="styles"></a>Stiller

`CComboBoxEx`, CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST ve WS_CHILD stilleri destekler. Pencereyi oluşturduğunuzda geçirilen diğer tüm stiller denetim tarafından yok sayılır. Pencere oluşturulduktan sonra, `CComboBoxEx` üye işlevi [Setil dedstyle](#setextendedstyle)' ı çağırarak diğer Birleşik giriş kutusu stillerini sağlayabilirsiniz. Bu stillerle şunları yapabilirsiniz:

- Listedeki dize aramalarını büyük/küçük harfe duyarlı olacak şekilde ayarlayın.

- Eğik çizgi ('/'), ters eğik çizgi ('\\') ve nokta ('. ') karakterlerini, sözcük sınırlayıcıları olarak kullanan bir Birleşik giriş kutusu denetimi oluşturun. Bu, kullanıcıların klavye kısayolunu CTRL + ok kullanarak Word 'e atlamasına izin verir.

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

##  <a name="ccomboboxex"></a>CComboBoxEx:: CComboBoxEx

`CComboBoxEx` nesnesi oluşturmak için bu üye işlevini çağırın.

```
CComboBoxEx();
```

##  <a name="create"></a>CComboBoxEx:: Create

Birleşik giriş kutusunu oluşturur ve `CComboBoxEx` nesnesine iliştirir.

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
Birleşik giriş kutusunun konumu ve boyutu olan bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine veya [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Birleşik giriş kutusunun üst penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine yönelik bir işaretçi (genellikle bir `CDialog`). NULL olmaması gerekir.

*NID*<br/>
Birleşik giriş kutusunun Denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda `CComboBoxEx` nesnesi oluşturun:

1. `CComboBoxEx` nesnesi oluşturmak için [CComboBoxEx](#ccomboboxex) öğesini çağırın.

1. Genişletilmiş Windows Birleşik giriş kutusunu oluşturan ve `CComboBoxEx` nesnesine ekleyen bu üye işlevini çağırın.

`Create`çağırdığınızda, MFC ortak denetimleri başlatır.

Birleşik giriş kutusunu oluşturduğunuzda, aşağıdaki Birleşik giriş kutusu stillerinden herhangi birini veya tümünü belirtebilirsiniz:

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

Pencereyi oluşturduğunuzda geçirilen diğer tüm stiller yok sayılır. `ComboBoxEx` denetimi de ek özellikler sağlayan Genişletilmiş stilleri destekler. Bu stiller, Windows SDK [ComboBoxEx denetimi genişletilmiş stillerinde](/windows/win32/Controls/comboboxex-control-extended-styles)açıklanmıştır. [Setil Dedstyle](#setextendedstyle)öğesini çağırarak bu stilleri ayarlayın.

Denetim ile genişletilmiş Windows stilleri kullanmak istiyorsanız, `Create`yerine [CreateEx](#createex) çağırın.

##  <a name="createex"></a>CComboBoxEx:: CreateEx

Genişletilmiş Birleşik giriş kutusu denetimi (alt pencere) oluşturmak ve `CComboBoxEx` nesnesiyle ilişkilendirmek için bu işlevi çağırın.

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
*PParentWnd*istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için `Create` yerine `CreateEx` kullanın.

`CreateEx`, *dwExStyle*tarafından belirtilen Genişletilmiş Windows stilleriyle denetimi oluşturur. [Setil dedstyle](#setextendedstyle)kullanarak genişletilmiş bir Birleşik giriş kutusu denetimine özgü genişletilmiş stilleri ayarlamanız gerekir. Örneğin, bu tür stilleri WS_EX_CONTEXTHELP olarak ayarlamak için `CreateEx` kullanın, ancak bu tür stilleri CBES_EX_CASESENSITIVE olarak ayarlamak için `SetExtendedStyle` kullanın. Daha fazla bilgi için, Windows SDK [ComboBoxEx denetimi genişletilmiş stillerinde](/windows/win32/Controls/comboboxex-control-extended-styles) başlıklı konuda açıklanan stillere bakın.

##  <a name="deleteitem"></a>CComboBoxEx::D Eleteıtem

`ComboBoxEx` denetiminden bir öğeyi kaldırır.

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

##  <a name="getcomboboxctrl"></a>CComboBoxEx:: GetComboBoxCtrl

`CComboBoxEx` nesnesi içindeki bir açılan kutu denetimine bir işaretçi almak için bu üye işlevi çağırın.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

`CComboBox` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CComboBoxEx` denetimi bir `CComboBox`kapsülleyen üst pencereden oluşur.

Dönüş değeri tarafından işaret edilen `CComboBox` nesnesi geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

##  <a name="geteditctrl"></a>CComboBoxEx:: GetEditCtrl

Birleşik giriş kutusu için düzenleme denetimine bir işaretçi almak için bu üye işlevi çağırın.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

[Cedıt](../../mfc/reference/cedit-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CComboBoxEx` denetimi, CBS_DROPDOWN stili ile oluşturulduğunda bir düzenleme kutusu kullanır.

Dönüş değeri tarafından işaret edilen `CEdit` nesnesi geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

##  <a name="getextendedstyle"></a>CComboBoxEx:: Getcdedstyle

Bir `CComboBoxEx` denetimi için kullanılan genişletilmiş stilleri almak için bu üye işlevi çağırın.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusu denetimi için kullanılan genişletilmiş stilleri içeren DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Bu stiller hakkında daha fazla bilgi için, bkz. Windows SDK [ComboBoxEx denetimi genişletilmiş stilleri](/windows/win32/Controls/comboboxex-control-extended-styles) .

##  <a name="getimagelist"></a>CComboBoxEx:: GetImageList

`CComboBoxEx` denetimi tarafından kullanılan görüntü listesine bir işaretçi almak için bu üye işlevi çağırın.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi. Başarısız olursa, bu üye işlevi NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri tarafından işaret edilen `CImageList` nesnesi geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

##  <a name="getitem"></a>CComboBoxEx:: GetItem

Belirli bir `ComboBoxEx` öğesi için öğe bilgilerini alır.

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

##  <a name="haseditchanged"></a>CComboBoxEx:: HasEditChanged

Kullanıcının `ComboBoxEx` düzenleme denetiminin içeriğini yazarak değiştirmeyeceğini belirler.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı denetimin düzenleme kutusuna yazmışsa sıfır dışında. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)ileti işlevlerini uygular.

##  <a name="insertitem"></a>CComboBoxEx:: InsertItem

`ComboBoxEx` denetimine yeni bir öğe ekler.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametreler

*pCBItem*<br/>
Öğe bilgilerini alacak bir [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısına yönelik işaretçi. Bu yapı öğe için geri çağırma bayrağı değerlerini içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni öğenin eklendiği Dizin; Aksi takdirde-1.

### <a name="remarks"></a>Açıklamalar

`InsertItem`çağırdığınızda, ana pencereye [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) bildirimine sahip bir [WM_NOTIFY](/windows/win32/controls/wm-notify) iletisi gönderilir.

##  <a name="setextendedstyle"></a>CComboBoxEx:: Setcdedstyle

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

##  <a name="setimagelist"></a>CComboBoxEx:: SetImageList

`ComboBoxEx` denetimi için bir görüntü listesi ayarlar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
`CComboBoxEx` denetimiyle birlikte kullanılacak görüntüleri içeren `CImageList` nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Daha önce `CComboBoxEx` denetimi tarafından kullanılan görüntüleri içeren bir [Ciımagelist](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi. Daha önce ayarlanmış bir görüntü listesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK açıklanan [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)ileti işlevlerini uygular. Varsayılan düzenleme denetiminin yüksekliğini değiştirirseniz, `SetImageList`çağırdıktan sonra denetiminizi yeniden boyutlandırmak için [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) Win32 işlevini çağırın veya düzgün şekilde gösterilmez.

Dönüş değeri tarafından işaret edilen `CImageList` nesnesi geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

##  <a name="setitem"></a>CComboBoxEx:: SetItem

`ComboBoxEx` denetimindeki bir öğenin özniteliklerini ayarlar.

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

##  <a name="setwindowtheme"></a>CComboBoxEx:: SetWindowTheme

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
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)
