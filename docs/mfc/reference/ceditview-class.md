---
description: 'Daha fazla bilgi edinin: CEditView sınıfı'
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
ms.openlocfilehash: b83b83b90fe530d2615a507d80e2af771397d286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184718"
---
# <a name="ceditview-class"></a>CEditView sınıfı

Bir Windows düzenleme denetiminin işlevselliğini sağlayan ve basit metin düzenleyici işlevselliği uygulamak için kullanılabilen bir görünüm sınıfı türü.

## <a name="syntax"></a>Syntax

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CEditView:: CEditView](#ceditview)|Türünde bir nesne oluşturur `CEditView` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CEditView:: FindText](#findtext)|Metin içinde bir dize arar.|
|[CEditView:: GetBufferLength](#getbufferlength)|Karakter arabelleğinin uzunluğunu alır.|
|[CEditView:: GetEditCtrl](#geteditctrl)|`CEdit`Bir nesnenin kısmına erişim sağlar `CEditView` (Windows düzenleme denetimi).|
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
|[CEditView::d wStyleDefault](#dwstyledefault)|Türündeki nesneler için varsayılan stil `CEditView` .|

## <a name="remarks"></a>Açıklamalar

`CEditView`Sınıfı aşağıdaki ek işlevleri sağlar:

- Yazdırın.

- Bul ve Değiştir.

Sınıfı `CEditView` , sınıfının bir türevi olduğundan `CView` , sınıf nesneleri `CEditView` Belgeler ve belge şablonlarıyla birlikte kullanılabilir.

Her `CEditView` Denetim metni kendi genel bellek nesnesinde tutulur. Uygulamanız herhangi bir sayıda nesneye sahip olabilir `CEditView` .

`CEditView`Yukarıda listelenen ekleme işlevleriyle bir düzenleme penceresi istiyorsanız veya basit metin düzenleyici işlevselliği istiyorsanız, türünde nesneler oluşturun. Bir `CEditView` nesne, bir pencerenin tüm istemci alanını açabilir. `CEditView`Temel işlevleri eklemek veya değiştirmek ya da bir belge şablonuna eklenebilen sınıfları bildirmek için ' den kendi sınıflarınızı türetebilirsiniz.

Sınıfının varsayılan uygulanması `CEditView` Şu komutları işler: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT ve ID_FILE_PRINT.

İçin varsayılan karakter sınırı `CEditView` (1024 \* 1024-1 = 1048575). Bu, temeldeki düzenleme denetiminin EM_LIMITTEXT işlevi çağırarak değiştirilebilir. Ancak, sınırlar işletim sistemine ve düzenleme denetiminin türüne (tek veya çok satırlı) bağlı olarak farklılık de vardır. Bu limitlerin hakkında daha fazla bilgi için bkz. [EM_LIMITTEXT](/windows/win32/Controls/em-limittext).

Denetiinizde bu sınırı değiştirmek için, `OnCreate()` sınıfınızın işlevini geçersiz kılın `CEditView` ve aşağıdaki kod satırını ekleyin:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

Türündeki nesneler `CEditView` (veya öğesinden türetilmiş türler `CEditView` ) aşağıdaki sınırlamalara sahiptir:

- `CEditView` , ne görmelerinizi (WYSıWYG) düzenlemenizi, doğru uygulamaz. Ekranda okunabilirlik ve eşleşen yazdırılmış çıktı arasında seçim olduğunda `CEditView` ekran okunabilirlik için OptIn 'ler vardır.

- `CEditView` yalnızca tek bir yazı tipinde metin gösterebilir. Özel karakter biçimlendirme desteklenmez. Daha fazla özellik için bkz. sınıf [CRichEditView](../../mfc/reference/cricheditview-class.md) .

- Bir metnin içerebileceği metin miktarı `CEditView` sınırlıdır. Sınırlar, denetim ile aynıdır `CEdit` .

Hakkında daha fazla bilgi için `CEditView` bkz. [MFC 'de kullanılabilen türetilmiş Görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="ceditviewceditview"></a><a name="ceditview"></a> CEditView:: CEditView

Türünde bir nesne oluşturur `CEditView` .

```
CEditView();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, düzenleme denetimi kullanılmadan önce [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) işlevini çağırmanız gerekir. Öğesinden bir sınıf türetirsiniz `CEditView` ve kullanarak şablona eklerseniz `CWinApp::AddDocTemplate` , çerçeve hem bu oluşturucuyu hem de `Create` işlevini çağırır.

## <a name="ceditviewdwstyledefault"></a><a name="dwstyledefault"></a> CEditView::d wStyleDefault

Nesnenin varsayılan stilini içerir `CEditView` .

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Açıklamalar

Nesnenin varsayılan stilini almak için bu statik üyeyi işlevin *dwStyle* parametresi olarak geçirin `Create` `CEditView` .

## <a name="ceditviewfindtext"></a><a name="findtext"></a> CEditView:: FindText

`FindText`Nesnenin metin arabelleğini aramak için işlevi çağırın `CEditView` .

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

Bu işlev, Geçerli seçimden başlayarak, *bNext* tarafından belirtilen yönde ve *bCase* tarafından belirtilen büyük/küçük harf duyarlılığı ile *lpszFind* tarafından belirtilen metin için arabellekteki metni arar. Metin bulunursa, seçimi bulunan metne ayarlar ve sıfır dışında bir değer döndürür. Metin bulunamazsa, işlev 0 döndürür.

Genellikle `FindText` , öğesini geçersiz kılmadığınız takdirde işlevini çağırmanız gerekmez, ancak `OnFindNext` çağırır `FindText` .

## <a name="ceditviewgetbufferlength"></a><a name="getbufferlength"></a> CEditView:: GetBufferLength

Null Sonlandırıcı dahil değil, düzenleme denetimi arabelleğinde Şu anda bulunan karakter sayısını almak için bu üye işlevi çağırın.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekteki dizenin uzunluğu.

## <a name="ceditviewgeteditctrl"></a><a name="geteditctrl"></a> CEditView:: GetEditCtrl

`GetEditCtrl`Düzenleme görünümü tarafından kullanılan düzenleme denetimine başvuru almak için çağırın.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CEdit` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu denetim [Cedıt](../../mfc/reference/cedit-class.md)türünde olduğundan, Windows düzenleme denetimini doğrudan `CEdit` üye işlevleri kullanarak değiştirebilirsiniz.

> [!CAUTION]
> Nesnesini kullanmak, `CEdit` temeldeki Windows düzenleme denetiminin durumunu değiştirebilir. Örneğin, bu ayarları hem düzenleme denetiminde hem de baskıda kullanılmak üzere önbelleğe aldığından, [Cedıt:: Settabstop](../../mfc/reference/cedit-class.md#settabstops) işlevini kullanarak sekme ayarlarını değiştirmemelisiniz `CEditView` . Bunun yerine [CEditView:: Settabstop](#settabstops)kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

## <a name="ceditviewgetprinterfont"></a><a name="getprinterfont"></a> CEditView:: GetPrinterFont

`GetPrinterFont`Geçerli yazıcı yazı tipini açıklayan bir [CFont](../../mfc/reference/cfont-class.md) nesnesine bir işaretçi almak için çağırın.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CFont`Geçerli yazıcı yazı tipini belirten bir nesne işaretçisi; Yazıcı yazı tipi ayarlanmamışsa NULL. İşaretçi geçici olabilir ve daha sonra kullanılmak üzere depolanmamalıdır.

### <a name="remarks"></a>Açıklamalar

Yazıcı yazı tipi ayarlanmamışsa, sınıfının varsayılan yazdırma davranışı, `CEditView` görüntüleme için kullanılan yazı tipini kullanarak yazdırılır.

Geçerli yazıcı yazı tipini öğrenmek için bu işlevi kullanın. İstenen yazıcı yazı tipi değilse, değiştirmek için [CEditView:: SetPrinterFont](#setprinterfont) kullanın.

## <a name="ceditviewgetselectedtext"></a><a name="getselectedtext"></a> CEditView:: GetSelectedText

`GetSelectedText`Seçili metni `CString` , seçimin sonuna kadar veya seçimdeki ilk satır başı karakterden önceki karakteri bir nesneye kopyalamak için çağırın.

```cpp
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Parametreler

*strResult*<br/>
`CString`Seçili metni alacak nesneye bir başvuru.

## <a name="ceditviewlockbuffer"></a><a name="lockbuffer"></a> CEditView:: LockBuffer

Arabelleğin işaretçisini almak için bu üye işlevini çağırın. Arabellek değiştirilmemelidir.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetiminin arabelleğine yönelik bir işaretçi.

## <a name="ceditviewonfindnext"></a><a name="onfindnext"></a> CEditView:: onsonra

*LpszFind* tarafından belirtilen metin için arabellekteki metni, *bCase* tarafından büyük/küçük harf duyarlılığı belirtilmiş şekilde *bNext* tarafından belirtilen yönde arar.

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

`OnFindNext`Bir `CEditView` türetilmiş nesnenin metni arama şeklini değiştirmek için geçersiz kılın. `CEditView``OnFindNext`Kullanıcı standart bul iletişim kutusunda Sonrakini Bul düğmesini seçtiğinde çağırır.

## <a name="ceditviewonreplaceall"></a><a name="onreplaceall"></a> CEditView:: OnReplaceAll

`CEditView``OnReplaceAll`Kullanıcı standart Değiştir iletişim kutusundaki Tümünü Değiştir düğmesini seçtiğinde çağırır.

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

`OnReplaceAll`*lpszFind* tarafından belirtilen metin için arabellekteki metni, *bCase* ile belirtilen büyük/küçük harf duyarlılığı ile arar. Arama, geçerli seçimin başlangıcında başlar. Arama metninin her bulunduğu her seferinde, bu işlev metnin *lpszReplace* tarafından belirtilen metinle değiştirir. Arama, [FindText](#findtext)çağrısıyla gerçekleştirilir. Varsayılan uygulamada [OnTextNotFound](#ontextnotfound) , metin bulunamazsa çağırılır.

Geçerli seçim *lpszFind* ile eşleşmiyorsa, seçim *lpszFind* tarafından belirtilen metnin ilk oluşumuna güncelleştirilir ve bir değiştirme gerçekleştirilmez. Bu, kullanıcının, seçimi değiştirilmekte olan metinle eşleşmediği zaman ne yapmak istediğiyle ilgili olduğunu onaylamasını sağlar.

`OnReplaceAll`Bir `CEditView` türetilen nesnenin metni değiştirme şeklini değiştirmek için geçersiz kılın.

## <a name="ceditviewonreplacesel"></a><a name="onreplacesel"></a> CEditView:: OnReplaceSel

`CEditView``OnReplaceSel`Kullanıcı standart değiştirme iletişim kutusunda Değiştir düğmesini seçtiğinde çağırır.

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

Bu işlev, seçimi değiştirdikten sonra, bCase tarafından belirtilen şekilde, *bCase* tarafından belirtilen şekilde, *bNext* tarafından belirtilen yönde *lpszFind* tarafından belirtilen metnin bir sonraki tekrarı için arabellekteki metni arar. Arama, [FindText](#findtext)çağrısıyla gerçekleştirilir. Metin bulunamazsa [OnTextNotFound](#ontextnotfound) çağırılır.

`OnReplaceSel`Bir `CEditView` -türetilmiş nesnenin seçili metnin yerini değiştirme şeklini değiştirmek için geçersiz kılın.

## <a name="ceditviewontextnotfound"></a><a name="ontextnotfound"></a> CEditView:: OnTextNotFound

Windows işlevini çağıran varsayılan uygulamayı değiştirmek için bu işlevi geçersiz kılın `MessageBeep` .

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszFind*<br/>
Bulunan metin.

## <a name="ceditviewprintinsiderect"></a><a name="printinsiderect"></a> CEditView::P rintInsideRect

`PrintInsideRect` *RectLayout* tarafından belirtilen dikdörtgende yazdırma metni çağrısı.

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

`CEditView`Denetimde stil es_autohscroll yoksa metin işleme dikdörtgeni içinde sarmalanır. Denetimde stil ES_AUTOHSCROLL varsa, metin dikdörtgenin sağ kenarında kırpılır.

`rect.bottom` *RectLayout* nesnesinin öğesi, dikdörtgenin boyutlarının metin tarafından kullanılan orijinal dikdörtgenin parçasını tanımlayabilmesi için değiştirilir.

## <a name="ceditviewserializeraw"></a><a name="serializeraw"></a> CEditView:: Serializsilinebilir w

`SerializeRaw`Bir `CArchive` nesnenin metin dosyasına okuma veya nesne içindeki metni yazma için çağrısı `CEditView` .

```cpp
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
`CArchive`Seri hale getirilmiş metni depolayan nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

`SerializeRaw``CEditView` `Serialize` , önceki nesne açıklama verileri olmadan yalnızca metni okuyup yazdığından ' ın iç uygulamasına göre farklılık gösterir.

## <a name="ceditviewsetprinterfont"></a><a name="setprinterfont"></a> CEditView:: SetPrinterFont

`SetPrinterFont`Yazıcı yazı tipini *pfont* tarafından belirtilen yazı tipine ayarlamak için çağırın.

```cpp
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Türünde bir nesne için bir işaretçi `CFont` . NULL ise, yazdırma için kullanılan yazı tipi, görüntüleme yazı tipine göre belirlenir.

### <a name="remarks"></a>Açıklamalar

Görünümlerinizin yazdırma için her zaman belirli bir yazı tipini kullanmasını istiyorsanız, sınıfınızın işlevindeki bir çağrı ekleyin `SetPrinterFont` `OnPreparePrinting` . Bu sanal işlev yazdırma gerçekleşmeden önce çağrılır, bu nedenle yazı tipi değişikliği, görünümün içerikleri yazdırılmadan önce gerçekleştirilir.

## <a name="ceditviewsettabstops"></a><a name="settabstops"></a> CEditView:: Settabstop

Görüntüleme ve yazdırma için kullanılan sekme duraklarının ayarlanması için bu işlevi çağırın.

```cpp
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Parametreler

*Ntabstop*<br/>
Her sekme durağını, iletişim kutusu birimlerinde Genişlik.

### <a name="remarks"></a>Açıklamalar

Yalnızca tek bir sekme durağı genişliği desteklenir. ( `CEdit` nesneler birden çok sekme genişliğini destekler.) Genişlikler, baskı veya görüntüleme sırasında kullanılan yazı tipinin (yalnızca büyük ve küçük harfli alfabetik karakterlere göre), ortalama karakter genişliğinin dörtte birine eşit olan iletişim kutusu birimleridir. ' İ kullanmanız gerekir, `CEdit::SetTabStops` çünkü `CEditView` Tab-stop değerini önbelleğe almalısınız.

Bu işlev, yalnızca çağrılan nesnenin sekmelerini değiştirir. Uygulamanızdaki her bir nesne için sekme duraklarının değiştirilmesini değiştirmek için `CEditView` , her nesnenin işlevini çağırın `SetTabStops` .

### <a name="example"></a>Örnek

Bu kod parçası, denetimin kullandığı yazı tipini dikkatle ölçerek denetimdeki sekme duraklarının her dördüncü karaktere göre ayarlanır.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

## <a name="ceditviewunlockbuffer"></a><a name="unlockbuffer"></a> CEditView:: UnlockBuffer

Arabelleğin kilidini açmak için bu üye işlevini çağırın.

```cpp
void UnlockBuffer() const;
```

### <a name="remarks"></a>Açıklamalar

`UnlockBuffer` [LockBuffer](#lockbuffer)tarafından döndürülen işaretçiyi kullanmayı bitirdikten sonra çağrısı yapın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek üst PANELI](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cedıt sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CDocument sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView sınıfı](../../mfc/reference/cricheditview-class.md)
