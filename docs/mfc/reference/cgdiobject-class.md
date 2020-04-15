---
title: CGdiObject Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
ms.openlocfilehash: 0cd7a0e0ed500ee9394b00e8906640e9f950163b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373731"
---
# <a name="cgdiobject-class"></a>CGdiObject Sınıfı

Bit eşlemler, bölgeler, fırçalar, kalemler, paletler ve yazı tipleri gibi çeşitli Windows grafik aygıtı arabirimi (GDI) nesneleri için taban sınıf sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CGdiObject : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CGdiObject::CGdiObject](#cgdiobject)|Bir `CGdiObject` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CGdiObject::Ekle](#attach)|Bir `CGdiObject` nesneye Windows GDI nesnesi bağlar.|
|[CGdiObject::CreateStockObject](#createstockobject)|Bir tutamacı Windows önceden tanımlanmış stok kalemlerinden, fırçalarından veya yazı tiplerinden birine alır.|
|[CGdiObject::DeleteObject](#deleteobject)|Nesneyle ilişkili tüm sistem depolama `CGdiObject` alanını serbest katarak nesneye iliştirilen Windows GDI nesnesini bellekten siler.|
|[CGdiObject::DeleteTempMap](#deletetempmap)|Tarafından oluşturulan `CGdiObject` geçici nesneleri siler. `FromHandle`|
|[CGdiObject::Detach](#detach)|Bir Windows GDI nesnesini `CGdiObject` bir nesneden ayırır ve bir tutamacı Windows GDI nesnesine döndürür.|
|[CGdiObject::FromHandle](#fromhandle)|Bir Windows GDI nesnesine tutamacı verilen bir `CGdiObject` nesneye işaretçiyi döndürür.|
|[CGdiObject::GetObject](#getobject)|Arabelleği nesneye bağlı Windows GDI nesnesini `CGdiObject` açıklayan verilerle doldurur.|
|[CGdiObject::GetObjectType](#getobjecttype)|GDI nesnesinin türünü alır.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|Bu `m_hObject` **this** NULL olmadığı sürece döndürür, bu durumda NULL döndürülür.|
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Fırçanın kaynağını sıfırlar veya mantıksal bir paleti sıfırlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CGdiObject::operatör !=](#operator_neq)|İki GDI nesnesi mantıksal olarak eşit olup olmadığını belirler.|
|[CGdiObject::operator ==](#operator_eq_eq)|İki GDI nesnesi mantıksal olarak eşit olup olmadığını belirler.|
|[CGdiObject::operatör HGDIOBJ](#operator_hgdiobj)|Bağlı Windows GDI nesnesine bir HANDLE alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|Bu nesneye bağlı HBITMAP, HPALETTE, HRGN, HBRUSH, HPEN veya HFONT içeren bir TUTAK.|

## <a name="remarks"></a>Açıklamalar

Asla doğrudan `CGdiObject` bir şey yaratmazsın. Bunun yerine, bir nesneyi türetilmiş sınıflarından `CBrush`birinden oluşturursunuz, örneğin. `CPen`

Daha fazla `CGdiObject`bilgi için [Bkz. Grafik Nesneler.](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cgdiobjectattach"></a><a name="attach"></a>CGdiObject::Ekle

Bir `CGdiObject` nesneye Windows GDI nesnesi bağlar.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Windows GDI nesnesine (örneğin, HPEN veya HBRUSH) bir HANDLE.

### <a name="return-value"></a>Dönüş Değeri

Eki başarılı olursa sıfır olmayan; aksi takdirde 0.

## <a name="cgdiobjectcgdiobject"></a><a name="cgdiobject"></a>CGdiObject::CGdiObject

Bir `CGdiObject` nesne inşa eder.

```
CGdiObject();
```

### <a name="remarks"></a>Açıklamalar

Asla doğrudan `CGdiObject` bir şey yaratmazsın. Bunun yerine, bir nesneyi türetilmiş sınıflarından `Cbrush`birinden oluşturursunuz, örneğin. `CPen`

## <a name="cgdiobjectcreatestockobject"></a><a name="createstockobject"></a>CGdiObject::CreateStockObject

Önceden tanımlanmış stok Windows GDI kalemlerinden, fırçalarından veya yazı tiplerinden birine bir tutamaç alır `CGdiObject` ve GDI nesnesini nesneye bağlar.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
İstenilen stok nesnesinin türünü belirten bir sabit. Uygun değerlerin açıklaması için Windows SDK'daki [GetStockObject](/windows/win32/api/wingdi/nf-wingdi-getstockobject) parametresi *fnObject* parametresini görün.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi, stok kalemi gibi `CPen` Windows GDI nesne türüne karşılık gelen türemiş sınıflardan biriyle çağırın.

## <a name="cgdiobjectdeleteobject"></a><a name="deleteobject"></a>CGdiObject::DeleteObject

Windows GDI nesnesi ile ilişkili tüm sistem depolamasını serbest kılarak ekli Windows GDI nesnesini bellekten siler.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Dönüş Değeri

GDI nesnesi başarıyla silinmişse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CGdiObject` Nesneyle ilişkili depolama bu çağrıdan etkilenmez. Uygulama, şu `DeleteObject` anda `CGdiObject` aygıt bağlamında seçilmiş bir nesneyi aramamalıdır.

Desen fırçası silindiğinde, fırçayla ilişkili bit eşlemi silinmez. Bit eşlemi bağımsız olarak silinmelidir.

## <a name="cgdiobjectdeletetempmap"></a><a name="deletetempmap"></a>CGdiObject::DeleteTempMap

Boşta kalan `CWinApp` zaman işleyicisi `DeleteTempMap` tarafından otomatik `CGdiObject` olarak çağrılır, tarafından `FromHandle`oluşturulan geçici nesneleri siler.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Açıklamalar

`DeleteTempMap`nesneyi silmeden önce geçici `CGdiObject` bir nesneye eklenen Windows `CGdiObject` GDI nesnesini ayırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

## <a name="cgdiobjectdetach"></a><a name="detach"></a>CGdiObject::Detach

Bir Windows GDI nesnesini `CGdiObject` bir nesneden ayırır ve bir tutamacı Windows GDI nesnesine döndürür.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Dönüş Değeri

A `HANDLE` Windows GDI nesnesine ayrılmış; aksi takdirde hiçbir GDI nesnesi eklenmişse NULL.

## <a name="cgdiobjectfromhandle"></a><a name="fromhandle"></a>CGdiObject::FromHandle

Bir Windows GDI nesnesine tutamacı verilen bir `CGdiObject` nesneye işaretçiyi döndürür.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Windows GDI nesnesine HANDLE.

### <a name="return-value"></a>Dönüş Değeri

Geçici veya `CGdiObject` kalıcı olabilecek bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Windows `CGdiObject` GDI nesnesine zaten bağlı olmayan bir nesne `CGdiObject` ise, geçici bir nesne oluşturulur ve eklenir.

Bu `CGdiObject` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olana ve tüm geçici grafik nesnelerinsilindiği zamana kadar geçerlidir. Bunu söylemenin başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olmasıdır.

## <a name="cgdiobjectgetobject"></a><a name="getobject"></a>CGdiObject::GetObject

Arabelleği, belirtilen nesneyi tanımlayan verilerle doldurur.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Parametreler

*nSayısı*<br/>
*lpObject* arabelleği içine kopyalamak için bayt sayısını belirtir.

*lpObject*<br/>
Bilgileri almak için kullanıcı tarafından sağlanan arabelleği işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Alınan bayt sayısı; aksi takdirde 0 bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

İşlev, aşağıdaki listede gösterildiği gibi, türü grafik nesnesinin türüne bağlı olan bir veri yapısı alır:

|Nesne|Arabellek türü|
|------------|-----------------|
|`CPen`|[LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen)|
|`CBrush`|[Logbrush](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|`CFont`|[Logfont](/windows/win32/api/wingdi/ns-wingdi-logfontw)|
|`CBitmap`|[Bitmap](/windows/win32/api/wingdi/ns-wingdi-bitmap)|
|`CPalette`|WORD|
|`CRgn`|Desteklenmiyor|

Nesne bir `CBitmap` nesneyse, `GetObject` bit eşleminin yalnızca genişliğini, yüksekliğini ve renk biçimi bilgilerini döndürür. Gerçek bitcmap kullanılarak [alınabilir::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).

Nesne bir `CPalette` nesneyse, `GetObject` paletteki giriş sayısını belirten bir WORD alır. İşlev, paleti tanımlayan [LOGPALETT](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısını almaz. Bir uygulama CPalette arayarak palet girişleri hakkında bilgi [alabilirsiniz::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).

## <a name="cgdiobjectgetobjecttype"></a><a name="getobjecttype"></a>CGdiObject::GetObjectType

GDI nesnesinin türünü alır.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa nesnenin türü; aksi takdirde 0. Değer aşağıdakilerden biri olabilir:

- OBJ_BITMAP Bitmap

- OBJ_BRUSH Fırçası

- OBJ_FONT Yazı Tipi

- OBJ_PAL Palet

- OBJ_PEN Kalem

- OBJ_EXTPEN Genişletilmiş kalem

- OBJ_REGION Bölgesi

- OBJ_DC Cihaz bağlamı

- OBJ_MEMDC Bellek aygıtı bağlamı

- OBJ_METAFILE Metafile

- metadosya aygıt bağlamı OBJ_METADC

- OBJ_ENHMETAFILE Geliştirilmiş metadosya

- OBJ_ENHMETADC Gelişmiş-metafile aygıt bağlamı

## <a name="cgdiobjectgetsafehandle"></a><a name="getsafehandle"></a>CGdiObject::GetSafeHandle

Bu `m_hObject` **this** NULL olmadığı sürece döndürür, bu durumda NULL döndürülür.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ekli Windows GDI nesnesine bir HANDLE; aksi takdirde hiçbir nesne eklenmişse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, genel tutamak arabirimi paradigmasının bir parçasıdır ve NULL bir tanıtıcı için geçerli veya özel bir değer olduğunda yararlıdır.

### <a name="example"></a>Örnek

  CWnd örneğine [bakın::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).

## <a name="cgdiobjectm_hobject"></a><a name="m_hobject"></a>CGdiObject::m_hObject

Bu nesneye bağlı HBITMAP, HRGN, HBRUSH, HPEN, HPALETTE veya HFONT içeren bir TUTAK.

```
HGDIOBJ m_hObject;
```

## <a name="cgdiobjectoperator-"></a><a name="operator_neq"></a>CGdiObject::operatör !=

İki GDI nesnesi mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Varolan `CGdiObject`bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir GDI nesnesinin sağ taraftaki bir GDI nesnesine eşit olup olmadığını belirler.

## <a name="cgdiobjectoperator-"></a><a name="operator_eq_eq"></a>CGdiObject::operator ==

İki GDI nesnesi mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Varolan `CGdiObject`bir .

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir GDI nesnesinin sağ taraftaki bir GDI nesnesine eşit olup olmadığını belirler.

## <a name="cgdiobjectoperator-hgdiobj"></a><a name="operator_hgdiobj"></a>CGdiObject::operatör HGDIOBJ

Bağlı Windows GDI nesnesine bir HANDLE alır; aksi takdirde hiçbir nesne eklenmişse NULL.

```
operator HGDIOBJ() const;
```

## <a name="cgdiobjectunrealizeobject"></a><a name="unrealizeobject"></a>CGdiObject::UnrealizeObject

Fırçanın kaynağını sıfırlar veya mantıksal bir paleti sıfırlar.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sınıfın `UnrealizeObject` bir üye işlevi olsa da, yalnızca veya `CPalette` nesnelerüzerinde `CBrush` çağrılmalıdır. `CGdiObject`

Nesneler `CBrush` için, `UnrealizeObject` bir sonraki kez bir aygıt bağlamına seçildiğinde verilen fırçanın kaynağını sıfırlamak için sistem yönlendirir. Nesne bir `CPalette` nesneyse, `UnrealizeObject` sistemi paleti daha önce gerçekleştiredilmemiş gibi gerçekleştirmeye yönlendirir. Uygulama CDC çağırır bir sonraki [kez::Belirtilen](../../mfc/reference/cdc-class.md#realizepalette) palet için RealizePalette fonksiyonu, sistem tamamen sistem paleti için mantıksal palet yeniden eşler.

İşlev `UnrealizeObject` stok nesneleri ile kullanılmamalıdır. Yeni `UnrealizeObject` bir fırça kaynağı ayarlandığında [(CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) işlevi) işlev çağrılmalıdır. İşlev, `UnrealizeObject` şu anda seçili fırça veya herhangi bir görüntü bağlamının şu anda seçili paleti için çağrılmamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBitmap Sınıfı](../../mfc/reference/cbitmap-class.md)<br/>
[CBrush Sınıfı](../../mfc/reference/cbrush-class.md)<br/>
[CFont Sınıfı](../../mfc/reference/cfont-class.md)<br/>
[CPalette Sınıfı](../../mfc/reference/cpalette-class.md)<br/>
[CPen Sınıfı](../../mfc/reference/cpen-class.md)<br/>
[CRgn Sınıfı](../../mfc/reference/crgn-class.md)
