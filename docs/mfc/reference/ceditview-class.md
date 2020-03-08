---
title: CEditView sınıfı
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: e9b7dea980e607c776e2d50c679042c765080fdb
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78872501"
---
# <a name="ceditview-class"></a>CEditView sınıfı

Bir Windows düzenleme denetiminin işlevselliğini sağlayan ve basit metin düzenleyici işlevselliği uygulamak için kullanılabilen bir görünüm sınıfı türü.

## <a name="syntax"></a>Sözdizimi

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CEditView:: CEditView](#ceditview)|`CEditView`türünde bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CEditView:: FindText](#findtext)|Metin içinde bir dize arar.|
|[CEditView:: GetBufferLength](#getbufferlength)|Karakter arabelleğinin uzunluğunu alır.|
|[CEditView:: GetEditCtrl](#geteditctrl)|Bir `CEditView` nesnesinin `CEdit` bölümüne (Windows düzenleme denetimi) erişim sağlar.|
|[CEditView:: GetPrinterFont](#getprinterfont)|Geçerli yazıcı yazı tipini alır.|
|[CEditView:: GetSelectedText](#getselectedtext)|Geçerli metin seçimini alır.|
|[CEditView:: LockBuffer](#lockbuffer)|Arabelleği kilitler.|
|[CEditView::P rintInsideRect](#printinsiderect)|Metni belirli bir dikdörtgen içinde işler.|
|[CEditView:: Serializsilinebilir w](#serializeraw)|`CEditView` nesnesini diske ham metin olarak seri hale getirir.|
|[CEditView:: SetPrinterFont](#setprinterfont)|Yeni bir yazıcı yazı tipi ayarlar.|
|[CEditView:: Settabstop](#settabstops)|Ekran görüntüleme ve yazdırma için sekme duraklarının her ikisini de ayarlar.|
|[CEditView:: UnlockBuffer](#unlockbuffer)|Arabelleğin kilidini açar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CEditView:: onsonra](#onfindnext)|Bir metin dizesinin sonraki tekrarını bulur.|
|[CEditView:: OnReplaceAll](#onreplaceall)|Belirli bir dizenin tüm oluşumlarını yeni bir dizeyle değiştirir.|
|[CEditView:: OnReplaceSel](#onreplacesel)|Geçerli seçimi değiştirir.|
|[CEditView:: OnTextNotFound](#ontextnotfound)|Bir bul işlemi başka bir metinle eşleşmediğinde çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CEditView::d wStyleDefault](#dwstyledefault)|`CEditView`türündeki nesnelerin varsayılan stili.|

## <a name="remarks"></a>Açıklamalar

`CEditView` sınıfı aşağıdaki ek işlevleri sağlar:

- Yazdır.

- Bul ve Değiştir.

Sınıf `CEditView` sınıf `CView`türevi olduğundan, sınıf `CEditView` nesneleri belgeler ve belge şablonlarıyla birlikte kullanılabilir.

Her `CEditView` denetiminin metni kendi genel bellek nesnesinde tutulur. Uygulamanızın herhangi bir sayıda `CEditView` nesnesi olabilir.

Yukarıda listelenen ekleme işlevleriyle bir düzenleme penceresi istiyorsanız veya basit metin düzenleyici işlevselliği istiyorsanız `CEditView` türünde nesneler oluşturun. Bir `CEditView` nesnesi, bir pencerenin tüm istemci alanının kaplamasını sağlayabilir. Temel işlevleri eklemek veya değiştirmek ya da bir belge şablonuna eklenebilen sınıfları bildirmek için `CEditView` ' den kendi sınıflarınızı türetebilirsiniz.

`CEditView` sınıfının varsayılan uygulanması şu komutları işler: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT ve ID_FILE_PRINT.

`CEditView` için varsayılan karakter sınırı (1024 \* 1024-1 = 1048575). Bu, temeldeki düzenleme denetiminin EM_LIMITTEXT işlevi çağırarak değiştirilebilir. Ancak, sınırlar işletim sistemine ve düzenleme denetiminin türüne (tek veya çok satırlı) bağlı olarak farklılık de vardır. Bu limitlerin hakkında daha fazla bilgi için bkz. [EM_LIMITTEXT](/windows/win32/Controls/em-limittext).

Denetiinizde bu sınırı değiştirmek için, `CEditView` sınıfınızın `OnCreate()` işlevini geçersiz kılın ve aşağıdaki kod satırını ekleyin:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

`CEditView` türündeki nesneler (veya `CEditView`türetilmiş türler) aşağıdaki sınırlamalara sahiptir:

- `CEditView`, ne görmelerinizi (WYSıWYG) düzenlemenizi, doğru uygulamaz. Ekranda okunabilirlik ve eşleşen yazılı çıktı arasında seçim olduğunda, ekran okunabilirlik için OptIn `CEditView`.

- `CEditView`, yalnızca tek bir yazı tipinde metin görüntüleyebilir. Özel karakter biçimlendirme desteklenmez. Daha fazla özellik için bkz. sınıf [CRichEditView](../../mfc/reference/cricheditview-class.md) .

- `CEditView` içerebileceği metin miktarı sınırlıdır. Sınırlar `CEdit` denetimi ile aynıdır.

`CEditView`hakkında daha fazla bilgi için bkz. [MFC 'de bulunan türetilmiş Görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

##  <a name="ceditview"></a>CEditView:: CEditView

`CEditView`türünde bir nesne oluşturur.

```
CEditView();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, düzenleme denetimi kullanılmadan önce [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) işlevini çağırmanız gerekir. `CEditView` bir sınıf türetirsiniz ve `CWinApp::AddDocTemplate`kullanarak şablona eklerseniz, çerçeve hem bu oluşturucuyu hem de `Create` işlevini çağırır.

##  <a name="dwstyledefault"></a>CEditView::d wStyleDefault

`CEditView` nesnesinin varsayılan stilini içerir.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Açıklamalar

`CEditView` nesnesinin varsayılan stilini almak için bu statik üyeyi `Create` işlevinin *dwStyle* parametresi olarak geçirin.

##  <a name="findtext"></a>CEditView:: FindText

`CEditView` nesnesinin metin arabelleğini aramak için `FindText` işlevini çağırın.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunan metin.

*bNext*<br/>
Aramanın yönünü belirtir. DOĞRU ise, arama yönü arabelleğin sonuna doğru olur. FALSE ise, arama yönü arabelleğin başına doğru olur.

*bCase*<br/>
Aramanın büyük/küçük harfe duyarlı olup olmadığını belirtir. DOĞRU ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değildir.

### <a name="return-value"></a>Dönüş Değeri

Arama metni bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Geçerli seçimden başlayarak, *bNext*tarafından belirtilen yönde ve *bCase*tarafından belirtilen büyük/küçük harf duyarlılığı ile *lpszFind*tarafından belirtilen metin için arabellekteki metni arar. Metin bulunursa, seçimi bulunan metne ayarlar ve sıfır dışında bir değer döndürür. Metin bulunamazsa, işlev 0 döndürür.

`FindText`çağıran `OnFindNext`geçersiz kılmadığınız müddetçe normalde `FindText` işlevini çağırmanız gerekmez.

##  <a name="getbufferlength"></a>CEditView:: GetBufferLength

Null Sonlandırıcı dahil değil, düzenleme denetimi arabelleğinde Şu anda bulunan karakter sayısını almak için bu üye işlevi çağırın.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekteki dizenin uzunluğu.

##  <a name="geteditctrl"></a>CEditView:: GetEditCtrl

Düzenleme görünümü tarafından kullanılan düzenleme denetimine başvuru almak için `GetEditCtrl` çağırın.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CEdit` nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu denetim [Cedıt](../../mfc/reference/cedit-class.md)türünde olduğundan, Windows düzenleme denetimini doğrudan `CEdit` üye işlevleri kullanarak değiştirebilirsiniz.

> [!CAUTION]
>  `CEdit` nesnesinin kullanılması, temeldeki Windows düzenleme denetiminin durumunu değiştirebilir. Örneğin, `CEditView`, bu ayarları hem düzenleme denetiminde hem de baskıda kullanılmak üzere önbelleğe aldığından, [Cedıt:: Settabstop](../../mfc/reference/cedit-class.md#settabstops) işlevini kullanarak sekme ayarlarını değiştirmemelisiniz. Bunun yerine [CEditView:: Settabstop](#settabstops)kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>CEditView:: GetPrinterFont

Geçerli yazıcı yazı tipini açıklayan bir [CFont](../../mfc/reference/cfont-class.md) nesnesine bir işaretçi almak için `GetPrinterFont` çağırın.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazıcı yazı tipini belirten `CFont` nesnesine yönelik bir işaretçi; Yazıcı yazı tipi ayarlanmamışsa NULL. İşaretçi geçici olabilir ve daha sonra kullanılmak üzere depolanmamalıdır.

### <a name="remarks"></a>Açıklamalar

Yazıcı yazı tipi ayarlanmamışsa, `CEditView` sınıfının varsayılan yazdırma davranışı, görüntüleme için kullanılan yazı tipini kullanarak yazdırılır.

Geçerli yazıcı yazı tipini öğrenmek için bu işlevi kullanın. İstenen yazıcı yazı tipi değilse, değiştirmek için [CEditView:: SetPrinterFont](#setprinterfont) kullanın.

##  <a name="getselectedtext"></a>CEditView:: GetSelectedText

Seçili metni bir `CString` nesnesine kopyalamak için `GetSelectedText` çağırın, seçimin sonuna kadar veya seçimdeki ilk satır başı karakterden önce gelen karakter.

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Parametreler

*strResult*<br/>
Seçili metni alacak `CString` nesnesine bir başvuru.

##  <a name="lockbuffer"></a>CEditView:: LockBuffer

Arabelleğin işaretçisini almak için bu üye işlevini çağırın. Arabellek değiştirilmemelidir.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetiminin arabelleğine yönelik bir işaretçi.

##  <a name="onfindnext"></a>CEditView:: onsonra

*LpszFind*tarafından belirtilen metin için arabellekteki metni, *bCase*tarafından büyük/küçük harf duyarlılığı belirtilmiş şekilde *bNext*tarafından belirtilen yönde arar.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunan metin.

*bNext*<br/>
Aramanın yönünü belirtir. DOĞRU ise, arama yönü arabelleğin sonuna doğru olur. FALSE ise, arama yönü arabelleğin başına doğru olur.

*bCase*<br/>
Aramanın büyük/küçük harfe duyarlı olup olmadığını belirtir. DOĞRU ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değildir.

### <a name="remarks"></a>Açıklamalar

Arama, geçerli seçimin başlangıcında başlar ve [FindText](#findtext)çağrısıyla gerçekleştirilir. Varsayılan uygulamada, `OnFindNext` metin bulunamazsa [OnTextNotFound](#ontextnotfound) ' ı çağırır.

`CEditView`türetilmiş bir nesnenin metni arama şeklini değiştirmek için `OnFindNext` geçersiz kılın. `CEditView`, Kullanıcı standart bul iletişim kutusunda Sonrakini Bul düğmesini seçtiğinde `OnFindNext` çağırır.

##  <a name="onreplaceall"></a>CEditView:: OnReplaceAll

`CEditView`, Kullanıcı standart Değiştir iletişim kutusundaki Tümünü Değiştir düğmesini seçtiğinde `OnReplaceAll` çağırır.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunan metin.

*lpszReplace*<br/>
Arama metninin yerini alacak metin.

*bCase*<br/>
Aramanın büyük/küçük harfe duyarlı olup olmadığını belirtir. DOĞRU ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değildir.

### <a name="remarks"></a>Açıklamalar

`OnReplaceAll`, *bCase*tarafından belirtilen büyük/küçük harf duyarlılığı ile *lpszFind*tarafından belirtilen metin için arabellekteki metni arar. Arama, geçerli seçimin başlangıcında başlar. Arama metninin her bulunduğu her seferinde, bu işlev metnin *lpszReplace*tarafından belirtilen metinle değiştirir. Arama, [FindText](#findtext)çağrısıyla gerçekleştirilir. Varsayılan uygulamada [OnTextNotFound](#ontextnotfound) , metin bulunamazsa çağırılır.

Geçerli seçim *lpszFind*ile eşleşmiyorsa, seçim *lpszFind* tarafından belirtilen metnin ilk oluşumuna güncelleştirilir ve bir değiştirme gerçekleştirilmez. Bu, kullanıcının, seçimi değiştirilmekte olan metinle eşleşmediği zaman ne yapmak istediğiyle ilgili olduğunu onaylamasını sağlar.

`CEditView`türetilmiş bir nesnenin metnin yerini değiştirme biçimini değiştirmek için `OnReplaceAll` geçersiz kılın.

##  <a name="onreplacesel"></a>CEditView:: OnReplaceSel

`CEditView`, Kullanıcı standart Değiştir iletişim kutusundaki Değiştir düğmesini seçtiğinde `OnReplaceSel` çağırır.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunan metin.

*bNext*<br/>
Aramanın yönünü belirtir. DOĞRU ise, arama yönü arabelleğin sonuna doğru olur. FALSE ise, arama yönü arabelleğin başına doğru olur.

*bCase*<br/>
Aramanın büyük/küçük harfe duyarlı olup olmadığını belirtir. DOĞRU ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değildir.

*lpszReplace*<br/>
Bulunan metnin yerine geçecek metin.

### <a name="remarks"></a>Açıklamalar

Bu işlev, seçimi değiştirdikten sonra, bCase tarafından belirtilen şekilde, *bCase*tarafından belirtilen şekilde, *bNext*tarafından belirtilen yönde *lpszFind*tarafından belirtilen metnin bir sonraki tekrarı için arabellekteki metni arar. Arama, [FindText](#findtext)çağrısıyla gerçekleştirilir. Metin bulunamazsa [OnTextNotFound](#ontextnotfound) çağırılır.

`CEditView`türetilmiş bir nesnenin seçili metnin yerini değiştirme biçimini değiştirmek için `OnReplaceSel` geçersiz kılın.

##  <a name="ontextnotfound"></a>CEditView:: OnTextNotFound

Windows işlevi `MessageBeep`çağıran varsayılan uygulamayı değiştirmek için bu işlevi geçersiz kılın.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunan metin.

##  <a name="printinsiderect"></a>CEditView::P rintInsideRect

*RectLayout*tarafından belirtilen dikdörtgende metin yazdırmak için `PrintInsideRect` çağırın.

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Yazıcı cihaz bağlamına yönelik işaretçi.

*rectLayout*<br/>
Metin işlenecek dikdörtgeni belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine veya [Rect yapısına](/windows/win32/api/windef/ns-windef-rect) başvuru.

*nIndexStart*<br/>
İşlenecek ilk karakter arabelleğinin içindeki dizin.

*Nındexstop*<br/>
İşlenecek son karakteri izleyen karakter arabelleği içinde dizin.

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak sonraki karakterin dizini (diğer bir deyişle, işlenen son karakteri izleyen karakter).

### <a name="remarks"></a>Açıklamalar

`CEditView` denetimin stili ES_AUTOHSCROLL yoksa metin işleme dikdörtgeni içinde sarmalanır. Denetimde stil ES_AUTOHSCROLL varsa, metin dikdörtgenin sağ kenarında kırpılır.

*RectLayout* nesnesinin `rect.bottom` öğesi, dikdörtgenin boyutları metnin kapladığı orijinal dikdörtgenin parçasını tanımlayabilmesi için değiştirilir.

##  <a name="serializeraw"></a>CEditView:: Serializsilinebilir w

`CArchive` nesnenin `CEditView` nesnesindeki metni metin dosyasına okuması veya yazması için `SerializeRaw` çağırın.

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Seri hale getirilmiş metni depolayan `CArchive` nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

`SerializeRaw`, önceki nesne açıklama verileri olmadan yalnızca metni okuyup yazmakta olan `Serialize` `CEditView`iç uygulamasına göre farklılık gösterir.

##  <a name="setprinterfont"></a>CEditView:: SetPrinterFont

Yazıcı yazı tipini *Pfont*tarafından belirtilen yazı tipine ayarlamak için `SetPrinterFont` çağırın.

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
`CFont`türünde bir nesne işaretçisi. NULL ise, yazdırma için kullanılan yazı tipi, görüntüleme yazı tipine göre belirlenir.

### <a name="remarks"></a>Açıklamalar

Görünümlerinizin yazdırma için her zaman belirli bir yazı tipini kullanmasını istiyorsanız, sınıfınızın `OnPreparePrinting` işlevindeki `SetPrinterFont` bir çağrı ekleyin. Bu sanal işlev yazdırma gerçekleşmeden önce çağrılır, bu nedenle yazı tipi değişikliği, görünümün içerikleri yazdırılmadan önce gerçekleştirilir.

##  <a name="settabstops"></a>CEditView:: Settabstop

Görüntüleme ve yazdırma için kullanılan sekme duraklarının ayarlanması için bu işlevi çağırın.

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Parametreler

*Ntabstop*<br/>
Her sekme durağını, iletişim kutusu birimlerinde Genişlik.

### <a name="remarks"></a>Açıklamalar

Yalnızca tek bir sekme durağı genişliği desteklenir. (`CEdit` nesneleri birden çok sekme genişliğini destekler.) Genişlikler, baskı veya görüntüleme sırasında kullanılan yazı tipinin (yalnızca büyük ve küçük harfli alfabetik karakterlere göre), ortalama karakter genişliğinin dörtte birine eşit olan iletişim kutusu birimleridir. `CEditView` sekme durağı değerini önbelleğe almanız gerektiğinden `CEdit::SetTabStops` kullanmamalısınız.

Bu işlev, yalnızca çağrılan nesnenin sekmelerini değiştirir. Uygulamanızdaki her bir `CEditView` nesnesinin sekme duraklarının değiştirilmesini değiştirmek için, her bir nesnenin `SetTabStops` işlevini çağırın.

### <a name="example"></a>Örnek

Bu kod parçası, denetimin kullandığı yazı tipini dikkatle ölçerek denetimdeki sekme duraklarının her dördüncü karaktere göre ayarlanır.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>CEditView:: UnlockBuffer

Arabelleğin kilidini açmak için bu üye işlevini çağırın.

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>Açıklamalar

[LockBuffer](#lockbuffer)tarafından döndürülen işaretçiyi kullanmayı bitirdikten sonra `UnlockBuffer` çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek üst PANELI](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
