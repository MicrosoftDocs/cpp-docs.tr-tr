---
title: CCheckListBox sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: f8c725ea30754a42ce3045f1160b7a09c4481e39
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507344"
---
# <a name="cchecklistbox-class"></a>CCheckListBox sınıfı

Windows Denetim listesi kutusunun işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCheckListBox:: CCheckListBox](#cchecklistbox)|Bir `CCheckListBox` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCheckListBox:: Create](#create)|Windows Denetim listesi kutusunu oluşturur ve `CCheckListBox` nesneye ekler.|
|[CCheckListBox::D rawItem](#drawitem)|Bir sahip çizimi liste kutusunun görsel yönü değiştiğinde Framework tarafından çağırılır.|
|[CCheckListBox:: Enable](#enable)|Denetim listesi kutusu öğesini etkinleştirilir veya devre dışı bırakır.|
|[CCheckListBox:: GetCheck](#getcheck)|Bir öğenin onay kutusunun durumunu alır.|
|[CCheckListBox:: GetCheckStyle](#getcheckstyle)|Denetimin onay kutularının stilini alır.|
|[CCheckListBox:: IsEnabled](#isenabled)|Bir öğenin etkin olup olmadığını belirler.|
|[CCheckListBox:: MeasureItem](#measureitem)|Sahip çizim stili olan bir liste kutusu oluşturulduğunda Framework tarafından çağırılır.|
|[CCheckListBox:: OnGetCheckPosition](#ongetcheckposition)|Bir öğenin onay kutusunun konumunu almak için Framework tarafından çağırılır.|
|[CCheckListBox:: SetCheck](#setcheck)|Bir öğenin onay kutusunun durumunu ayarlar.|
|[CCheckListBox:: SetCheckStyle](#setcheckstyle)|Denetimin onay kutularının stilini ayarlar.|

## <a name="remarks"></a>Açıklamalar

"Denetim listesi kutusu" dosya adları gibi öğelerin bir listesini görüntüler. Listedeki her öğe, kullanıcının denetleyip temizle, temizle, temizle, işaret edip temizlebir onay kutusu içerir.

`CCheckListBox`yalnızca sahibi tarafından çizilen denetimler içindir çünkü liste metin dizeleri içeriyor. En basit noktada, bir denetim listesi kutusu metin dizeleri ve onay kutuları içerir, ancak bir metin olması gerekmez. Örneğin, her öğenin yanında bir onay kutusu olan küçük bit eşlemlerin listesine sahip olabilirsiniz.

Kendi denetim listesi kutusunu oluşturmak için, kendi sınıfınızı ' den `CCheckListBox`türetmeniz gerekir. Kendi sınıfınızı türetmek için, türetilmiş sınıf için bir Oluşturucu yazın ve ardından öğesini çağırın `Create`.

Bir liste kutusu tarafından üst öğeye (genellikle [CDialog](../../mfc/reference/cdialog-class.md)'dan türetilmiş bir sınıf) gönderilen Windows bildirim iletilerini işlemek istiyorsanız, her ileti için üst sınıfa bir ileti eşleme girişi ve ileti işleyici üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

Bildirimde (kimlik, memberFxn) **\_**

Burada `id` bildirimi gönderen denetimin alt pencere kimliğini belirtir ve `memberFxn` bildirimi işlemek için yazdığınız üst üye işlevinin adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

`afx_msg void memberFxn();`

Özellikle `CCheckListBox` ilgili olan yalnızca bir ileti eşleme girişi vardır (ancak aynı zamanda, [clienstbox](../../mfc/reference/clistbox-class.md)için ileti eşleme girişlerine bakın):

- ON_CLBN_CHKCHANGE Kullanıcı bir öğenin onay kutusunun durumunu değiştirdi.

Denetim listesi kutusu varsayılan bir denetim listesi kutusu ise (her birinin solunda varsayılan boyutlu onay kutularına sahip dizelerin listesi), denetim listesi kutusunu çizmek için varsayılan [CCheckListBox::D rawitem](#drawitem) kullanabilirsiniz. Aksi takdirde [Clienstbox:: CompareItem](../../mfc/reference/clistbox-class.md#compareitem) Işlevini ve [cchecklistbox::D Rawitem](#drawitem) ve [CCheckListBox:: MeasureItem](#measureitem) işlevlerini geçersiz kılmanız gerekir.

Bir iletişim kutusu şablonundan ya da doğrudan kodunuzda bir denetim listesi kutusu oluşturabilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cchecklistbox"></a>CCheckListBox:: CCheckListBox

Bir `CCheckListBox` nesnesi oluşturur.

```
CCheckListBox();
```

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CCheckListBox` nesne oluşturursunuz. İlk olarak, öğesinden `CCheckListBox`türetilmiş bir sınıf tanımlayın, `Create`sonra Windows Denetim listesi kutusunu başlatan `CCheckListBox` ve nesneyi nesnesine iliştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

##  <a name="create"></a>CCheckListBox:: Create

Windows Denetim listesi kutusunu oluşturur ve `CCheckListBox` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Denetim listesi kutusunun stilini belirtir. Stil, LBS_HASSTRINGS ve LBS_OWNERDRAWFIXED (listedeki tüm öğeler aynı yükseklikte) ya da LBS_OWNERDRAWVARIABLE (listedeki öğeler farklı yüksekliklerdir) olmalıdır. Bu stil, LBS_USETABSTOPS hariç diğer [liste kutusu stilleriyle](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) birleştirilebilir.

*Rect*<br/>
Denetim listesi-kutusunun boyutunu ve konumunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi ya da bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Denetim listesi kutusunun üst penceresini (genellikle bir `CDialog` nesne) belirtir. NULL olmaması gerekir.

*NID*<br/>
Denetim listesi kutusunun Denetim KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CCheckListBox` nesne oluşturursunuz. İlk olarak, öğesinden `CcheckListBox` türetilmiş bir sınıf tanımlayın ve `Create`sonra Windows Denetim listesi kutusunu başlatan `CCheckListBox`ve bunu öğesine iliştirir. Örnek için bkz. [CCheckListBox:: CCheckListBox](#cchecklistbox) .

[](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) [](../../mfc/reference/cwnd-class.md#oncreate) [](../../mfc/reference/cwnd-class.md#onnccalcsize) [](../../mfc/reference/cwnd-class.md#onnccreate)Yürütüldüğünde, Windows, WM_NCCREATE, WM_CREATE, WM_NCCALCSIZE ve WM_GETMINMAXINFO iletilerini denetim listesi-Box denetimine gönderir. `Create`

Bu iletiler, `CWnd` temel sınıftaki [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)ve [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) member işlevleri tarafından varsayılan olarak işlenir. Varsayılan ileti işlemeyi genişletmek için, türetilmiş sınıfınıza bir ileti haritası ekleyin ve önceki ileti işleyici üye işlevlerini geçersiz kılın. Yeni `OnCreate`bir sınıf için gerekli başlatmayı gerçekleştirmek üzere, örneğin, öğesini geçersiz kılın.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir denetim listesi kutusu denetimine uygulayın:

- WS_CHILD her zaman

- WS_VISIBLE genellikle

- WS_DISABLED nadiren

- Dikey kaydırma çubuğunu eklemek Için WS_VSCROLL

- Yatay kaydırma çubuğu eklemek Için WS_HSCROLL

- WS_GROUP denetimleri

- WS_TABSTOP bu denetime sekmeye izin vermek Için

##  <a name="drawitem"></a>CCheckListBox::D rawItem

Sahip tarafından çizilmiş bir denetim listesi kutusunun görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Gerekli çizim türü hakkında bilgi içeren [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapının ve `itemState` üyeleri gerçekleştirilecek çizim eylemini tanımlar. `itemAction` `DRAWITEMSTRUCT`

Varsayılan olarak, bu işlev varsayılan bir onay kutusu listesi çizer, bu, her biri varsayılan boyutlu bir onay kutusu olan dizelerin listesinden oluşur. CheckBox listesinin boyutu [Create](#create)içinde belirtilen bir değer.

Dize olmayan listelerle, değişken yükseklikli öğelerle veya sol tarafta olmayan onay kutularına sahip denetim listesi kutuları gibi, varsayılan olmayan sahip çizim denetim listesi kutularının çizimini uygulamak için bu üye işlevini geçersiz kılın. Uygulamanın, bu üye işlevin sonlandırılması için *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

Denetim listesi kutusu öğeleri aynı yükseklikte değilse, denetim listesi kutusu stili (içinde `Create`belirtilen) * * LBS_OWNERVARIABLE olmalıdır ve [MeasureItem](#measureitem) işlevini geçersiz kılmanız gerekir.

##  <a name="enable"></a>CCheckListBox:: Enable

Denetim listesi kutusu öğesini etkinleştirmek veya devre dışı bırakmak için bu işlevi çağırın.

```
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Etkinleştirilecek denetim listesi kutusu öğesinin dizini.

*bEnabled*<br/>
Öğenin etkin veya devre dışı olduğunu belirtir.

##  <a name="getcheck"></a>CCheckListBox:: GetCheck

Belirtilen onay kutusunun durumunu alır.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda bulunan onay kutusunun sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen onay kutusunun durumu. Aşağıdaki tabloda olası değerler listelenmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|BST_CHECKED|Onay kutusu işaretlenir.|
|BST_UNCHECKED|Onay kutusu işaretli değil.|
|BST_INDETERMINATE|Onay kutusu durumu belirsiz.|

##  <a name="getcheckstyle"></a>CCheckListBox:: GetCheckStyle

Denetim listesi kutusunun stilini almak için bu işlevi çağırın.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin onay kutularının stili.

### <a name="remarks"></a>Açıklamalar

Olası stiller hakkında daha fazla bilgi için bkz. [SetCheckStyle](#setcheckstyle).

##  <a name="isenabled"></a>CCheckListBox:: IsEnabled

Bir öğenin etkin olup olmadığını öğrenmek için bu işlevi çağırın.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Öğe etkinse sıfır dışı; Aksi takdirde 0.

##  <a name="measureitem"></a>CCheckListBox:: MeasureItem

Varsayılan olmayan bir stil içeren bir denetim listesi oluşturulduğunda Framework tarafından çağırılır.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) yapısına yönelik uzun bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu üye işlevi hiçbir şey yapmaz. Bu üye işlevini geçersiz kılın ve pencere denetim `MEASUREITEMSTRUCT` kutusu öğeleri boyutlarını bilgilendirmek için yapıyı girin. Denetim listesi kutusu [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) stiliyle oluşturulduysa, çerçeve liste kutusundaki her öğe için bu üye işlevini çağırır. Aksi takdirde, bu üye yalnızca bir kez çağrılır.

##  <a name="ongetcheckposition"></a>CCheckListBox:: OnGetCheckPosition

Framework, bir öğedeki onay kutusunun konumunu ve boyutunu almak için bu işlevi çağırır.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>Parametreler

*Rectıtem*<br/>
Liste öğesinin konumu ve boyutu.

*rectCheckBox*<br/>
Bir öğenin onay kutusunun varsayılan konumu ve boyutu.

### <a name="return-value"></a>Dönüş Değeri

Bir öğenin onay kutusunun konumu ve boyutu.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama yalnızca onay kutusunun (`rectCheckBox`) varsayılan konumunu ve boyutunu döndürür. Varsayılan olarak, bir onay kutusu öğenin sol üst köşesine hizalanır ve standart onay kutusu boyutudur. Onay kutularının sağ tarafta olmasını veya daha büyük ya da daha küçük bir onay kutusu olmasını istediğiniz durumlar olabilir. Bu durumlarda, öğe içindeki `OnGetCheckPosition` onay kutusu konumunu ve boyutunu değiştirmek için geçersiz kılın.

##  <a name="setcheck"></a>CCheckListBox:: SetCheck

Belirtilen onay kutusunun durumunu ayarlar.

```
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Liste kutusunda bulunan onay kutusunun sıfır tabanlı dizini.

*Nhatayla*<br/>
Belirtilen onay kutusu için düğme durumu. Olası değerler için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, *nCheck* parametresi için olası değerler listelenmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|BST_CHECKED|Belirtilen onay kutusunu seçin.|
|BST_UNCHECKED|Belirtilen onay kutusunu temizleyin.|
|BST_INDETERMINATE|Belirtilen onay kutusu durumunu belirsiz olarak ayarlayın.<br /><br /> Bu durum yalnızca onay kutusu stili BS_AUTO3STATE veya BS_3STATE olduğunda kullanılabilir. Daha fazla bilgi için bkz. [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).|

##  <a name="setcheckstyle"></a>CCheckListBox:: SetCheckStyle

Denetim listesi kutusundaki onay kutularının stilini ayarlamak için bu işlevi çağırın.

```
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
Denetim listesi kutusundaki onay kutularının stilini belirler.

### <a name="remarks"></a>Açıklamalar

Geçerli stiller şunlardır:

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

Bu stillerle ilgili bilgi için bkz. [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)
