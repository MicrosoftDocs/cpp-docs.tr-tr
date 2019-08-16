---
title: CBitmap sınıfı
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
ms.openlocfilehash: 7161a4cf4484b6cc9e76e6955de558ca6e9121ca
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507448"
---
# <a name="cbitmap-class"></a>CBitmap sınıfı

Bir Windows grafik cihaz arabirimi (GDI) bit eşlemini kapsüller ve bit eşlemi işlemek için üye işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBitmap:: CBitmap](#cbitmap)|Bir `CBitmap` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmap:: CreateBitmap](#createbitmap)|Nesneyi, belirtilen genişlik, yükseklik ve bit düzenine sahip bir cihaza bağımlı bellek bit eşlemi ile başlatır.|
|[CBitmap:: Createbitmapdolaylı](#createbitmapindirect)|Bir `BITMAP` yapıda verilen genişlik, yükseklik ve bit düzeniyle (belirtilmişse) bir bit eşlem ile nesneyi başlatır.|
|[CBitmap:: CreateCompatibleBitmap](#createcompatiblebitmap)|Belirtilen bir cihazla uyumlu olması için nesneyi bir bit eşlem ile başlatır.|
|[CBitmap:: CreateDiscardableBitmap](#creatediscardablebitmap)|Nesneyi belirtilen bir cihazla uyumlu bir discardable bit eşlem ile başlatır.|
|[CBitmap:: FromHandle](#fromhandle)|`CBitmap` Windows`HBITMAP` bit eşlemiyle bir tanıtıcı verildiğinde, nesne için bir işaretçi döndürür.|
|[CBitmap:: GetBitmap](#getbitmap)|Bir `BITMAP` yapıyı bit eşlem hakkındaki bilgilerle doldurur.|
|[CBitmap:: GetBitmapBits](#getbitmapbits)|Belirtilen bit eşlemin bitlerini belirtilen arabelleğe kopyalar.|
|[CBitmap:: GetBitmapDimension](#getbitmapdimension)|Bit eşlemin genişliğini ve yüksekliğini döndürür. Yükseklik ve genişlik, daha önce [SetBitmapDimension](#setbitmapdimension) üye işlevi tarafından ayarlanmış olarak kabul edilir.|
|[CBitmap:: LoadBitmap](#loadbitmap)|Uygulamanın yürütülebilir dosyasından adlandırılmış bir bit eşlem kaynağı yükleyerek ve bit eşlemi nesnesine ekleyerek nesneyi başlatır.|
|[CBitmap:: LoadMappedBitmap](#loadmappedbitmap)|Bir bit eşlem yükler ve renkleri geçerli sistem renklerine eşler.|
|[CBitmap:: LoadOEMBitmap](#loadoembitmap)|Önceden tanımlanmış bir Windows bit eşlemi yükleyerek ve bit eşlemi nesnesine ekleyerek nesneyi başlatır.|
|[CBitmap:: Setbitmapbitleri](#setbitmapbits)|Bit eşlemin bitlerini belirtilen bit değerlerine ayarlar.|
|[CBitmap:: SetBitmapDimension](#setbitmapdimension)|0,1-milimetre ölçüm birimlerindeki bir bit eşleme genişlik ve Yükseklik atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmap:: operator HBıX](#operator_hbitmap)|`CBitmap` Nesnesine eklenen Windows işleyicisini döndürür.|

## <a name="remarks"></a>Açıklamalar

Bir `CBitmap` nesne kullanmak için, nesneyi oluşturun, başlatma üye işlevlerinden biriyle bir bit eşlem tutamacı ekleyin ve ardından nesnenin üye işlevlerini çağırın.

Gibi `CBitmap`grafik nesnelerini kullanma hakkında daha fazla bilgi için bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cbitmap"></a>CBitmap:: CBitmap

Bir `CBitmap` nesnesi oluşturur.

```
CBitmap();
```

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan nesne, başlatma üyesi işlevlerinden biri ile başlatılmalıdır.

##  <a name="createbitmap"></a>CBitmap:: CreateBitmap

Belirtilen genişlik, yükseklik ve bit düzenine sahip bir cihaza bağımlı bellek bit eşlemi başlatır.

```
BOOL CreateBitmap(
    int nWidth,
    int nHeight,
    UINT nPlanes,
    UINT nBitcount,
    const void* lpBits);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Bit eşlemin genişliğini (piksel cinsinden) belirtir.

*nHeight*<br/>
Bit eşlemin yüksekliğini (piksel cinsinden) belirtir.

*Ndüzlemler*<br/>
Bit eşlemdeki renk düzlemleri sayısını belirtir.

*nBitcount*<br/>
Ekran pikseli başına renk bitlerinin sayısını belirtir.

*lpBits*<br/>
İlk bit eşlem bit değerlerini içeren bir bayt dizisine işaret eder. NULL ise, yeni bit eşlem başlatılmamış olarak bırakılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Color bit eşlem için, *Ndüzlemler* ya da *nBitcount* parametresi 1 olarak ayarlanmalıdır. Bu parametrelerin her ikisi de 1 olarak ayarlanırsa, `CreateBitmap` tek renkli bir bit eşlem oluşturur.

Bir ekran cihazı için bir bit eşlem doğrudan seçilemese de, CDC:: [NesneSeç](../../mfc/reference/cdc-class.md#selectobject) kullanılarak "bellek cihaz bağlamı" için geçerli bit eşlem olarak seçilebilir ve [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) işlevi kullanılarak uyumlu herhangi bir cihaz bağlamına kopyalanabilir.

İşlev tarafından oluşturulan `CBitmap` nesneyle bitirdiğinizde, önce cihaz `CBitmap` bağlamından bit eşlemini seçin, sonra nesneyi silin. `CreateBitmap`

Daha fazla bilgi için, `bmBits` `BITMAP` yapıdaki alanın açıklamasına bakın. [Bit eşlem](/windows/win32/api/wingdi/ns-wingdi-bitmap) yapısı, [CBitmap:: createbitmapdolaylı](#createbitmapindirect) üye işlevi altında açıklanmaktadır.

##  <a name="createbitmapindirect"></a>CBitmap:: Createbitmapdolaylı

*Lpbit eşlem*tarafından işaret edilen yapıda belirtilen genişlik, yükseklik ve bit düzenine (belirtilmişse) sahip bir bit eşlem başlatır.

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>Parametreler

*Lpbit eşlem*<br/>
Bit eşlem hakkında bilgi içeren bir [bit eşlem](/windows/win32/api/wingdi/ns-wingdi-bitmap) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir ekran cihazı için bir bit eşlem doğrudan seçilemese de, CDC:: [NesneSeç](../../mfc/reference/cdc-class.md#selectobject) kullanarak bir bellek cihaz bağlamı için geçerli bit eşlem olarak seçilebilir ve [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [CDC:: ile uyumlu herhangi bir cihaz bağlamına kopyalanabilir. Irblt](../../mfc/reference/cdc-class.md#stretchblt) işlevi. ( [CDC::P atBlt](../../mfc/reference/cdc-class.md#patblt) işlevi, geçerli fırça için bit eşlemi doğrudan görüntüleme cihazı bağlamına kopyalayabilir.)

*Lpbıx* parametresi tarafından işaret edilen `GetObject` Yapıişlevikullanılarakdoldurulduysa,biteşleminbitleribelirtilmezvebiteşlembaşlatılmamışolur.`BITMAP` Bir uygulama, bit eşlemi başlatmak için, `CGdiObject::GetObject` ilk parametresi tarafından tanımlanan bit eşlemden tarafından `CreateBitmapIndirect`oluşturulan bit eşlemden bitleri kopyalamak üzere [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [SetDIBits](/windows/win32/api/wingdi/nf-wingdi-setdibits) gibi bir işlevi kullanabilir.

İşlev ile `CBitmap` `CreateBitmapIndirect` oluşturulan nesneyle bitirdiğinizde, önce cihaz `CBitmap` bağlamından bit eşlemini seçin, sonra nesneyi silin.

##  <a name="createcompatiblebitmap"></a>CBitmap:: CreateCompatibleBitmap

*PDC*tarafından belirtilen cihazla uyumlu bir bit eşlem başlatır.

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Cihaz bağlamını belirtir.

*nWidth*<br/>
Bit eşlemin genişliğini (piksel cinsinden) belirtir.

*nHeight*<br/>
Bit eşlemin yüksekliğini (piksel cinsinden) belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlem, belirtilen cihaz bağlamı ile aynı sayıda renk düzlemleri veya piksel başına aynı bit biçimine sahiptir. *PDC*tarafından belirtile uyumlu herhangi bir bellek aygıtı için geçerli bit eşlem olarak seçilebilir.

*PDC* bir bellek cihaz bağlamıdır, döndürülen bit eşlem o cihaz bağlamındaki Şu anda seçili olan bit eşlemle aynı biçimde olur. "Bellek cihaz bağlamı", bir görüntü yüzeyini temsil eden bir bellek bloğudur. Uyumlu cihazın gerçek görüntü yüzeyine kopyalamadan önce bellekte görüntü hazırlamak için kullanılabilir.

Bir bellek cihaz bağlamı oluşturulduğunda, GDI otomatik olarak kendisi için bir tek renkli hisse senedi bit eşlemi seçer.

Renk belleği cihaz bağlamında renk veya tek renkli bit eşlemler seçili olduğundan, `CreateCompatibleBitmap` işlev tarafından döndürülen bit eşlemin biçimi her zaman aynı değildir; ancak, bellek dışı bir cihaz bağlamı için uyumlu bir bit eşlem biçimi her zaman Cihazın biçimi.

İşlevle oluşturduğunuz `CBitmap` nesneyle bitirdiğinizde, önce cihaz `CBitmap` bağlamından bit eşlemini seçin, sonra nesneyi silin. `CreateCompatibleBitmap`

##  <a name="creatediscardablebitmap"></a>CBitmap:: CreateDiscardableBitmap

*PDC*tarafından tanımlanan cihaz bağlamı ile uyumlu bir discardable bit eşlemi başlatır.

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Bir cihaz bağlamını belirtir.

*nWidth*<br/>
Bit eşlemin genişliğini (bit cinsinden) belirtir.

*nHeight*<br/>
Bit eşlemin yüksekliğini (bit cinsinden) belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlem, belirtilen cihaz bağlamı ile aynı sayıda renk düzlemleri veya piksel başına aynı bit biçimine sahiptir. Bir uygulama, *PDC*tarafından belirtilen bir bellek cihazının geçerli bit eşlemi olarak bu bit eşlemi seçebilir.

Windows, bu işlev tarafından oluşturulan bir bit eşlemi atabilir, ancak bir uygulama onu bir görüntüleme bağlamına seçmez. Pencere seçili olmadığında ve uygulama daha sonra bunu açmaya çalıştığında, bu bit eşlemi atar. [](../../mfc/reference/cdc-class.md#selectobject)

İşlevle oluşturduğunuz `CBitmap` nesneyle bitirdiğinizde, önce cihaz `CBitmap` bağlamından bit eşlemini seçin, sonra nesneyi silin. `CreateDiscardableBitmap`

##  <a name="fromhandle"></a>CBitmap:: FromHandle

Bir Windows GDI bit eşlemiyle bir tanıtıcı verildiğinde `CBitmap` nesnesine bir işaretçi döndürür.

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*HBITMAP*<br/>
Bir Windows GDI bit eşlemini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CBitmap` nesne için bir işaretçi; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bir `CBitmap` nesne zaten tanıtıcıya iliştirilmişse, geçici `CBitmap` bir nesne oluşturulur ve eklenir. Bu geçici `CBitmap` nesne yalnızca uygulamanın olay döngüsünde bir sonraki kez boşta kalması durumunda geçerlidir. bu süre, tüm geçici grafik nesneleri silinir. Bunun başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olduğu durumdur.

##  <a name="getbitmap"></a>CBitmap:: GetBitmap

Ekli bit eşlem için görüntü özelliklerini alır.

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>Parametreler

*Pbımap*<br/>
Görüntü özelliklerini alacak bir [bit eşlem](/windows/win32/api/wingdi/ns-wingdi-bitmap) yapısına yönelik işaretçi. Bu parametre NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="getbitmapbits"></a>CBitmap:: GetBitmapBits

Ekli bit eşlemin bit modelini belirtilen arabelleğe kopyalar.

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>Parametreler

*dwCount*<br/>
Arabelleğe kopyalanacak bayt sayısı.

*lpBits*<br/>
Bit eşlemi alacak olan arabelleğin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa arabelleğe kopyalanmış bayt sayısı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Gerekli arabellek boyutunu öğrenmek için [CBitmap:: GetBitmap](#getbitmap) kullanın.

##  <a name="getbitmapdimension"></a>CBitmap:: GetBitmapDimension

Bit eşlemin genişliğini ve yüksekliğini döndürür.

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin 0,1 milimetre ölçüm birimlerinde ölçülen genişliği ve yüksekliği. Yükseklik `cy` `CSize` nesnenin üyesidir ve Genişlik `cx` üyede olur. Bit eşlem genişliği ve yüksekliği kullanılarak `SetBitmapDimension`ayarlanmamışsa, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Height ve Width 'in daha önce [SetBitmapDimension](#setbitmapdimension) üye işlevi kullanılarak ayarlandığı varsayılır.

##  <a name="loadbitmap"></a>CBitmap:: LoadBitmap

*LpszResourceName* tarafından adlandırılan ya da uygulamanın yürütülebilir dosyasındaki *nidresource* içindeki kimlik numarası tarafından tanımlanan bit eşlem kaynağını yükler.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Bit eşlem kaynağının adını içeren, null ile sonlandırılmış bir dizeye işaret eder.

*nIDResource*<br/>
Bit eşlem kaynağının kaynak KIMLIĞI numarasını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yüklenen bit eşlem `CBitmap` nesnesine eklenir.

*LpszResourceName* tarafından tanımlanan bit eşlem yoksa veya bit eşlemi yüklemek için yeterli bellek yoksa, işlev 0 döndürür.

İşlev tarafından yüklenen bit eşlemi silmek için [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) işlevini kullanabilirsiniz veya yıkıcınesneyisiziniçinsiler.`CBitmap` `LoadBitmap`

> [!CAUTION]
>  Nesneyi silmeden önce, bir cihaz bağlamına seçili olmadığından emin olun.

Aşağıdaki bit eşlemler Windows 3,1 ve üzeri sürümlere eklenmiştir:

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

Bu bit eşlemler Windows 3,0 ve önceki sürümleri için aygıt sürücülerinde bulunamadı. Bit eşlemlerin ve görünüşlerinin tamamı bir listesi için Windows SDK bakın.

##  <a name="loadmappedbitmap"></a>CBitmap:: LoadMappedBitmap

Bir bit eşlem yüklemek ve renkleri geçerli sistem renkleriyle eşlemek için bu üye işlevini çağırın.

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>Parametreler

*Nıdbit eşlem*<br/>
Bit eşlem kaynağının KIMLIĞI.

*nFlags*<br/>
Bit eşlem için bayrak. Sıfır veya CMB_MASKED olabilir.

*lpColorMap*<br/>
Bit eşlemler eşlemek için `COLORMAP` gereken renk bilgilerini içeren bir yapıya yönelik işaretçi. Bu parametre NULL ise, işlev varsayılan renk eşlemesini kullanır.

*nMapSize*<br/>
*LpColorMap*tarafından işaret edilen renk haritaları sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `LoadMappedBitmap` düğme glifleri içinde yaygın olarak kullanılan renkleri eşler.

Eşlenmiş bir bit eşlem oluşturma hakkında daha fazla bilgi için, Windows SDK Windows işlevi [CreateMappedBitmap](https://go.microsoft.com/fwlink/p/?linkid=230562) ve [ColorMap](/windows/win32/api/commctrl/ns-commctrl-colormap) yapısına bakın.

##  <a name="loadoembitmap"></a>CBitmap:: LoadOEMBitmap

Windows tarafından kullanılan önceden tanımlanmış bir bit eşlemi yükler.

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>Parametreler

*Nıdbit eşlem*<br/>
Önceden tanımlanmış Windows bit eşlemin KIMLIK numarası. Olası değerler WINDOWS 'dan aşağıda listelenmiştir. Olsun

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

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

OBM_OLD ile başlayan bit eşlem adları 3,0 ' dan önceki Windows sürümleri tarafından kullanılan bit eşlemleri temsil eder.

WINDOWS dahil etmeden önce sabit OEMRESOURCE 'in tanımlanması gerektiğini unutmayın. H **OBM_** sabitlerinden herhangi birini kullanmak için.

##  <a name="operator_hbitmap"></a>CBitmap:: operator HBıX

`CBitmap` Nesnenin ekli Windows GDI işleyicisini almak için bu işleci kullanın.

```
operator HBITMAP() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `CBitmap` nesne tarafından temsil edilen Windows GDI nesnesine yönelik bir tanıtıcı; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir `HBITMAP` nesnenin doğrudan kullanımını destekleyen bir atama işleçtir.

Grafik nesnelerini kullanma hakkında daha fazla bilgi için, Windows SDK [grafik nesneleri](/windows/win32/gdi/graphic-objects) bölümüne bakın.

##  <a name="setbitmapbits"></a>CBitmap:: Setbitmapbitleri

Bit eşlemin bitlerini *lpBits*tarafından verilen bit değerlerine ayarlar.

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>Parametreler

*dwCount*<br/>
*LpBits*tarafından işaret edilen bayt sayısını belirtir.

*lpBits*<br/>
`CBitmap` Nesneye kopyalanacak piksel değerlerini içeren bayt dizisine işaret eder. Bit eşlemin görüntüsünü doğru bir şekilde işleyebilmesi için değerler, CBitmap örneği oluşturulduğunda belirtilen yükseklik, genişlik ve renk derinliği değerlerine uyacak şekilde biçimlendirilmelidir. Daha fazla bilgi için bkz. [CBitmap:: Createbit eşlem](#createbitmap).

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem bitlerini ayarlamak için kullanılan bayt sayısı; işlev başarısız olursa 0.

##  <a name="setbitmapdimension"></a>CBitmap:: SetBitmapDimension

0,1-milimetre ölçüm birimlerindeki bir bit eşleme genişlik ve Yükseklik atar.

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Bit eşlemin genişliğini belirtir (0,1-milimetre ölçüm birimi).

*nHeight*<br/>
Bit eşlemin yüksekliğini belirtir (0,1-milimetre ölçüm birimi).

### <a name="return-value"></a>Dönüş Değeri

Önceki bit eşlem boyutları. Yükseklik nesnenin üye değişkeninde, Width ise `cx` üye değişkenidir. `cy` `CSize`

### <a name="remarks"></a>Açıklamalar

GDI, bir uygulama [GetBitmapDimension](#getbitmapdimension) üye işlevini çağırdığında bu değerleri döndürmeleri dışında kullanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MDI](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
