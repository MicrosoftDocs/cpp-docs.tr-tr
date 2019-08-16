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
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506720"
---
# <a name="ceditview-class"></a>CEditView sınıfı

Bir Windows düzenleme denetiminin işlevselliğini sağlayan ve basit metin düzenleyici işlevselliği uygulamak için kullanılabilen bir görünüm sınıfı türü.

## <a name="syntax"></a>Sözdizimi

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CEditView:: CEditView](#ceditview)|Türünde `CEditView`bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CEditView:: FindText](#findtext)|Metin içinde bir dize arar.|
|[CEditView:: GetBufferLength](#getbufferlength)|Karakter arabelleğinin uzunluğunu alır.|
|[CEditView:: GetEditCtrl](#geteditctrl)|`CEdit` Bir`CEditView` nesnenin kısmına erişim sağlar (Windows düzenleme denetimi).|
|[CEditView:: GetPrinterFont](#getprinterfont)|Geçerli yazıcı yazı tipini alır.|
|[CEditView:: GetSelectedText](#getselectedtext)|Geçerli metin seçimini alır.|
|[CEditView:: LockBuffer](#lockbuffer)|Arabelleği kilitler.|
|[CEditView::P rintInsideRect](#printinsiderect)|Metni belirli bir dikdörtgen içinde işler.|
|[CEditView:: Serializsilinebilir w](#serializeraw)|Bir `CEditView` nesneyi ham metin olarak diske dizleştirir.|
|[CEditView:: SetPrinterFont](#setprinterfont)|Yeni bir yazıcı yazı tipi ayarlar.|
|[CEditView:: Settabstop](#settabstops)|Ekran görüntüleme ve yazdırma için sekme duraklarının her ikisini de ayarlar.|
|[CEditView:: UnlockBuffer](#unlockbuffer)|Arabelleğin kilidini açar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CEditView:: onsonra](#onfindnext)|Bir metin dizesinin sonraki tekrarını bulur.|
|[CEditView:: OnReplaceAll](#onreplaceall)|Belirli bir dizenin tüm oluşumlarını yeni bir dizeyle değiştirir.|
|[CEditView:: OnReplaceSel](#onreplacesel)|Geçerli seçimi değiştirir.|
|[CEditView:: OnTextNotFound](#ontextnotfound)|Bir bul işlemi başka bir metinle eşleşmediğinde çağırılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CEditView::d wStyleDefault](#dwstyledefault)|Türündeki `CEditView`nesneler için varsayılan stil.|

## <a name="remarks"></a>Açıklamalar

`CEditView` Sınıfı aşağıdaki ek işlevleri sağlar:

- Yazdırdığımda.

- Bul ve Değiştir.

Sınıfı `CEditView` `CView`, sınıfının bir türevi olduğundan, sınıf `CEditView` nesneleri belgeler ve belge şablonlarıyla birlikte kullanılabilir.

Her `CEditView` denetim metni kendi genel bellek nesnesinde tutulur. Uygulamanız herhangi bir sayıda `CEditView` nesneye sahip olabilir.

Yukarıda listelenen ekleme işlevleriyle `CEditView` bir düzenleme penceresi istiyorsanız veya basit metin düzenleyici işlevselliği istiyorsanız, türünde nesneler oluşturun. Bir `CEditView` nesne, bir pencerenin tüm istemci alanını açabilir. Temel işlevleri eklemek veya değiştirmek `CEditView` ya da bir belge şablonuna eklenebilen sınıfları bildirmek için ' den kendi sınıflarınızı türetebilirsiniz.

Sınıfının `CEditView` varsayılan uygulanması aşağıdaki komutları işler: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT ve ID_FILE_PRINT.

İçin `CEditView` varsayılan karakter sınırı (1024 \* 1024-1 = 1048575). Bu, temeldeki düzenleme denetiminin EM_LIMITTEXT işlevi çağırarak değiştirilebilir. Ancak, sınırlar işletim sistemine ve düzenleme denetiminin türüne (tek veya çok satırlı) bağlı olarak farklılık de vardır. Bu limitlerin hakkında daha fazla bilgi için bkz. [EM_LIMITTEXT](/windows/win32/Controls/em-limittext).

Denetiinizde bu sınırı değiştirmek için, `OnCreate()` `CEditView` sınıfınızın işlevini geçersiz kılın ve aşağıdaki kod satırını ekleyin:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

Türündeki `CEditView` nesneler (veya öğesinden `CEditView`türetilmiş türler) aşağıdaki sınırlamalara sahiptir:

- `CEditView`, ne görmelerinizi (WYSıWYG) düzenlemenizi, doğru uygulamaz. Ekranda okunabilirlik ve eşleşen yazdırılmış çıktı `CEditView` arasında seçim olduğunda ekran okunabilirlik için OptIn 'ler vardır.

- `CEditView`yalnızca tek bir yazı tipinde metin gösterebilir. Özel karakter biçimlendirme desteklenmez. Daha fazla özellik için bkz. sınıf [CRichEditView](../../mfc/reference/cricheditview-class.md) .

- Bir `CEditView` metnin içerebileceği metin miktarı sınırlıdır. Sınırlar, `CEdit` denetim ile aynıdır.

Hakkında `CEditView`daha fazla bilgi için bkz. [MFC 'de kullanılabilen türetilmiş Görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md).

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

Türünde `CEditView`bir nesne oluşturur.

```
CEditView();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, düzenleme denetimi kullanılmadan önce [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) işlevini çağırmanız gerekir. Öğesinden `CEditView` bir sınıf türetirsiniz ve kullanarak `CWinApp::AddDocTemplate`şablona eklerseniz, çerçeve `Create` hem bu oluşturucuyu hem de işlevini çağırır.

##  <a name="dwstyledefault"></a>CEditView::d wStyleDefault

`CEditView` Nesnenin varsayılan stilini içerir.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Açıklamalar

Nesnenin varsayılan stilini almak için bu statik üyeyi `Create` işlevin *dwStyle* parametresi olarak geçirin. `CEditView`

##  <a name="findtext"></a>CEditView:: FindText

`CEditView` Nesnenin metin arabelleğini aramak için işleviçağırın.`FindText`

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

Genellikle, öğesini geçersiz kılmadığınız `FindText` `OnFindNext`takdirde işlevini çağırmanız gerekmez, ancak çağırır `FindText`.

##  <a name="getbufferlength"></a>CEditView:: GetBufferLength

Null Sonlandırıcı dahil değil, düzenleme denetimi arabelleğinde Şu anda bulunan karakter sayısını almak için bu üye işlevi çağırın.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekteki dizenin uzunluğu.

##  <a name="geteditctrl"></a>CEditView:: GetEditCtrl

Düzenleme `GetEditCtrl` görünümü tarafından kullanılan düzenleme denetimine başvuru almak için çağırın.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CEdit` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu denetim [cedıt](../../mfc/reference/cedit-class.md)türünde olduğundan, Windows düzenleme denetimini doğrudan `CEdit` üye işlevleri kullanarak değiştirebilirsiniz.

> [!CAUTION]
>  `CEdit` Nesnesini kullanmak, temeldeki Windows düzenleme denetiminin durumunu değiştirebilir. Örneğin, bu ayarları hem düzenleme denetiminde hem de baskıda kullanılmak üzere önbelleğe aldığından `CEditView` , [cedıt:: settabstop](../../mfc/reference/cedit-class.md#settabstops) işlevini kullanarak sekme ayarlarını değiştirmemelisiniz. Bunun yerine [CEditView:: Settabstop](#settabstops)kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>CEditView:: GetPrinterFont

Geçerli `GetPrinterFont` yazıcı yazı tipini açıklayan bir [CFont](../../mfc/reference/cfont-class.md) nesnesine bir işaretçi almak için çağırın.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazıcı yazı tipini `CFont` belirten bir nesne işaretçisi; Yazıcı yazı tipi ayarlanmamışsa NULL. İşaretçi geçici olabilir ve daha sonra kullanılmak üzere depolanmamalıdır.

### <a name="remarks"></a>Açıklamalar

Yazıcı yazı tipi ayarlanmamışsa, `CEditView` sınıfının varsayılan yazdırma davranışı, görüntüleme için kullanılan yazı tipini kullanarak yazdırılır.

Geçerli yazıcı yazı tipini öğrenmek için bu işlevi kullanın. İstenen yazıcı yazı tipi değilse, değiştirmek için [CEditView:: SetPrinterFont](#setprinterfont) kullanın.

##  <a name="getselectedtext"></a>CEditView:: GetSelectedText

Seçili `GetSelectedText` metni, seçimin sonuna kadar veya seçimdeki `CString` ilk satır başı karakterden önceki karakteri bir nesneye kopyalamak için çağırın.

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Parametreler

*strResult*<br/>
Seçili metni alacak `CString` nesneye bir başvuru.

##  <a name="lockbuffer"></a>CEditView:: LockBuffer

Arabelleğin işaretçisini almak için bu üye işlevini çağırın. Arabellek değiştirilmemelidir.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetiminin arabelleğine yönelik bir işaretçi.

##  <a name="onfindnext"></a>CEditView:: onsonra

*LpszFind*tarafından belirtilen metin için arabellekteki metni, bCase tarafından büyük/küçük harf duyarlılığı belirtilmiş şekilde *bNext*tarafından belirtilen yönde arar.

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

Arama, geçerli seçimin başlangıcında başlar ve [FindText](#findtext)çağrısıyla gerçekleştirilir. Varsayılan uygulamada, metin bulunamazsa `OnFindNext` [OnTextNotFound](#ontextnotfound) ' ı çağırır.

`OnFindNext` Bir`CEditView`türetilmiş nesnenin metni arama şeklini değiştirmek için geçersiz kılın. `CEditView`Kullanıcı `OnFindNext` standart bul iletişim kutusunda Sonrakini Bul düğmesini seçtiğinde çağırır.

##  <a name="onreplaceall"></a>CEditView:: OnReplaceAll

`CEditView`Kullanıcı `OnReplaceAll` standart Değiştir iletişim kutusundaki Tümünü Değiştir düğmesini seçtiğinde çağırır.

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

`OnReplaceAll`*lpszFind*tarafından belirtilen metin için arabellekteki metni, *bCase*ile belirtilen büyük/küçük harf duyarlılığı ile arar. Arama, geçerli seçimin başlangıcında başlar. Arama metninin her bulunduğu her seferinde, bu işlev metnin *lpszReplace*tarafından belirtilen metinle değiştirir. Arama, [FindText](#findtext)çağrısıyla gerçekleştirilir. Varsayılan uygulamada [OnTextNotFound](#ontextnotfound) , metin bulunamazsa çağırılır.

Geçerli seçim *lpszFind*ile eşleşmiyorsa, seçim *lpszFind* tarafından belirtilen metnin ilk oluşumuna güncelleştirilir ve bir değiştirme gerçekleştirilmez. Bu, kullanıcının, seçimi değiştirilmekte olan metinle eşleşmediği zaman ne yapmak istediğiyle ilgili olduğunu onaylamasını sağlar.

`OnReplaceAll` Bir`CEditView`türetilen nesnenin metni değiştirme şeklini değiştirmek için geçersiz kılın.

##  <a name="onreplacesel"></a>CEditView:: OnReplaceSel

`CEditView`Kullanıcı `OnReplaceSel` standart değiştirme iletişim kutusunda Değiştir düğmesini seçtiğinde çağırır.

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

Bu işlev, seçimi değiştirdikten sonra, bCase tarafından belirtilen şekilde, *bCase*tarafından belirtilen şekilde, bNext tarafından belirtilen yönde *lpszFind*tarafından belirtilen metnin birsonraki tekrarı için arabellekteki metni arar. Arama, [FindText](#findtext)çağrısıyla gerçekleştirilir. Metin bulunamazsa [OnTextNotFound](#ontextnotfound) çağırılır.

`OnReplaceSel` Bir`CEditView`-türetilmiş nesnenin seçili metnin yerini değiştirme şeklini değiştirmek için geçersiz kılın.

##  <a name="ontextnotfound"></a>CEditView:: OnTextNotFound

Windows işlevini `MessageBeep`çağıran varsayılan uygulamayı değiştirmek için bu işlevi geçersiz kılın.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunan metin.

##  <a name="printinsiderect"></a>CEditView::P rintInsideRect

`PrintInsideRect` *RectLayout*tarafından belirtilen dikdörtgende yazdırma metni çağrısı.

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

`CEditView` Denetimde stil es_autohscroll yoksa metin işleme dikdörtgeni içinde sarmalanır. Denetimde ES_AUTOHSCROLL stili varsa, metin dikdörtgenin sağ kenarında kırpılır.

*RectLayout* nesnesinin öğesi,dikdörtgeninboyutlarınınmetintarafındankullanılanorijinaldikdörtgeninparçasınıtanımlayabilmesiiçindeğiştirilir.`rect.bottom`

##  <a name="serializeraw"></a>CEditView:: Serializsilinebilir w

`CEditView` Bir `SerializeRaw` nesnenin`CArchive` metin dosyasına okuma veya nesne içindeki metni yazma için çağrısı.

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Seri hale getirilmiş metni depolayan nesneyebaşvuru.`CArchive`

### <a name="remarks"></a>Açıklamalar

`SerializeRaw`, önceki nesne açıklama verileri olmadan `Serialize` yalnızca metni okuyup yazdığından ' ın iç uygulamasına göre farklılık gösterir. `CEditView`

##  <a name="setprinterfont"></a>CEditView:: SetPrinterFont

Yazıcı `SetPrinterFont` yazı tipini *pfont*tarafından belirtilen yazı tipine ayarlamak için çağırın.

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Türünde `CFont`bir nesne için bir işaretçi. NULL ise, yazdırma için kullanılan yazı tipi, görüntüleme yazı tipine göre belirlenir.

### <a name="remarks"></a>Açıklamalar

Görünümlerinizin yazdırma için her zaman belirli bir yazı tipini kullanmasını istiyorsanız, `SetPrinterFont` `OnPreparePrinting` sınıfınızın işlevindeki bir çağrı ekleyin. Bu sanal işlev yazdırma gerçekleşmeden önce çağrılır, bu nedenle yazı tipi değişikliği, görünümün içerikleri yazdırılmadan önce gerçekleştirilir.

##  <a name="settabstops"></a>CEditView:: Settabstop

Görüntüleme ve yazdırma için kullanılan sekme duraklarının ayarlanması için bu işlevi çağırın.

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Parametreler

*Ntabstop*<br/>
Her sekme durağını, iletişim kutusu birimlerinde Genişlik.

### <a name="remarks"></a>Açıklamalar

Yalnızca tek bir sekme durağı genişliği desteklenir. ( `CEdit` nesneler birden çok sekme genişliğini destekler.) Genişlikler, baskı veya görüntüleme sırasında kullanılan yazı tipinin (yalnızca büyük ve küçük harfli alfabetik karakterlere göre), ortalama karakter genişliğinin dörtte birine eşit olan iletişim kutusu birimleridir. ' İ kullanmanız `CEdit::SetTabStops` gerekir, `CEditView` çünkü Tab-stop değerini önbelleğe almalısınız.

Bu işlev, yalnızca çağrılan nesnenin sekmelerini değiştirir. Uygulamanızdaki her `CEditView` bir nesne için sekme duraklarının değiştirilmesini değiştirmek için, her `SetTabStops` nesnenin işlevini çağırın.

### <a name="example"></a>Örnek

Bu kod parçası, denetimin kullandığı yazı tipini dikkatle ölçerek denetimdeki sekme duraklarının her dördüncü karaktere göre ayarlanır.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>CEditView:: UnlockBuffer

Arabelleğin kilidini açmak için bu üye işlevini çağırın.

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>Açıklamalar

`UnlockBuffer` [LockBuffer](#lockbuffer)tarafından döndürülen işaretçiyi kullanmayı bitirdikten sonra çağrısı yapın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek üst PANELI](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
