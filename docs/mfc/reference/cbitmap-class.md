---
title: CBitmap Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
ms.openlocfilehash: 9a33a6e1bea601422e043d7f2a80029c72d97e50
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352740"
---
# <a name="cbitmap-class"></a>CBitmap Sınıfı

Bir Windows grafik aygıtı arabirimini (GDI) biteşe saklar ve bit eşlemi işlemek için üye işlevler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBitmap::CBitmap](#cbitmap)|Bir `CBitmap` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBitmap::CreateBitmap](#createbitmap)|Nesneyi, belirli bir genişliğe, yüksekliğe ve bit desenine sahip aygıta bağımlı bellek bit eşlemi yle başolarak adlandırır.|
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Nesneyi, bir `BITMAP` yapıda verilen genişlik, yükseklik ve bit deseni (belirtilmişse) ile bir bit eşlemi ile başolarak karşılar.|
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Nesneyi bir bit eşlemi ile başharfe, böylece belirli bir aygıtla uyumlu hale getirin.|
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Nesneyi, belirli bir aygıtla uyumlu bir bit eşlemi ile başolarak adlandırır.|
|[CBitmap::FromHandle](#fromhandle)|Bir Windows `HBITMAP` bit `CBitmap` eşlemi için bir tanıtıcı verildiğinde bir nesneye bir işaretçi döndürür.|
|[CBitmap::GetBitmap](#getbitmap)|Bir `BITMAP` yapıyı bit eşlemi hakkında bilgiyle doldurur.|
|[CBitmap::GetBitmapBits](#getbitmapbits)|Belirtilen bit eşleminin bitlerini belirtilen arabelleğe kopyalar.|
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Bit eşleminin genişliğini ve yüksekliğini verir. Yükseklik ve genişlik [SetBitmapDimension](#setbitmapdimension) üye işlevi tarafından daha önce ayarlanmış olduğu varsayılır.|
|[CBitmap::LoadBitmap](#loadbitmap)|Uygulamanın yürütülebilir dosyasından adlandırılmış bir bitmap kaynağı yükleyerek ve bit eşlemini nesneye ekleyerek nesneyi başlatır.|
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Bir biteşme yükler ve renkleri geçerli sistem renkleriyle eşler.|
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Önceden tanımlanmış bir Windows bit eşlemi yükleyerek ve bit eşlemi nesneye ekleyerek nesneyi başolarak algılar.|
|[CBitmap::SetBitmapBits](#setbitmapbits)|Bit eşlemi bitlerini belirtilen bit değerlerine ayarlar.|
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|0,1 milimetrelik birimlerde bir bit eşleneğine bir genislik ve yükseklik atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CBitmap::operatör HBITMAP](#operator_hbitmap)|Nesneye bağlı Windows tutamacını `CBitmap` döndürür.|

## <a name="remarks"></a>Açıklamalar

Bir `CBitmap` nesneyi kullanmak için nesneyi oluştur, başlangıç üye işlevlerinden biriyle ona bir bit eşlemi tutamacı ekle ve sonra nesnenin üye işlevlerini çağırın.

Gibi `CBitmap`grafik nesneleri kullanma hakkında daha fazla bilgi için [bkz.](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cgdiobject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cbitmapcbitmap"></a><a name="cbitmap"></a>CBitmap::CBitmap

Bir `CBitmap` nesne inşa eder.

```
CBitmap();
```

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan nesne, başlatma üye işlevlerinden biriyle başharfe bilmelidir.

## <a name="cbitmapcreatebitmap"></a><a name="createbitmap"></a>CBitmap::CreateBitmap

Belirtilen genişliğe, yüksekliğe ve bit desenine sahip aygıta bağımlı bellek bit eşlemi başolarak karşılar.

```
BOOL CreateBitmap(
    int nWidth,
    int nHeight,
    UINT nPlanes,
    UINT nBitcount,
    const void* lpBits);
```

### <a name="parameters"></a>Parametreler

*Nwidth*<br/>
Bit eşleninin genişliğini (piksel olarak) belirtir.

*Nheight*<br/>
Bit eşleninin yüksekliğini (piksel olarak) belirtir.

*nUçaklar*<br/>
Bit haritasındaki renk düzlemlerinin sayısını belirtir.

*nBitsayısı*<br/>
Görüntü pikseli başına renk biti sayısını belirtir.

*lpBits*<br/>
İlk bit eşlemi bit değerlerini içeren bir bayt dizisini gösterir. NULL ise, yeni bit eşlemi baş harfe bağlı olarak bırakılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Renkli bitmap için *nPlanes* veya *nBitcount* parametresi 1 olarak ayarlanmalıdır. Bu parametrelerin her ikisi de `CreateBitmap` 1 olarak ayarlanırsa, tek renkli bit eşlemi oluşturur.

Bir ekran aygıtı için doğrudan bir bit eşlemi seçilemese de, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) kullanarak bir "bellek aygıtı bağlamı" için geçerli bit eşlemi olarak seçilebilir ve [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) işlevini kullanarak herhangi bir uyumlu aygıt bağlamına kopyalanabilir.

İşlev tarafından `CBitmap` oluşturulan nesneyle bitirdiğinizde, önce aygıt bağlamının bit eşlesini seçin, ardından nesneyi `CBitmap` silin. `CreateBitmap`

Daha fazla bilgi için, `bmBits` yapıdaki `BITMAP` alanın açıklamasına bakın. [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) yapısı [CBitmap altında açıklanmıştır::CreateBitmapIndirect](#createbitmapindirect) üye fonksiyonu.

## <a name="cbitmapcreatebitmapindirect"></a><a name="createbitmapindirect"></a>CBitmap::CreateBitmapIndirect

LPBitmap tarafından işaret edilen yapıda verilen genişlik, yükseklik ve bit deseni (belirtilmişse) olan bir *bit eşlemi*başlatifleştirir.

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>Parametreler

*lpBitmap*<br/>
Bitmap hakkında bilgi içeren bir [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) yapısına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir ekran aygıtı için doğrudan bir bit eşlemi seçilemese de, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) kullanarak bellek aygıtı bağlamı için geçerli bit eşlemi olarak seçilebilir ve [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [CDC:StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) işlevi kullanılarak herhangi bir uyumlu aygıt bağlamına kopyalanabilir. [(CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) işlevi geçerli fırçanın bit eşlesini doğrudan görüntü aygıtı bağlamına kopyalayabilir.)

*LPBitmap* parametresi tarafından işaret edilen `GetObject` `BITMAP` yapı işlevi kullanılarak doldurulmuşsa, bit eşlemenin bitleri belirtilmemiş ve bit eşlemi baş harfize edilmemiştir. Bit eşlemi nin başlatılması için, bir uygulama [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [SetDIBits](/windows/win32/api/wingdi/nf-wingdi-setdibits) gibi bir işlevi kullanarak bit haritasının ilk parametresi tarafından `CGdiObject::GetObject` `CreateBitmapIndirect`tanımlanan bit eşleminden oluşturulan bit eşleminin bit eşleminden kopyalanabilir.

İşlevle `CBitmap` `CreateBitmapIndirect` oluşturulan nesneyle bitirdiğinizde, önce aygıt bağlamının bit eşlesini seçin, ardından nesneyi `CBitmap` silin.

## <a name="cbitmapcreatecompatiblebitmap"></a><a name="createcompatiblebitmap"></a>CBitmap::CreateCompatibleBitmap

*pDC*tarafından belirtilen aygıtla uyumlu bir bit eşlemi başlatma.

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Aygıt bağlamını belirtir.

*Nwidth*<br/>
Bit eşleninin genişliğini (piksel olarak) belirtir.

*Nheight*<br/>
Bit eşleninin yüksekliğini (piksel olarak) belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlemi, belirtilen aygıt bağlamıyla aynı sayıda renk düzlemine veya piksel başına aynı bit biçimine sahiptir. *PDC*tarafından belirtilen bellek aygıtı ile uyumlu herhangi bir bellek aygıtı için geçerli bit map olarak seçilebilir.

*pDC* bir bellek aygıtı bağlamıysa, döndürülen bit eşlemi, bu aygıt bağlamında şu anda seçili bit eşlemiyle aynı biçime sahiptir. "Bellek aygıtı bağlamı", görüntü yüzeyini temsil eden bir bellek bloğudur. Görüntüleri uyumlu cihazın gerçek ekran yüzeyine kopyalamadan önce bellekte hazırlamak için kullanılabilir.

Bir bellek aygıtı bağlamı oluşturulduğunda, GDI bunun için otomatik olarak tek renkli bir stok bit eşlemi seçer.

Renkli bellek aygıtı bağlamı renk veya tek renkli bit eşlemleri seçilebildiği `CreateCompatibleBitmap` için, işlev tarafından döndürülen bit eşlemi biçimi her zaman aynı değildir; ancak, bellek olmayan aygıt bağlamı için uyumlu bir biteşin biçimi her zaman aygıtın biçimindedir.

İşlevle oluşturulan `CBitmap` nesneyle bitirdiğinizde, önce aygıt bağlamının bit eşlesini `CBitmap` seçin, ardından nesneyi silin. `CreateCompatibleBitmap`

## <a name="cbitmapcreatediscardablebitmap"></a><a name="creatediscardablebitmap"></a>CBitmap::CreateDiscardableBitmap

*pDC*tarafından tanımlanan aygıt bağlamıyla uyumlu bir atılabilir bit eşlemi başlatılır.

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Aygıt bağlamı belirtir.

*Nwidth*<br/>
Bit eşleminin genişliğini (bit olarak) belirtir.

*Nheight*<br/>
Bit haritasının yüksekliğini (bit olarak) belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlemi, belirtilen aygıt bağlamıyla aynı sayıda renk düzlemine veya piksel başına aynı bit biçimine sahiptir. Bir uygulama *pDC*tarafından belirtilen ile uyumlu bir bellek aygıtı için geçerli bitmap olarak bu bitmap seçebilirsiniz.

Windows, bu işlev tarafından oluşturulan bir bit eşlemi yalnızca bir uygulama görüntü bağlamına seçmemişse atabilir. Windows seçilmediğinde bit eşlemi atar ve uygulama daha sonra onu seçmeye çalışırsa, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) işlevi NULL döndürür.

İşlevle oluşturulan `CBitmap` nesneyle bitirdiğinizde, önce aygıt bağlamının bit eşlesini `CBitmap` seçin, ardından nesneyi silin. `CreateDiscardableBitmap`

## <a name="cbitmapfromhandle"></a><a name="fromhandle"></a>CBitmap::FromHandle

Bir Windows GDI bit eşlemi için bir tanıtıcı verildiğinde bir `CBitmap` nesneye bir işaretçi döndürür.

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
Windows GDI bit eşlemi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CBitmap` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir `CBitmap` nesne tutamacına zaten eklenmiş değilse, geçici `CBitmap` bir nesne oluşturulur ve eklenir. Bu `CBitmap` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olduğu ve tüm geçici grafik nesnelerinin silindiği bir sonraki zamana kadar geçerlidir. Bunu söylemenin başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olmasıdır.

## <a name="cbitmapgetbitmap"></a><a name="getbitmap"></a>CBitmap::GetBitmap

Ekli bit eşlemi için görüntü özelliklerini alır.

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>Parametreler

*pBitMap*<br/>
Görüntü özelliklerini alacak bir [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) yapısıiçin işaretçi. Bu parametre NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cbitmapgetbitmapbits"></a><a name="getbitmapbits"></a>CBitmap::GetBitmapBits

Ekli bit eşleminin bit desenini belirtilen arabelleğe kopyalar.

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>Parametreler

*dwSay*<br/>
Arabelleğe kopyalanması için bayt sayısı.

*lpBits*<br/>
Bit eşlemi alacak arabelleğe işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa arabelleğe kopyalanan bayt sayısı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Gerekli arabellek boyutunu belirlemek için [CBitmap::GetBitmap'i](#getbitmap) kullanın.

## <a name="cbitmapgetbitmapdimension"></a><a name="getbitmapdimension"></a>CBitmap::GetBitmapDimension

Bit eşleminin genişliğini ve yüksekliğini verir.

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>Dönüş Değeri

0,1 milimetrelik birimler olarak ölçülen bit haritasının genişliği ve yüksekliği. Yükseklik `cy` `CSize` nesnenin üyesinde, genişlik ise `cx` üyededir. Biteş genişliği ve yüksekliği kullanılarak `SetBitmapDimension`ayarlanmadıysa, iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Yükseklik ve genişlik [SetBitmapDimension](#setbitmapdimension) üye işlevi kullanılarak daha önce ayarlanmış olduğu varsayılır.

## <a name="cbitmaploadbitmap"></a><a name="loadbitmap"></a>CBitmap::LoadBitmap

*lpszResourceName* tarafından adlandırılmış veya *nIDResource'daki* kimlik numarasıyla tanımlanan biteşe kaynağını uygulamanın yürütülebilir dosyasından yükler.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Bitmap kaynağının adını içeren null-sonlandırılan dizeyi işaret edin.

*nIDKaynak*<br/>
Bitmap kaynağının kaynak kimlik numarasını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yüklenen bit eşlemi `CBitmap` nesneye eklenir.

*lpszResourceName* tarafından tanımlanan bit eşlemi yoksa veya bit eşlemini yüklemek için yeterli bellek yoksa, işlev 0 döndürür.

`LoadBitmap` [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) işlevini kullanarak işlev tarafından yüklenen bit eşlemi `CBitmap` silebilir veya yıkıcı nesneyi sizin için siler.

> [!CAUTION]
> Nesneyi silmeden önce, aygıtın aygıt bağlamına seçilmediğinden emin olun.

Aşağıdaki bit eşlemler Windows sürümleri 3.1 ve sonraki sürümlere eklendi:

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

Bu bit eşlemleri Windows sürümleri 3.0 ve daha önceki aygıt sürücülerinde bulunmaz. Bit eşlemlerin tam listesi ve görünümlerinin bir göstergesi için Windows SDK'ya bakın.

## <a name="cbitmaploadmappedbitmap"></a><a name="loadmappedbitmap"></a>CBitmap::LoadMappedBitmap

Bitmap yüklemek ve renkleri geçerli sistem renkleriyle eşlemek için bu üye işlevi arayın.

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>Parametreler

*nIDBitmap*<br/>
Bitmap kaynağının kimliği.

*Nflags*<br/>
Bit map için bir bayrak. Sıfır veya CMB_MASKED olabilir.

*lpColorMap*<br/>
Bit eşlemlerini eşlemek için gereken renk bilgilerini içeren bir `COLORMAP` yapıya işaretçi. Bu parametre NULL ise, işlev varsayılan renk eşlemi kullanır.

*nMapSize*<br/>
*lpColorMap*tarafından işaret edilen renk haritaları nın sayısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `LoadMappedBitmap` düğme glifleri yaygın olarak kullanılan renkleri eşler.

Eşlenen bit eşlemi oluşturma hakkında daha fazla bilgi için [CreateMappedBitmap](https://go.microsoft.com/fwlink/p/?linkid=230562) ve Windows SDK'daki [COLORMAP](/windows/win32/api/commctrl/ns-commctrl-colormap) yapısına bakın.

## <a name="cbitmaploadoembitmap"></a><a name="loadoembitmap"></a>CBitmap::LoadOEMBitmap

Windows tarafından kullanılan önceden tanımlanmış bir bit eşlemi yükler.

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>Parametreler

*nIDBitmap*<br/>
Önceden tanımlanmış Windows bit haritasının kimlik numarası. Olası değerler windows aşağıda listelenmiştir. H:

|||
|-|-|
|OBM_BTNCORNERS|OBM_OLD_RESTORE|
|OBM_BTSIZE|OBM_OLD_RGARROW|
|OBM_CHECK|OBM_OLD_UPARROW|
|OBM_CHECKBOXES|OBM_OLD_ZOOM|
|OBM_CLOSE|OBM_REDUCE|
|OBM_COMBO|OBM_REDUCED|
|OBM_DNARROW|OBM_RESTORE|
|OBM_DNARROWD|OBM_RESTORED|
|OBM_DNARROWI|OBM_RGARROW|
|OBM_LFARROW|OBM_RGARROWD|
|OBM_LFARROWD|OBM_RGARROWI|
|OBM_LFARROWI|OBM_SIZE|
|OBM_MNARROW|OBM_UPARROW|
|OBM_OLD_CLOSE|OBM_UPARROWD|
|OBM_OLD_DNARROW|OBM_UPARROW|
|OBM_OLD_LFARROW|OBM_ZOOM|
|OBM_OLD_REDUCE|OBM_ZOOMD|

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OBM_OLD ile başlayan Bitmap adları, Windows sürümleri tarafından 3.0'dan önce kullanılan bit eşlemlerini temsil etmektedir.

Windows dahil edilmeden önce sabit OEMRESOURCE tanımlanması gerektiğini unutmayın. **OBM_** sabitlerinden herhangi birini kullanmak için H.

## <a name="cbitmapoperator-hbitmap"></a><a name="operator_hbitmap"></a>CBitmap::operatör HBITMAP

`CBitmap` Nesnenin ekli Windows GDI tutamacını almak için bu işleci kullanın.

```
operator HBITMAP() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesne tarafından temsil edilen Windows `CBitmap` GDI nesnesine bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir nesnenin doğrudan `HBITMAP` kullanımını destekleyen bir döküm işlecidir.

Grafik nesneleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Grafik Nesneler'e](/windows/win32/gdi/graphic-objects) bakın.

## <a name="cbitmapsetbitmapbits"></a><a name="setbitmapbits"></a>CBitmap::SetBitmapBits

Bit eşlemi bitlerini *lpBits*tarafından verilen bit değerlerine ayarlar.

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>Parametreler

*dwSay*<br/>
*LPBits*tarafından işaret edilen bayt sayısını belirtir.

*lpBits*<br/>
Nesneye kopyalanacak piksel değerlerini içeren BYTE dizisini `CBitmap` gösterir. Bit eşleminin görüntüsünü doğru bir şekilde işleyebilmesi için, değerlerin CBitmap örneği oluşturulduğunda belirtilen yükseklik, genişlik ve renk derinliği değerlerine uyacak şekilde biçimlendirilmesi gerekir. Daha fazla bilgi için [Bkz. CBitmap::CreateBitmap](#createbitmap).

### <a name="return-value"></a>Dönüş Değeri

Bitmap bitlerini ayarlamada kullanılan bayt sayısı; Fonksiyon başarısız olursa 0.

## <a name="cbitmapsetbitmapdimension"></a><a name="setbitmapdimension"></a>CBitmap::SetBitmapDimension

0,1 milimetrelik birimlerde bir bit eşleneğine bir genislik ve yükseklik atar.

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*Nwidth*<br/>
Bit eşleminin genişliğini (0,1 milimetrelik birimler halinde) belirtir.

*Nheight*<br/>
Bit eşleminin yüksekliğini (0,1 milimetrelik birimler halinde) belirtir.

### <a name="return-value"></a>Dönüş Değeri

Önceki biteş boyutu. Yükseklik `cy` `CSize` nesnenin üye değişkeninde, genişlik `cx` ise üye değişkendedir.

### <a name="remarks"></a>Açıklamalar

GDI, bir uygulama [GetBitmapDimension](#getbitmapdimension) üye işlevini aradığında bu değerleri döndürmek dışında kullanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
