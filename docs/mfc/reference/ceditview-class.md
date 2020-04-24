---
title: CEditView Sınıfı
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
ms.openlocfilehash: 33b5975eea534eeaf308f73b5ca7fca2cd76787f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753191"
---
# <a name="ceditview-class"></a>CEditView Sınıfı

Windows edit denetiminin işlevselliğini sağlayan ve basit metin düzenleyicisi işlevini uygulamak için kullanılabilen bir görünüm sınıfı türü.

## <a name="syntax"></a>Sözdizimi

```
class CEditView : public CCtrlView
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CEditView::CEditView](#ceditview)|Türünde `CEditView`bir nesne oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CEditView::FindText](#findtext)|Metin içinde bir dize arar.|
|[CEditView::GetBufferLength](#getbufferlength)|Karakter arabelleği uzunluğunu alır.|
|[CEditView::GetEditCtrl](#geteditctrl)|`CEditView` Nesnenin bölümüne `CEdit` (Windows denetim denetimi) erişim sağlar.|
|[CEditView::GetPrinterFont](#getprinterfont)|Geçerli yazıcı yazı tipini alır.|
|[CEditView::GetSelectedText](#getselectedtext)|Geçerli metin seçimini alır.|
|[CEditView::LockBuffer](#lockbuffer)|Arabelleği kilitler.|
|[CEditView::PrintInsideRect](#printinsiderect)|Metni belirli bir dikdörtgenin içinde işler.|
|[CEditView::SerializeRaw](#serializeraw)|Bir `CEditView` nesneyi ham metin olarak diske seri hale getirir.|
|[CEditView::SetPrinterFont](#setprinterfont)|Yeni bir yazıcı yazı tipi ayarlar.|
|[CEditView::SetTabStops](#settabstops)|Hem ekran ekranı hem de yazdırma için sekme duraklarını ayarlar.|
|[CEditView::UnlockBuffer](#unlockbuffer)|Arabelleği açar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CEditView::OnFindNext](#onfindnext)|Bir metin dizesinin sonraki oluşumunu bulur.|
|[CEditView::OnReplaceAll](#onreplaceall)|Belirli bir dizedeki tüm oluşumları yeni bir dizeyle değiştirir.|
|[CEditView::OnReplaceSel](#onreplacesel)|Geçerli seçimi değiştirir.|
|[CEditView::OnTextNotFound](#ontextnotfound)|Bir bul işlemi başka bir metni eşleştiremezse çağrılır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CEditView::dwStyleDefault](#dwstyledefault)|Tür `CEditView`nesneleri için varsayılan stil.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CEditView` aşağıdaki ek işlevleri sağlar:

- Yazdırma.

- Bul ve değiştir.

Sınıf `CEditView` sınıfın `CView`bir türevi olduğundan, `CEditView` sınıf nesneleri belgeler ve belge şablonları ile kullanılabilir.

Her `CEditView` denetimin metni kendi genel bellek nesnesinde tutulur. Uygulamanızda herhangi bir `CEditView` sayıda nesne olabilir.

Yukarıda listelenen işlevsellik eklenmiş bir edit penceresi veya basit metin düzenleyicisi işlevselliği istiyorsanız, tür `CEditView` nesneleri oluşturun. Bir `CEditView` nesne pencerenin tüm istemci alanını kaplayabilir. Temel işlevselliği eklemek `CEditView` veya değiştirmek veya belge şablonuna eklenebilecek sınıfları bildirmek için kendi sınıflarınızı türetin.

Sınıfın `CEditView` varsayılan uygulaması aşağıdaki komutları işler: ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT ve ID_FILE_PRINT.

Varsayılan karakter sınırı `CEditView` (1024 \* 1024 - 1 = 1048575). Bu, temel düzenleme denetiminin EM_LIMITTEXT işlevini çağırarak değiştirilebilir. Ancak, sınırlar işletim sistemine ve düzenle denetiminin türüne (tek veya çok satırlı) bağlı olarak farklıdır. Bu sınırlar hakkında daha fazla bilgi için [EM_LIMITTEXT.](/windows/win32/Controls/em-limittext)

