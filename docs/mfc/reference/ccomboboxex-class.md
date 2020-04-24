---
title: CComboBoxEx Sınıfı
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
ms.openlocfilehash: a948d54be17103fa83848ff5f0e86dd2c522f0a3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754817"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx Sınıfı

Resim listeleri için destek sağlayarak açılan kutu denetimini genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Bir `CComboBoxEx` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComboBoxEx::Oluştur](#create)|Açılan kutuyu oluşturur ve `CComboBoxEx` nesneye bağlar.|
|[CComboBoxEx:CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri içeren bir açılan kutu oluşturur ve `ComboBoxEx` bir nesneye bağlar.|
|[CComboBoxEx::DeleteItem](#deleteitem)|Bir öğeyi `ComboBoxEx` denetimden kaldırır.|
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Alt açılan kutu denetimi için bir işaretçi alır.|
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Tutamacı denetimdenetimibölümüne `ComboBoxEx` alır.|
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|`ComboBoxEx` Denetim için kullanılan genişletilmiş stilleri alır.|
|[CComboBoxEx::GetImageList](#getimagelist)|Denetime atanan görüntü listesine `ComboBoxEx` bir işaretçi alır.|
|[CComboBoxEx::GetItem](#getitem)|Belirli `ComboBoxEx` bir öğenin madde bilgilerini alır.|
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Kullanıcının `ComboBoxEx` yazarak düzenleme denetiminin içeriğini değiştirip değiştirmediğini belirler.|
|[CComboBoxEx::InsertItem](#insertitem)|Denetime yeni bir `ComboBoxEx` öğe ekler.|
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Denetim içinde `ComboBoxEx` genişletilmiş stilleri ayarlar.|
|[CComboBoxEx::SetImageList](#setimagelist)|`ComboBoxEx` Denetim için bir resim listesi ayarlar.|
|[CComboBoxEx::SetItem](#setitem)|`ComboBoxEx` Denetimdeki bir öğenin özniteliklerini ayarlar.|
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Genişletilmiş açılan kutu denetiminin görsel stilini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Açılan `CComboBoxEx` kutu denetimleri oluşturmak için kullanarak, artık kendi resim çizim kodunuzu uygulamanız gerekmez. Bunun yerine, resim listesinden görüntülere erişmek için kullanın. `CComboBoxEx`

## <a name="image-list-support"></a>Resim Listesi Desteği

Standart bir açılan kutuda, açılan kutunun sahibi, açılan kutuyu sahibi çekme denetimi olarak oluşturarak görüntü çizmekten sorumludur. Kullandığınızda, `CComboBoxEx`çizim stillerini CBS_OWNERDRAWFIXED ve CBS_HASSTRINGS olarak ayarlamanız gerekmez, çünkü bunlar ima edilir. Aksi takdirde, çizim işlemleri gerçekleştirmek için kod yazmanız gerekir. Denetim, `CComboBoxEx` öğe başına en fazla üç görüntüyü destekler: biri seçili durum için, biri seçilmemiş durum için ve diğeri de bindirme görüntüsü için.

## <a name="styles"></a>Stiller

`CComboBoxEx`CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST ve WS_CHILD stillerini destekler. Pencereyi oluştururken geçirilen diğer tüm stiller denetim tarafından yoksayılır. Pencere oluşturulduktan sonra, `CComboBoxEx` üye işlev [SetExtendedStyle](#setextendedstyle)çağırarak diğer açılan kutu stilleri sağlayabilir. Bu stiller ile şunları yapabilirsiniz:

- Dizi aramalarını büyük/küçük harf duyarlı olacak şekilde listedeki olarak ayarlayın.

- Kesme ('/'), ters eğik çizgi ('\\') ve dönem ('.') karakterlerini sözcük sınırlayıcıları olarak kullanan bir açılan kutu denetimi oluşturun. Bu, klavye kısayolu CTRL+ ARROW'u kullanarak kullanıcıların kelimeden kelimeye atlamalarına olanak tanır.

- Açılan kutu denetimini görüntülenecek veya görüntülemeyecek şekilde ayarlayın. Görüntü görüntülenmiyorsa, açılan kutu görüntüyü barındıran metin girintisini kaldırabilir.

- İçerdiği daha geniş açılan kutuyu klipslesin diye boyutlandırma da dahil olmak üzere dar bir açılan kutu denetimi oluşturun.

Bu stil bayrakları [CComboBoxEx kullanarak](../../mfc/using-ccomboboxex.md)daha fazla açıklanmıştır.

## <a name="item-retention-and-callback-item-attributes"></a>Öğe Bekletme ve Geri Arama Öğe Öznitelikleri

Öğeler ve resimler, girinti değerleri ve metin dizeleri gibi öğe bilgileri, Windows SDK'da açıklandığı gibi Win32 yapısı [COMBOBOXEXITEM'de](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)depolanır. Yapı, geri arama bayraklarına karşılık gelen üyeleri de içerir.

Ayrıntılı ve kavramsal bir tartışma için [bkz.](../../mfc/using-ccomboboxex.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ccombobox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a>CComboBoxEx::CComboBoxEx

Bir `CComboBoxEx` nesne oluşturmak için bu üye işlevi çağırın.

```
CComboBoxEx();
```

## <a name="ccomboboxexcreate"></a><a name="create"></a>CComboBoxEx::Oluştur

Açılan kutuyu oluşturur ve `CComboBoxEx` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Açılan kutuya uygulanan açılan kutu stillerinin birleşimini belirtir. Stiller hakkında daha fazla bilgi için aşağıdaki **Açıklamalar'a** bakın.

*Rect*<br/>
Açılan kutunun konumu ve boyutu olan [bir CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına yapılan başvuru.

*pParentWnd*<br/>
Açılan kutunun ana penceresi olan [CWnd](../../mfc/reference/cwnd-class.md) nesnesine işaretçi (genellikle bir). `CDialog` NULL olmamalıdır.

*Nıd*<br/>
Açılan kutunun denetim kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki `CComboBoxEx` adımda nesne oluşturun:

1. Bir `CComboBoxEx` nesne oluşturmak için [CComboBoxEx'i](#ccomboboxex) arayın.

1. Genişletilmiş Windows açılan kutusunu oluşturan ve `CComboBoxEx` nesneye iliştiren bu üye işlevi arayın.

Arama `Create`yaptığınızda, MFC ortak denetimleri başharflekarşılar.

Açılan kutuyu oluşturduğunuzda, aşağıdaki açılan kutu stillerinden birini veya tümlerini belirtebilirsiniz:

- CBS_SIMPLE

- Cbs_dropdown

- Cbs_dropdownlıst

- CBS_AUTOHSCROLL

- Ws_chıld

Pencereyi oluştururken geçirilen diğer tüm stiller yoksayılır. Denetim, `ComboBoxEx` ek özellikler sağlayan genişletilmiş stilleri de destekler. Bu stiller, Windows SDK'da [ComboBoxEx denetimigenişletilmiş stilleri](/windows/win32/Controls/comboboxex-control-extended-styles)açıklanmıştır. [SetExtendedStyle'ı](#setextendedstyle)arayarak bu stilleri ayarlayın.

Genişletilmiş windows stillerini denetiminiz ile kullanmak istiyorsanız, `Create`'' yerine [CreateEx'i](#createex) arayın.

## <a name="ccomboboxexcreateex"></a><a name="createex"></a>CComboBoxEx:CreateEx

Genişletilmiş bir açılan kutu denetimi (alt pencere) oluşturmak ve `CComboBoxEx` nesneyle ilişkilendirmek için bu işlevi arayın.

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
Açılan kutu denetiminin stili. Stil listesi için [oluştur'a](#create) bakın.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş `Create` stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak yerine kullanın.

`CreateEx`*dwExStyle*tarafından belirtilen genişletilmiş Windows stilleri ile denetim oluşturur. [SetExtendedStyle'ı](#setextendedstyle)kullanarak genişletilmiş açılan kutu denetimine özgü genişletilmiş stilleri ayarlamanız gerekir. Örneğin, WS_EX_CONTEXTHELP `CreateEx` gibi stilleri ayarlamak için `SetExtendedStyle` kullanın, ancak CBES_EX_CASESENSITIVE gibi stilleri ayarlamak için kullanın. Daha fazla bilgi için, Windows SDK'da [ComboBoxEx Denetimi Genişletilmiş Stiller'de](/windows/win32/Controls/comboboxex-control-extended-styles) açıklanan stillelere bakın.

## <a name="ccomboboxexdeleteitem"></a><a name="deleteitem"></a>CComboBoxEx::DeleteItem

Bir öğeyi `ComboBoxEx` denetimden kaldırır.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
Kaldırılacak öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Denetimde kalan öğe sayısı. *iIndex* geçersizse, işlev CB_ERR döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [ileti nin CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)işlevselliğini uygular. DeleteItem'i aradiğinizde, ana pencereye CBEN_DELETEITEM bildirimi içeren bir [WM_NOTIFY](/windows/win32/controls/wm-notify) ileti gönderilir.

## <a name="ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl

Bir `CComboBoxEx` nesne içinde açılan kutu denetimi için bir işaretçi almak için bu üye işlevi arayın.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CComboBox` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Denetim, `CComboBoxEx` bir `CComboBox`.

İade `CComboBox` değeri tarafından işaret edilen nesne geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl

Açılan kutu için denetim ekive işaretçi almak için bu üye işlevi arayın.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

[CEdit](../../mfc/reference/cedit-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Denetim, `CComboBoxEx` CBS_DROPDOWN stiliyle oluşturulduğunda bir denetim kutusu kullanır.

İade `CEdit` değeri tarafından işaret edilen nesne geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle

Denetim için kullanılan genişletilmiş stilleri almak için `CComboBoxEx` bu üye işlevi arayın.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan kutu denetimi için kullanılan genişletilmiş stilleri içeren DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Bu stiller hakkında daha fazla bilgi için Windows SDK'daki [ComboBoxEx Denetim Genişletilmiş Stilleri'ne](/windows/win32/Controls/comboboxex-control-extended-styles) bakın.

## <a name="ccomboboxexgetimagelist"></a><a name="getimagelist"></a>CComboBoxEx::GetImageList

`CComboBoxEx` Denetim tarafından kullanılan görüntü listesine işaretçi almak için bu üye işlevi arayın.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi. Başarısız olursa, bu üye işlev NULL döndürür.

### <a name="remarks"></a>Açıklamalar

İade `CImageList` değeri tarafından işaret edilen nesne geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexgetitem"></a><a name="getitem"></a>CComboBoxEx::GetItem

Belirli `ComboBoxEx` bir öğenin madde bilgilerini alır.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametreler

*pCBItem*<br/>
Madde bilgilerini alacak bir [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı [gibi, CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)iletinin işlevselliğini uygular.

## <a name="ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a>CComboBoxEx::HasEditChanged

Kullanıcının `ComboBoxEx` yazarak düzenleme denetiminin içeriğini değiştirip değiştirmediğini belirler.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı denetimin denetim kutusuna yazdıysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi, [ileti CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)işlevselliğini uygular.

## <a name="ccomboboxexinsertitem"></a><a name="insertitem"></a>CComboBoxEx::InsertItem

Denetime yeni bir `ComboBoxEx` öğe ekler.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametreler

*pCBItem*<br/>
Madde bilgilerini alacak bir [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısına işaretçi. Bu yapı, öğe için geri arama bayrak değerleri içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa yeni öğenin eklendiği dizin; aksi takdirde -1.

### <a name="remarks"></a>Açıklamalar

Aradiğinizde, üst pencereye [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) bildirimi içeren WM_NOTIFY bir ileti gönderilir. [WM_NOTIFY](/windows/win32/controls/wm-notify) `InsertItem`

## <a name="ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a>CComboBoxEx::SetExtendedStyle

Açılan kutu genişletilmiş denetimi için kullanılan genişletilmiş stilleri ayarlamak için bu üye işlevi arayın.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>Parametreler

*dwExMask*<br/>
*dwExStyles* hangi stillerin etkileneceğini gösteren bir DWORD değeri. Sadece *dwExMask* genişletilmiş stilleri değiştirilecektir. Diğer tüm stiller olduğu gibi korunacaktır. Bu parametre sıfır ise, *dwExStyles'taki* tüm stiller etkilenir.

*dwExStyles*<br/>
Denetim için ayarlanacak genişletilmiş stilleri oluşturan açılan kutu denetimini içeren bir DWORD değeri.

### <a name="return-value"></a>Dönüş Değeri

Denetim için daha önce kullanılan genişletilmiş stilleri içeren bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Bu stiller hakkında daha fazla bilgi için Windows SDK'daki [ComboBoxEx Denetim Genişletilmiş Stilleri'ne](/windows/win32/Controls/comboboxex-control-extended-styles) bakın.

Genişletilmiş windows stilleri ile genişletilmiş bir açılan kutu genişletilmiş denetim oluşturmak için [CreateEx'i](#createex)kullanın.

## <a name="ccomboboxexsetimagelist"></a><a name="setimagelist"></a>CComboBoxEx::SetImageList

`ComboBoxEx` Denetim için bir resim listesi ayarlar.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametreler

*pImageList*<br/>
Denetimle birlikte `CImageList` kullanılacak görüntüleri içeren bir nesneye işaretçi. `CComboBoxEx`

### <a name="return-value"></a>Dönüş Değeri

Denetim tarafından daha önce kullanılan görüntüleri içeren bir `CComboBoxEx` [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi. Daha önce görüntü listesi ayarlıdeğilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu üye [işlev,](/windows/win32/Controls/cbem-setimagelist)Windows SDK'da açıklandığı gibi CBEM_SETIMAGELIST iletinin işlevselliğini uygular. Varsayılan edit denetiminin yüksekliğini değiştirirseniz, siz aradıktan sonra denetiminizi yeniden boyutlandırmak için Win32 işlevi [SetWindowPos'u](/windows/win32/api/winuser/nf-winuser-setwindowpos) `SetImageList`arayın veya düzgün görüntülenmez.

İade `CImageList` değeri tarafından işaret edilen nesne geçici bir nesnedir ve bir sonraki boşta işleme süresi boyunca yok edilir.

## <a name="ccomboboxexsetitem"></a><a name="setitem"></a>CComboBoxEx::SetItem

`ComboBoxEx` Denetimdeki bir öğenin özniteliklerini ayarlar.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametreler

*pCBItem*<br/>
Madde bilgilerini alacak bir [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [ileti CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)işlevselliğini uygular.

## <a name="ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a>CComboBoxEx::SetWindowTheme

Genişletilmiş açılan kutu denetiminin görsel stilini ayarlar.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametreler

*pszSubAppName*<br/>
Ayarlanacak genişletilmiş açılan kutu görsel stilini içeren Unicode dizesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İade değeri kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) iletinin işlevselliğini taklit eder.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)
