---
title: CGdiObject sınıfı
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
ms.openlocfilehash: ea82e2c667dcbd476d22ed23085d409b448b27ed
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506250"
---
# <a name="cgdiobject-class"></a>CGdiObject sınıfı

Bit eşlemler, bölgeler, fırçalar, kalemler, paletler ve yazı tipleri gibi çeşitli türlerde Windows grafik cihaz arabirimi (GDI) nesneleri için bir temel sınıf sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CGdiObject : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject:: CGdiObject](#cgdiobject)|Bir `CGdiObject` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject:: Attach](#attach)|`CGdiObject` Nesnesine bir Windows GDI nesnesi ekler.|
|[CGdiObject:: Createstokobject](#createstockobject)|Windows önceden tanımlanmış hisse senedi, fırçalar veya yazı tiplerinden birine yönelik bir tanıtıcı alır.|
|[CGdiObject::D eleteObject](#deleteobject)|Nesneyle ilişkili tüm sistem depolama alanını boşaltarak `CGdiObject` , nesneye eklenen Windows GDI nesnesini bellekten siler.|
|[CGdiObject::D eleteTempMap](#deletetempmap)|`CGdiObject` Tarafından`FromHandle`oluşturulan geçici nesneleri siler.|
|[CGdiObject::D etach](#detach)|Bir Windows GDI nesnesini bir `CGdiObject` nesneden ayırır ve Windows GDI nesnesine bir tanıtıcı döndürür.|
|[CGdiObject:: FromHandle](#fromhandle)|Bir Windows GDI nesnesine bir `CGdiObject` tanıtıcı verilen nesneye yönelik bir işaretçi döndürür.|
|[CGdiObject:: GetObject](#getobject)|`CGdiObject` Nesneye eklenen Windows GDI nesnesini açıklayan verilerle bir arabelleği doldurur.|
|[CGdiObject:: GetObjectType](#getobjecttype)|GDI nesnesinin türünü alır.|
|[CGdiObject:: GetSafeHandle](#getsafehandle)|Null `m_hObject` değer döndürülmediği takdirde döndürür; **Bu** durumda null döndürülür.|
|[CGdiObject:: UnrealizeObject](#unrealizeobject)|Bir fırçanın kaynağını sıfırlar veya bir mantıksal paleti sıfırlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject:: operator! =](#operator_neq)|İki GDI nesnesinin mantıksal olarak eşit olup olmadığını belirler.|
|[CGdiObject:: operator = =](#operator_eq_eq)|İki GDI nesnesinin mantıksal olarak eşit olup olmadığını belirler.|
|[CGdiObject:: operator HGDIOBJ](#operator_hgdiobj)|Ekli Windows GDI nesnesine bir tanıtıcı alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject:: m_hObject](#m_hobject)|Bu nesneye eklenen HBıX, HPALETTE, HRGN, HFıRÇA, HPEN veya HFONT 'u içeren bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Hiçbir şekilde `CGdiObject` doğrudan oluşturmayın. Bunun yerine, veya `CPen` `CBrush`gibi türetilmiş sınıflarından birindeki bir nesne oluşturursunuz.

Hakkında `CGdiObject`daha fazla bilgi için bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="attach"></a>CGdiObject:: Attach

`CGdiObject` Nesnesine bir Windows GDI nesnesi ekler.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Windows GDI nesnesine yönelik bir tanıtıcı (örneğin, HPEN veya HBRUSH).

### <a name="return-value"></a>Dönüş Değeri

Ek başarılı olursa sıfır dışı; Aksi takdirde 0.

##  <a name="cgdiobject"></a>CGdiObject:: CGdiObject

Bir `CGdiObject` nesnesi oluşturur.

```
CGdiObject();
```

### <a name="remarks"></a>Açıklamalar

Hiçbir şekilde `CGdiObject` doğrudan oluşturmayın. Bunun yerine, veya `CPen` `Cbrush`gibi türetilmiş sınıflarından birindeki bir nesne oluşturursunuz.

##  <a name="createstockobject"></a>CGdiObject:: Createstokobject

Önceden tanımlanmış hisse senedi Windows GDI kalemleri, fırçaları veya yazı tiplerden birine yönelik bir tanıtıcı alır ve GDI nesnesini `CGdiObject` nesneye ekler.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
İstenen hisse senedi nesnesi türünü belirten bir sabit. Uygun değerlerin bir açıklaması için Windows SDK, bkz. [Getıstokobject](/windows/win32/api/wingdi/nf-wingdi-getstockobject) Için *fnObject* parametresi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi, `CPen` bir hisse senedi kalemi gibi Windows GDI nesne türüne karşılık gelen türetilmiş sınıflardan biriyle çağırın.

##  <a name="deleteobject"></a>CGdiObject::D eleteObject

Windows GDI nesnesiyle ilişkili tüm sistem depolama alanını boşaltarak ekli Windows GDI nesnesini bellekten siler.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Dönüş Değeri

GDI nesnesi başarıyla silinmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CGdiObject` Nesneyle ilişkili depolama alanı bu çağrıdan etkilenmez. Uygulama, şu anda bir `DeleteObject` cihaz bağlamına `CGdiObject` seçili olan bir nesneyi çağırmamalıdır.

Bir desenli fırça silindiğinde, fırçayla ilişkili bit eşlem silinmez. Bit eşlemin bağımsız olarak silinmesi gerekir.

##  <a name="deletetempmap"></a>CGdiObject::D eleteTempMap

, `CWinApp` Boşta kalma süresi işleyicisi tarafından otomatik olarak çağırılır `DeleteTempMap` , tarafından `FromHandle`oluşturulan `CGdiObject` geçici nesneleri siler.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Açıklamalar

`DeleteTempMap`nesne silinmeden önce geçici `CGdiObject` bir nesneye eklenen Windows GDI nesnesini ayırır. `CGdiObject`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

##  <a name="detach"></a>CGdiObject::D etach

Bir Windows GDI nesnesini bir `CGdiObject` nesneden ayırır ve Windows GDI nesnesine bir tanıtıcı döndürür.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Windows `HANDLE` GDI nesnesine bir ayrılır; Aksi takdirde, herhangi bir GDI nesnesi ekli değilse null olur.

##  <a name="fromhandle"></a>CGdiObject:: FromHandle

Bir Windows GDI nesnesine bir `CGdiObject` tanıtıcı verilen nesneye yönelik bir işaretçi döndürür.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Windows GDI nesnesine yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Geçici veya kalıcı olabilecek `CGdiObject` bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir `CGdiObject` nesne Windows GDI nesnesine zaten iliştirilmişse, geçici `CGdiObject` bir nesne oluşturulur ve eklenir.

Bu geçici `CGdiObject` nesne yalnızca uygulamanın olay döngüsünde süresi bir sonraki sefer, tüm geçici grafik nesneleri silindiği zaman geçerli olur. Bunun başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olduğu durumdur.

##  <a name="getobject"></a>CGdiObject:: GetObject

Belirtilen nesneyi tanımlayan verilerle bir arabelleği doldurur.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
*LpObject* arabelleğine kopyalanacak bayt sayısını belirtir.

*lpObject*<br/>
Bilgileri almak için Kullanıcı tarafından sağlanan bir arabelleğe işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Alınan bayt sayısı; Aksi takdirde 0 bir hata oluşur.

### <a name="remarks"></a>Açıklamalar

İşlevi, aşağıdaki listede gösterildiği gibi, türü grafik nesnesinin türüne bağlı olan bir veri yapısını alır:

|Nesne|Arabellek türü|
|------------|-----------------|
|`CPen`|[LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen)|
|`CBrush`|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|`CFont`|[GÜNLÜĞE KAYDETME YAZI TİPİ](/windows/win32/api/wingdi/ns-wingdi-logfontw)|
|`CBitmap`|[BITEŞ](/windows/win32/api/wingdi/ns-wingdi-bitmap)|
|`CPalette`|WORD|
|`CRgn`|Desteklenmez|

Nesne bir `CBitmap` nesnese, `GetObject` yalnızca bit eşlemin genişlik, yükseklik ve renk biçimi bilgilerini döndürür. Gerçek bitler [CBitmap:: GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits)kullanılarak alınabilir.

Nesne bir `CPalette` nesnedir, `GetObject` paletteki giriş sayısını belirten bir sözcük alır. İşlev, paleti tanımlayan [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısını almaz. Bir uygulama, [CPalette:: GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)çağırarak palet girişleri hakkında bilgi alabilir.

##  <a name="getobjecttype"></a>CGdiObject:: GetObjectType

GDI nesnesinin türünü alır.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa nesnenin türü; Aksi takdirde 0. Değer aşağıdakilerden biri olabilir:

- OBJ_BITMAP bit eşlem

- OBJ_BRUSH fırçası

- OBJ_FONT yazı tipi

- OBJ_PAL paleti

- OBJ_PEN kalemi

- OBJ_EXTPEN genişletilmiş kalem

- OBJ_REGION bölgesi

- OBJ_DC cihaz bağlamı

- OBJ_MEMDC bellek cihaz bağlamı

- OBJ_METAFILE meta dosyası

- OBJ_METADC meta dosyası cihaz bağlamı

- OBJ_ENHMETAFILE gelişmiş meta dosyası

- OBJ_ENHMETADC gelişmiş-meta dosyası cihaz bağlamı

##  <a name="getsafehandle"></a>CGdiObject:: GetSafeHandle

Null `m_hObject` değer döndürülmediği takdirde döndürür; **Bu** durumda null döndürülür.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ekli Windows GDI nesnesine yönelik bir tanıtıcı; Aksi takdirde, hiçbir nesne iliştirilmişse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, genel tanıtıcı arabirim paradigmasının bir parçasıdır ve NULL ya da bir tanıtıcı için özel bir değer olduğunda faydalıdır.

### <a name="example"></a>Örnek

  [CWnd:: IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled)örneğine bakın.

##  <a name="m_hobject"></a>CGdiObject:: m_hObject

Bu nesneye eklenen HBıX, HRGN, HFıRÇA, HPEN, HPALETI veya HFONT içeren bir tanıtıcı.

```
HGDIOBJ m_hObject;
```

##  <a name="operator_neq"></a>CGdiObject:: operator! =

İki GDI nesnesinin mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Var olan `CGdiObject`bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir GDI nesnesinin sağ taraftaki bir GDI nesnesine eşit olup olmadığını belirler.

##  <a name="operator_eq_eq"></a>CGdiObject:: operator = =

İki GDI nesnesinin mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Var olan `CGdiObject`bir başvuru.

### <a name="remarks"></a>Açıklamalar

Sol taraftaki bir GDI nesnesinin sağ taraftaki bir GDI nesnesine eşit olup olmadığını belirler.

##  <a name="operator_hgdiobj"></a>CGdiObject:: operator HGDIOBJ

Ekli Windows GDI nesnesine bir tanıtıcı alır; Aksi takdirde, hiçbir nesne iliştirilmişse NULL.

```
operator HGDIOBJ() const;
```

##  <a name="unrealizeobject"></a>CGdiObject:: UnrealizeObject

Bir fırçanın kaynağını sıfırlar veya bir mantıksal paleti sıfırlar.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

, `UnrealizeObject` `CGdiObject` Sınıfının bir üye işlevi olsa da, yalnızca `CBrush` veya `CPalette` nesnelerinde çağrılmalıdır.

Nesneler `CBrush` için, `UnrealizeObject` bir sonraki sefer bir cihaz bağlamına seçildiği zaman, sistemi verilen fırçanın kaynağını sıfırlamasına yöneltir. Nesne bir `CPalette` nesnese, `UnrealizeObject` daha önce gerçekleştirilmese de, sistemi paleti fark etmek için yönlendirir. Uygulama, belirtilen palet için [CDC:: RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) işlevini bir sonraki çağırdığında, sistem mantıksal paleti sistem paletiyle tamamen yeniden eşler.

İşlev `UnrealizeObject` , stok nesneleriyle birlikte kullanılmamalıdır. Her yeni fırça kaynağı ayarlandığında işlevinçağrılmasıgerekir(CDC::setbrühorgişleviyoluyla).`UnrealizeObject` [](../../mfc/reference/cdc-class.md#setbrushorg) `UnrealizeObject` İşlevin Şu anda seçili olan fırça veya herhangi bir görüntüleme bağlamının seçili paleti için çağrılmaması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBitmap Sınıfı](../../mfc/reference/cbitmap-class.md)<br/>
[CBrush Sınıfı](../../mfc/reference/cbrush-class.md)<br/>
[CFont Sınıfı](../../mfc/reference/cfont-class.md)<br/>
[CPalette Sınıfı](../../mfc/reference/cpalette-class.md)<br/>
[CPen Sınıfı](../../mfc/reference/cpen-class.md)<br/>
[CRgn Sınıfı](../../mfc/reference/crgn-class.md)