Denetiminizdeki bu sınırı değiştirmek için, `OnCreate()` sınıfınızın `CEditView` işlevini geçersiz kılın ve aşağıdaki kod satırını ekleyin:

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

Tür `CEditView` nesneleri (veya türetilen `CEditView`türler) aşağıdaki sınırlamalara sahiptir:

- `CEditView`ne gördüğünüz (WYSIWYG) düzenleme olsun doğru uygulamaz. Ekranda okunabilirlik ile yazdırılan çıktının eşleştirilmesi `CEditView` arasında bir seçim varsa, ekran okunabilirliğini tercih eder.

- `CEditView`metni yalnızca tek bir yazı tipinde görüntüleyebilir. Özel karakter biçimlendirmesi desteklenmez. Daha fazla özellik için [CRichEditView](../../mfc/reference/cricheditview-class.md) sınıfına bakın.

- A'nın `CEditView` içerebileceği metin miktarı sınırlıdır. Sınırlar `CEdit` denetim için aynıdır.

Hakkında daha `CEditView`fazla bilgi için [Bkz. MFC'de Bulunan Türemiş Görünüm Sınıfları.](../../mfc/derived-view-classes-available-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cview](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="ceditviewceditview"></a><a name="ceditview"></a>CEditView::CEditView

Türünde `CEditView`bir nesne oluşturuyor.

```
CEditView();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra, dama denetimi kullanılmadan önce [CWnd::Create](../../mfc/reference/cwnd-class.md#create) işlevini çağırmalısınız. Bir sınıftifve `CEditView` şablona kullanarak `CWinApp::AddDocTemplate`eklerseniz, çerçeve hem bu oluşturucuyu hem de `Create` işlevi çağırır.

## <a name="ceditviewdwstyledefault"></a><a name="dwstyledefault"></a>CEditView::dwStyleDefault

Nesnenin varsayılan stilini `CEditView` içerir.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>Açıklamalar

Nesne için varsayılan stili elde etmek için `Create` bu statik üyeyi `CEditView` işlevin *dwStyle* parametresi olarak geçirin.

## <a name="ceditviewfindtext"></a><a name="findtext"></a>CEditView::FindText

Nesnenin `FindText` metin arabelleği `CEditView` arama işlevi arayın.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunacak metin.

*bSonraki*<br/>
Aramanın yönünü belirtir. DOĞRUysa, arama yönü arabelleğin sonuna doğru. FALSE ise, arama yönü arabelleğin başına doğru.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harf duyarlıdır. FALSE ise, arama büyük/küçük harf duyarlı değildir.

### <a name="return-value"></a>Dönüş Değeri

Arama metni bulunursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu *işlev, lpszFind*tarafından belirtilen metin için arabellekteki metni arar , geçerli seçimden başlayarak, *bNext*tarafından belirtilen yönde , ve *bCase*tarafından belirtilen durum hassasiyeti ile . Metin bulunursa, seçimi bulunan metne ayarlar ve sıfır olmayan bir değer döndürür. Metin bulunamazsa, işlev 0 döndürür.

Normalde `FindText` geçersiz kılmadığınız `OnFindNext`sürece işlevi aramanız gerekmez, `FindText`bu da .

## <a name="ceditviewgetbufferlength"></a><a name="getbufferlength"></a>CEditView::GetBufferLength

Null sonlandırıcıdahil değil, edit denetiminin arabelleğinde bulunan karakter sayısını elde etmek için bu üye işlevi arayın.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arabellekteki dizenin uzunluğu.

## <a name="ceditviewgeteditctrl"></a><a name="geteditctrl"></a>CEditView::GetEditCtrl

Düzenleme `GetEditCtrl` görünümü tarafından kullanılan düzenleme denetimine başvurmak için arayın.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CEdit` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu denetim [CEdit](../../mfc/reference/cedit-class.md)türündendir, böylece `CEdit` windows düzenleme denetimini doğrudan üye işlevleri kullanarak değiştirebilirsiniz.

> [!CAUTION]
> Nesneyi `CEdit` kullanmak, windows denetiminin altında yatan durumu değiştirebilir. Örneğin, [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) işlevini kullanarak sekme ayarlarını `CEditView` değiştirmemelisiniz, çünkü bu ayarları hem denetimde hem de yazdırmada kullanmak üzere önbelleğe aldanmalıdır. Bunun yerine, [CEditView kullanın::SetTabStops](#settabstops).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

## <a name="ceditviewgetprinterfont"></a><a name="getprinterfont"></a>CEditView::GetPrinterFont

Geçerli `GetPrinterFont` yazıcı yazı tipini açıklayan bir [CFont](../../mfc/reference/cfont-class.md) nesnesine işaretçi almak için arayın.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazıcı `CFont` yazı tipini belirten bir nesneye işaretçi; Yazıcı yazı tipi ayarlanmadıysa NULL. İşaretçi geçici olabilir ve daha sonra kullanılmak üzere depolanmamalıdır.

### <a name="remarks"></a>Açıklamalar

Yazıcı yazı tipi ayarlanmadıysa, `CEditView` sınıfın varsayılan yazdırma davranışı, görüntü için kullanılan aynı yazı tipini kullanarak yazdırmaktır.

Geçerli yazıcı yazı tipini belirlemek için bu işlevi kullanın. İstenilen yazıcı yazı tipi değilse, değiştirmek için [CEditView:SetPrinterFont'u](#setprinterfont) kullanın.

## <a name="ceditviewgetselectedtext"></a><a name="getselectedtext"></a>CEditView::GetSelectedText

Seçili metni, seçimin `CString` sonuna kadar veya seçimdeki ilk satır başı karakterinden önceki karaktere kadar bir nesneye kopyalamak için arayın. `GetSelectedText`

```cpp
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>Parametreler

*strResult*<br/>
Seçili metni `CString` almak için nesneye bir başvuru.

## <a name="ceditviewlockbuffer"></a><a name="lockbuffer"></a>CEditView::LockBuffer

Arabellek için bir işaretçi almak için bu üye işlevi arayın. Arabellek değiştirilmemelidir.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin arabelleği için bir işaretçi.

## <a name="ceditviewonfindnext"></a><a name="onfindnext"></a>CEditView::OnFindNext

*lpszFind*tarafından belirtilen metin için arabellekteki metni arar , *bNext*tarafından belirtilen yönde , *bCase*tarafından belirtilen durum hassasiyeti ile .

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunacak metin.

*bSonraki*<br/>
Aramanın yönünü belirtir. DOĞRUysa, arama yönü arabelleğin sonuna doğru. FALSE ise, arama yönü arabelleğin başına doğru.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harf duyarlıdır. FALSE ise, arama büyük/küçük harf duyarlı değildir.

### <a name="remarks"></a>Açıklamalar

Arama geçerli seçimin başında başlar ve [FindText'e](#findtext)yapılan bir çağrı ile gerçekleştirilir. Varsayılan uygulamada, `OnFindNext` metin bulunamazsa [OnTextNotFound](#ontextnotfound) çağırır.

Türetilen `OnFindNext` nesnenin `CEditView`metni arama biçimini değiştirmek için geçersiz kılma. `CEditView`kullanıcı `OnFindNext` standart Bul iletişim kutusundaKi İleri Bul düğmesini seçtiğinde arar.

## <a name="ceditviewonreplaceall"></a><a name="onreplaceall"></a>CEditView::OnReplaceAll

`CEditView`kullanıcı `OnReplaceAll` standart Değiştir iletişim kutusundaki Tümünü Değiştir düğmesini seçtiğinde arar.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunacak metin.

*lpszDeğiştir*<br/>
Arama metnini değiştirmek için metin.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harf duyarlıdır. FALSE ise, arama büyük/küçük harf duyarlı değildir.

### <a name="remarks"></a>Açıklamalar

`OnReplaceAll`*lpszFind*tarafından belirtilen metin için arabellekteki metni arar , *bCase*tarafından belirtilen durum hassasiyeti ile . Arama geçerli seçimin başında başlar. Arama metni her bulunduğunda, bu işlev metnin oluşumunu *lpszReplace*tarafından belirtilen metinle değiştirir. Arama [FindText](#findtext)için bir çağrı ile gerçekleştirilir. Varsayılan uygulamada, metin bulunmazsa [OnTextNotFound](#ontextnotfound) çağrılır.

Geçerli seçim *lpszFind*eşleşmiyorsa, seçim *lpszFind* tarafından belirtilen metnin ilk oluşumuna güncelleştirilir ve bir değiştirme yapılmaz. Bu, seçim değiştirilecek metinle eşleşmediğinde, kullanıcının yapmak istedikleri şeyin bu olduğunu onaylamasını sağlar.

Türetilen `OnReplaceAll` nesnenin `CEditView`metnin yerini değiştirme şeklini değiştirmek için geçersiz kılma.

## <a name="ceditviewonreplacesel"></a><a name="onreplacesel"></a>CEditView::OnReplaceSel

`CEditView`kullanıcı `OnReplaceSel` standart Değiştir iletişim kutusunda değiştir düğmesini seçtiğinde arar.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunacak metin.

*bSonraki*<br/>
Aramanın yönünü belirtir. DOĞRUysa, arama yönü arabelleğin sonuna doğru. FALSE ise, arama yönü arabelleğin başına doğru.

*bCase*<br/>
Aramanın büyük/küçük harf duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harf duyarlıdır. FALSE ise, arama büyük/küçük harf duyarlı değildir.

*lpszDeğiştir*<br/>
Bulunan metni değiştirmek için metin.

### <a name="remarks"></a>Açıklamalar

Seçimi değiştirdikten sonra, bu işlev *lpszFind*tarafından belirtilen metnin bir sonraki oluşumu için arabellekteki metni arar , *bNext*tarafından belirtilen yönde , *bCase*tarafından belirtilen durum hassasiyeti ile . Arama [FindText](#findtext)için bir çağrı ile gerçekleştirilir. Metin bulunamazsa, [OnTextNotFound](#ontextnotfound) çağrılır.

Türetilen `OnReplaceSel` nesnenin `CEditView`seçili metnin yerini değiştirme şeklini değiştirmek için geçersiz kılma.

## <a name="ceditviewontextnotfound"></a><a name="ontextnotfound"></a>CEditView::OnTextNotFound

Windows işlevini `MessageBeep`çağıran varsayılan uygulamayı değiştirmek için bu işlevi geçersiz kılın.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>Parametreler

*lpszBul*<br/>
Bulunacak metin.

## <a name="ceditviewprintinsiderect"></a><a name="printinsiderect"></a>CEditView::PrintInsideRect

Dikdörtgen `PrintInsideRect` tarafından belirtilen dikdörtgende metin yazdırmak için *çağrı.*

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Yazıcı aygıtı bağlamını işaretçi.

*rektLayout*<br/>
Metnin oluşturulacak dikdörtgeni belirten bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine veya [RECT yapısına](/windows/win32/api/windef/ns-windef-rect) başvuru.

*nIndexStart*<br/>
İşlenecek ilk karakterin arabelleği içinde dizin.

*nIndexStop*<br/>
Oluşturulacak son karakteri izleyen karakterin arabelleği içinde dizin.

### <a name="return-value"></a>Dönüş Değeri

Yazdırılacak bir sonraki karakterin dizini (diğer bir süre, işlenen son karakteri izleyen karakter).

### <a name="remarks"></a>Açıklamalar

`CEditView` Denetimin stili ES_AUTOHSCROLL yoksa, metin işleme dikdörtgeninin içine sarılır. Denetimde ES_AUTOHSCROLL stili varsa, metin dikdörtgenin sağ kenarında niçin kırpılır.

dikdörtgen `rect.bottom` nesnesinin *rectLayout* öğesi, dikdörtgenin boyutlarının metnin kaplayan özgün dikdörtgen bölümünü tanımlaması için değiştirilir.

## <a name="ceditviewserializeraw"></a><a name="serializeraw"></a>CEditView::SerializeRaw

Nesnedeki `SerializeRaw` `CArchive` metni `CEditView` bir metin dosyasına okuması veya yazması için arayın.

```cpp
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Serileştirilmiş `CArchive` metni depolayan nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

`SerializeRaw`nesne açıklaması `CEditView`verilerinden önce `Serialize` olmadan yalnızca metni okuyup yazması 'nın iç uygulamasından farklıdır.

## <a name="ceditviewsetprinterfont"></a><a name="setprinterfont"></a>CEditView::SetPrinterFont

Yazıcı `SetPrinterFont` yazı tipini *pFont*tarafından belirtilen yazı tipine ayarlamak için arayın.

```cpp
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Türünden `CFont`bir nesneye işaretçi. NULL ise, yazdırmak için kullanılan yazı tipi görüntü yazı tipini temel alar.

### <a name="remarks"></a>Açıklamalar

Görünümünüzün her zaman yazdırma için belirli bir yazı `SetPrinterFont` tipini kullanmasını `OnPreparePrinting` istiyorsanız, sınıfınızın işlevine bir çağrı ekleyin. Bu sanal işlev yazdırma gerçekleşmeden önce çağrılır, bu nedenle yazı tipi değişikliği görünümün içeriği yazdırılmadan önce gerçekleşir.

## <a name="ceditviewsettabstops"></a><a name="settabstops"></a>CEditView::SetTabStops

Görüntüleme ve yazdırma için kullanılan sekme duraklarını ayarlamak için bu işlevi arayın.

```cpp
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>Parametreler

*nTabStops*<br/>
Her sekme durağının genişliği, iletişim birimlerinde.

### <a name="remarks"></a>Açıklamalar

Yalnızca tek bir sekme durdurma genişliği desteklenir. ( `CEdit` nesneler birden çok sekme genişliğini destekler.) Genişlikler, yazdırma veya görüntüleme sırasında kullanılan yazı tipinin ortalama karakter genişliğinin dörtte birine eşit olan iletişim birimlerindedir (yalnızca büyük harf ve küçük alfabetik karakterlere göre). Sekme durdurma `CEdit::SetTabStops` `CEditView` değerini önbelleğe almanız gerektiğinden kullanmamalısınız.

Bu işlev yalnızca çağrıldığı nesnenin sekmelerini değiştirir. Uygulamanızdaki her `CEditView` nesne için sekme duraklarını değiştirmek `SetTabStops` için, her nesnenin işlevini arayın.

### <a name="example"></a>Örnek

Bu kod parçası, denetimin kullandığı yazı tipini dikkatle ölçerek sekme duraklarını denetimde her dördüncü karaktere ayarlar.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

## <a name="ceditviewunlockbuffer"></a><a name="unlockbuffer"></a>CEditView::UnlockBuffer

Arabelleği açmak için bu üye işlevi arayın.

```cpp
void UnlockBuffer() const;
```

### <a name="remarks"></a>Açıklamalar

`UnlockBuffer` [LockBuffer](#lockbuffer)tarafından döndürülen işaretçiyi kullanmayı bitirdikten sonra arayın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[Kişniş Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView Sınıfı](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
