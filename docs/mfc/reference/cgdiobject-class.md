---
title: CGdiObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 097d2a636ae277f2391815f531464ed5ee10571f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398202"
---
# <a name="cgdiobject-class"></a>CGdiObject sınıfı

Bir temel sınıf için çeşitli türlerdeki Windows grafik cihaz arabirimi (GDI) nesneleri bit eşlemler, bölgeler, Fırçalar, kalemler, paletler ve yazı tipleri gibi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CGdiObject : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject::CGdiObject](#cgdiobject)|Oluşturur bir `CGdiObject` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject::Attach](#attach)|Bir Windows GDI nesnesine iliştirir bir `CGdiObject` nesne.|
|[CGdiObject::CreateStockObject](#createstockobject)|Bir Windows önceden tanımlanmış stok kalemler, Fırçalar veya yazı tipleri için bir tanıtıcı alır.|
|[CGdiObject::DeleteObject](#deleteobject)|Windows GDI nesnesi iliştirilmiş siler `CGdiObject` nesne nesneyle ilişkili tüm sistem deposu boşaltma tarafından bellek.|
|[CGdiObject::DeleteTempMap](#deletetempmap)|Herhangi bir geçici siler `CGdiObject` tarafından oluşturulmuş nesneleri `FromHandle`.|
|[CGdiObject::Detach](#detach)|Bir Windows GDI nesneden çıkarır bir `CGdiObject` nesne ve Windows GDI nesnesi için bir tanıtıcı döndürür.|
|[CGdiObject::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CGdiObject` bir Windows GDI nesnesi için bir tanıtıcı verilen nesne.|
|[CGdiObject::GetObject](#getobject)|Windows GDI nesnesi açıklayan verileri bir önbellekle dolgular iliştirilmiş `CGdiObject` nesne.|
|[CGdiObject::GetObjectType](#getobjecttype)|GDI nesnenin türünü alır.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|Döndürür `m_hObject` sürece **bu** null, servis talebi NULL döndürülür.|
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Fırça kaynağını sıfırlar veya mantıksal paletini sıfırlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject::operator! =](#operator_neq)|GDI iki nesne eşit değilse mantıksal olarak belirler.|
|[CGdiObject::operator ==](#operator_eq_eq)|GDI nesneleri iki mantıksal olarak eşit olup olmadığını belirler.|
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Ekli Windows GDI nesnesi için bir tanıtıcı alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|HBITMAP, HPALETTE, HRGN, HBRUSH, HPEN veya HFONT içeren bir tanıtıcı, bu nesneye iliştirilmiş.|

## <a name="remarks"></a>Açıklamalar

Asla oluşturma bir `CGdiObject` doğrudan. Bunun yerine, bir nesne, ondan türetilen sınıflardan biri gibi oluşturduğunuz `CPen` veya `CBrush`.

Daha fazla bilgi için `CGdiObject`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="attach"></a>  CGdiObject::Attach

Bir Windows GDI nesnesine iliştirir bir `CGdiObject` nesne.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Bir Windows GDI nesnesi (örneğin, HPEN veya HBRUSH) için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Ek başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject

Oluşturur bir `CGdiObject` nesne.

```
CGdiObject();
```

### <a name="remarks"></a>Açıklamalar

Asla oluşturma bir `CGdiObject` doğrudan. Bunun yerine, bir nesne, ondan türetilen sınıflardan biri gibi oluşturduğunuz `CPen` veya `Cbrush`.

##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject

Önceden tanımlanmış stok Windows GDI kalemler, Fırçalar veya yazı tipleri için bir tanıtıcı alır ve GDI nesnesine iliştirir `CGdiObject` nesne.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
İstenen stok nesne türünü belirten bir sabit değer. Bkz. parametre *fnObject* için [GetStockObject](/windows/desktop/api/wingdi/nf-wingdi-getstockobject) uygun değerlerin bir tanımı için Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sınıflar türetilmiş biri ile bu işlev çağrısı Windows GDI nesne türüne gibi karşılık gelen `CPen` stok kalem için.

##  <a name="deleteobject"></a>  CGdiObject::DeleteObject

Bağlı Windows GDI nesneyi bellekten Windows GDI nesneyle ilişkili tüm sistem depolama azaltarak siler.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Dönüş Değeri

GDI nesnesi başarıyla silindi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İle ilişkili depolama `CGdiObject` nesne bu çağrı tarafından etkilenmez. Bir uygulama değil, çağırmalıdır `DeleteObject` üzerinde bir `CGdiObject` bir cihaz bağlamına seçili olan nesne.

Bir desen Fırçası silindiğinde, fırça ile ilişkili bit eşlem silinmez. Bit eşlem bağımsız olarak silinmesi gerekir.

##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap

Tarafından otomatik olarak adlandırılan `CWinApp` boşta kalma süresi işleyici `DeleteTempMap` herhangi bir geçici siler `CGdiObject` tarafından oluşturulmuş nesneleri `FromHandle`.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Açıklamalar

`DeleteTempMap` geçici bir eklenmiş Windows GDI nesnesi ayırır `CGdiObject` silmeden önce nesne `CGdiObject` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

##  <a name="detach"></a>  CGdiObject::Detach

Bir Windows GDI nesneden çıkarır bir `CGdiObject` nesne ve Windows GDI nesnesi için bir tanıtıcı döndürür.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Dönüş Değeri

A `HANDLE` için Windows GDI nesnesi ayrılır; GDI nesnesi yok bağlıysa, bulunmazsa null değerini DÖNDÜRÜR.

##  <a name="fromhandle"></a>  CGdiObject::FromHandle

Bir işaretçi döndüren bir `CGdiObject` bir Windows GDI nesnesi için bir tanıtıcı verilen nesne.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Bir Windows GDI nesnesi için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CGdiObject` geçici veya kalıcı olabilir.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CGdiObject` nesne zaten iliştirilmemiş geçici, Windows GDI nesnesi `CGdiObject` nesnesi oluşturulur ve bağlı.

Bu geçici `CGdiObject` nesne, yalnızca geçerli uygulama aynı zamanda tüm geçici grafik nesneler silinir kendi olay döngüsü içinde boşta kalma süresi olan zamana kadar. Bunu belirten bir başka yolu geçici bir nesne yalnızca bir pencere iletisi işlenirken geçerli olmasıdır.

##  <a name="getobject"></a>  CGdiObject::GetObject

Arabellek belirtilen bir nesneyi tanımlayan verilerle doldurur.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Parametreler

*nCount*<br/>
İçine kopyalanacak bayt sayısını belirtir *lpObject* arabellek.

*lpObject*<br/>
Bilgi almak için bir kullanıcı tarafından sağlanan arabellek işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Alınan bayt sayısı; Aksi durumda 0 ise bir hata oluşur.

### <a name="remarks"></a>Açıklamalar

İşlev türü grafik nesnenin türüne bağlıdır veri yapısı tarafından aşağıdaki listede gösterildiği gibi alır:

|Nesne|Arabellek türü|
|------------|-----------------|
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|
|`CFont`|[LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)|
|`CBitmap`|[BİT EŞLEM](../../mfc/reference/bitmap-structure.md)|
|`CPalette`|WORD|
|`CRgn`|Desteklenmez|

Nesne ise bir `CBitmap` nesnesi `GetObject` yalnızca genişlik, yükseklik ve bit eşlemin renk biçim bilgilerini döndürür. Gerçek BITS kullanarak alınabilir [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).

Nesne ise bir `CPalette` nesnesi `GetObject` palette giriş sayısını belirten bir sözcük alır. İşlev alamadı [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) paleti tanımlayan yapısını. Bir uygulama çağırarak paleti girdileri hakkında bilgi alabilirsiniz [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).

##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType

GDI nesnenin türünü alır.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa nesnenin türü; Aksi durumda 0. Değerin aşağıdakilerden biri olabilir:

- OBJ_BITMAP bit eşlem

- OBJ_BRUSH fırça

- OBJ_FONT yazı tipi

- OBJ_PAL paleti

- OBJ_PEN kalem

- Kalem OBJ_EXTPEN genişletilmiş

- OBJ_REGION bölge

- OBJ_DC cihaz bağlamı

- OBJ_MEMDC bellek cihaz bağlamı

- OBJ_METAFILE meta dosyası

- OBJ_METADC meta dosyası cihaz bağlamı

- OBJ_ENHMETAFILE Gelişmiş Meta dosyası

- OBJ_ENHMETADC Gelişmiş Meta dosyası cihaz bağlamı

##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle

Döndürür `m_hObject` sürece **bu** null, servis talebi NULL döndürülür.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ekli Windows GDI nesnesi için bir tanıtıcı; hiçbir nesne bağlıysa, bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bu genel tanıtıcı arabirimi paradigma bir parçasıdır ve bir tanıtıcı için geçerli veya özel bir değer NULL olduğunda yararlıdır.

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).

##  <a name="m_hobject"></a>  CGdiObject::m_hObject

HBITMAP, HRGN, HBRUSH, HPEN, HPALETTE veya HFONT içeren bir tanıtıcı, bu nesneye iliştirilmiş.

```
HGDIOBJ m_hObject;
```

##  <a name="operator_neq"></a>  CGdiObject::operator! =

GDI iki nesne eşit değilse mantıksal olarak belirler.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Varolan bir işaretçi `CGdiObject`.

### <a name="remarks"></a>Açıklamalar

İşlecin sol tarafındaki bir GDI nesnesi işlecin sağ tarafındaki bir GDI nesnesi eşit değilse belirler.

##  <a name="operator_eq_eq"></a>  CGdiObject::operator ==

GDI nesneleri iki mantıksal olarak eşit olup olmadığını belirler.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Var olan bir başvuru `CGdiObject`.

### <a name="remarks"></a>Açıklamalar

İşlecin sol tarafındaki bir GDI nesnesi işlecin sağ tarafındaki GDI nesnesine eşit olup olmadığını belirler.

##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ

Ekli Windows GDI nesnesi için bir tanıtıcı alır; hiçbir nesne bağlıysa, bulunmazsa null değerini DÖNDÜRÜR.

```
operator HGDIOBJ() const;
```

##  <a name="unrealizeobject"></a>  CGdiObject::UnrealizeObject

Fırça kaynağını sıfırlar veya mantıksal paletini sıfırlar.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sırada `UnrealizeObject` bir üye işlevidir `CGdiObject` sınıfı, bunu çağrılabilir yalnızca `CBrush` veya `CPalette` nesneleri.

İçin `CBrush` nesneleri `UnrealizeObject` verilen fırça kaynağını bir cihaz bağlamına seçildiğinden açtığında sıfırlamak için yönlendirir. Nesne ise bir `CPalette` nesnesi `UnrealizeObject` bunu değil daha önce gerçekleşen ancak paletini uygulaması için yönlendirir. Uygulama başlatıldığında [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) işlevi için belirtilen paleti, sistemin tamamen sistem paleti mantıksal paleti yeniden eşlemesi.

`UnrealizeObject` İşlevi stok nesneleri ile kullanılmamalıdır. `UnrealizeObject` İşlevi yeni bir fırça kaynağını her çağrılmalıdır (yoluyla [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) işlevi). `UnrealizeObject` İşlevi, değil şu anda seçili fırça veya herhangi bir görüntü bağlamının şu anda seçili palet için çağrılmalıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBitmap Sınıfı](../../mfc/reference/cbitmap-class.md)<br/>
[CBrush Sınıfı](../../mfc/reference/cbrush-class.md)<br/>
[CFont Sınıfı](../../mfc/reference/cfont-class.md)<br/>
[CPalette Sınıfı](../../mfc/reference/cpalette-class.md)<br/>
[CPen Sınıfı](../../mfc/reference/cpen-class.md)<br/>
[CRgn Sınıfı](../../mfc/reference/crgn-class.md)
