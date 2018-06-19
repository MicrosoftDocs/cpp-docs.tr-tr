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
ms.openlocfilehash: ba88269cf37f41cf8a594745eb2e98a57ccf64ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369021"
---
# <a name="cgdiobject-class"></a>CGdiObject sınıfı
Bir temel sınıf çeşitli Windows grafik için bit eşlemler, bölgeler, Fırçalar, kalemler, paletleri ve yazı tipleri gibi cihaz arabirimi (GDI) nesneleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|Oluşturan bir `CGdiObject` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Bir Windows GDI nesnesine ekler bir `CGdiObject` nesnesi.|  
|[CGdiObject::CreateStockObject](#createstockobject)|Windows önceden tanımlanmış stok kalemler, Fırçalar veya yazı tipi için bir tanıtıcı alır.|  
|[CGdiObject::DeleteObject](#deleteobject)|Windows GDI nesnesi iliştirilmiş siler `CGdiObject` nesnesiyle ilişkili tüm sistem depolama boşaltma tarafından bellekten nesnesi.|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|Tüm geçici siler `CGdiObject` tarafından oluşturulan nesneler `FromHandle`.|  
|[CGdiObject::Detach](#detach)|Bir Windows GDI nesneden çıkarır bir `CGdiObject` nesne ve Windows GDI nesnesi için bir işleyici döner.|  
|[CGdiObject::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CGdiObject` Windows GDI nesnesi için bir tanıtıcı verilen nesnesi.|  
|[CGdiObject::GetObject](#getobject)|Windows GDI nesneyi tanımlayan verilerle bir arabellek dolgular iliştirilmiş `CGdiObject` nesnesi.|  
|[CGdiObject::GetObjectType](#getobjecttype)|GDI nesne türünü alır.|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|Döndürür `m_hObject` sürece `this` olan `NULL`, bu durumda `NULL` döndürülür.|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Fırça kökeni sıfırlar veya bir mantıksal paleti sıfırlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|İki GDI nesneleri eşit değilse mantıksal olarak belirler.|  
|[CGdiObject::operator ==](#operator_eq_eq)|İki GDI nesneleri mantıksal olarak eşit olup olmadığını belirler.|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Alır bir `HANDLE` ekli Windows GDI nesnesine.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|A `HANDLE` içeren `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, veya `HFONT` bu nesneye iliştirilmiş.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturduğunuz bir `CGdiObject` doğrudan. Bunun yerine, bir nesne türetilmiş sınıflarından biri gibi oluşturduğunuz `CPen` veya `CBrush`.  
  
 Daha fazla bilgi için `CGdiObject`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="attach"></a>  CGdiObject::Attach  
 Bir Windows GDI nesnesine ekler bir `CGdiObject` nesnesi.  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `hObject`  
 A `HANDLE` Windows GDI nesnesi için (örneğin, `HPEN` veya `HBRUSH`).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ek başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject  
 Oluşturan bir `CGdiObject` nesnesi.  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturduğunuz bir `CGdiObject` doğrudan. Bunun yerine, bir nesne türetilmiş sınıflarından biri gibi oluşturduğunuz `CPen` veya **Cbrush**.  
  
##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject  
 Önceden tanımlanmış stok Windows GDI kalemler, Fırçalar veya yazı tipi için bir tanıtıcı alır ve GDI nesnesine ekler `CGdiObject` nesnesi.  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 İstenen stok nesne türünü belirten bir sabit değer. Bkz. parametre *fnObject* için [GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925) uygun değerleri bir açıklaması için Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev biriyle türetilmiş sınıfları çağrısı Windows GDI nesne türüne gibi karşılık gelen `CPen` stok kalem için.  
  
##  <a name="deleteobject"></a>  CGdiObject::DeleteObject  
 Ekli Windows GDI nesnesi Windows GDI nesneyle ilişkili tüm sistem depolama azaltarak bellekten siler.  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 GDI nesnesi başarıyla silindiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili depolama `CGdiObject` nesne bu çağrısı tarafından etkilenmez. Bir uygulama değil çağırmalıdır `DeleteObject` üzerinde bir `CGdiObject` bir cihaz bağlamına şu anda seçili nesne.  
  
 Bir desen Fırçası silindiğinde, fırça ile ilişkili bit eşlem silinmez. Bit eşlem bağımsız olarak silinmesi gerekir.  
  
##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap  
 Tarafından otomatik olarak çağrılır `CWinApp` boşta kalma süresi işleyici `DeleteTempMap` herhangi geçici siler `CGdiObject` tarafından oluşturulan nesneler `FromHandle`.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `DeleteTempMap` geçici bir eklenen Windows GDI nesnesi ayırır `CGdiObject` silmeden önce nesne `CGdiObject` nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>  CGdiObject::Detach  
 Bir Windows GDI nesneden çıkarır bir `CGdiObject` nesne ve Windows GDI nesnesi için bir işleyici döner.  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `HANDLE` ayrılmış; Aksi takdirde Windows GDI nesnesi **NULL** GDI nesnesi yok bağlıysa.  
  
##  <a name="fromhandle"></a>  CGdiObject::FromHandle  
 Bir işaretçi döndüren bir `CGdiObject` Windows GDI nesnesi için bir tanıtıcı verilen nesnesi.  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `hObject`  
 A `HANDLE` Windows GDI nesnesine.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CGdiObject` geçici veya kalıcı olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CGdiObject` nesne zaten iliştirilmemiş geçici bir Windows GDI nesne `CGdiObject` nesnesi oluşturulur ve bağlı.  
  
 Bu geçici `CGdiObject` nesnesidir yalnızca geçerli uygulama aynı zamanda tüm geçici grafik nesneleri silinir, olay döngüde boşta kalma süresi sahip zamana kadar. Bu bildiren başka bir şekilde geçici nesne yalnızca bir pencere ileti işleme sırasında geçerli olmasıdır.  
  
##  <a name="getobject"></a>  CGdiObject::GetObject  
 Arabellek belirtilen bir nesneyi tanımlayan verileri ile doldurur.  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nCount`  
 İçine kopyalanacak bayt sayısını belirtir `lpObject` arabellek.  
  
 `lpObject`  
 Bilgi almak için bir kullanıcı tarafından sağlanan arabellek noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Alınan bayt sayısı; Aksi halde 0 ise bir hata oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev türü grafik nesne türüne bağlı bir veri yapısı tarafından aşağıdaki listede gösterildiği gibi alır:  
  
|Nesne|Arabellek türü|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[BİT EŞLEM](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|Desteklenmez|  
  
 Nesne ise bir `CBitmap` nesnesi `GetObject` yalnızca genişlik, yükseklik ve bit eşlem renk biçimi bilgileri döndürür. Gerçek BITS kullanarak alınabilir [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).  
  
 Nesne ise bir `CPalette` nesnesi `GetObject` alır bir **WORD** palette girdilerinin sayısını belirtir. İşlev alamadı [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) palet tanımlar yapısı. Bir uygulama çağırarak paleti girdileri hakkında bilgi edinebilirsiniz [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).  
  
##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType  
 GDI nesne türünü alır.  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa nesne türünü; Aksi takdirde 0. Değerin aşağıdakilerden biri olabilir:  
  
- **OBJ_BITMAP** bit eşlem  
  
- **OBJ_BRUSH** fırça  
  
- **OBJ_FONT** yazı tipi  
  
- **OBJ_PAL** paleti  
  
- **OBJ_PEN** kalem  
  
- **OBJ_EXTPEN** genişletilmiş kalem  
  
- **OBJ_REGION** bölge  
  
- **OBJ_DC** cihaz bağlamı  
  
- **OBJ_MEMDC** bellek cihaz bağlamı  
  
- **OBJ_METAFILE** meta dosyası  
  
- **OBJ_METADC** meta dosyası cihaz bağlamı  
  
- **OBJ_ENHMETAFILE** Gelişmiş Meta dosyası  
  
- **OBJ_ENHMETADC** geliştirilmiş meta dosyası cihaz bağlamı  
  
##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle  
 Döndürür `m_hObject` sürece **bu** olan **NULL**, bu durumda **NULL** döndürülür.  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `HANDLE` nesnesine ekli Windows GDI; Aksi halde **NULL** hiçbir nesne bağlıysa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genel tanıtıcı arabirimi kip bir parçasıdır ve ne zaman kullanışlıdır **NULL** bir tanıtıcı için geçerli veya özel bir değer.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).  
  
##  <a name="m_hobject"></a>  CGdiObject::m_hObject  
 A `HANDLE` içeren `HBITMAP`, **HRGN**, `HBRUSH`, `HPEN`, `HPALETTE`, veya **HFONT** bu nesneye iliştirilmiş.  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>  CGdiObject::operator! =  
 İki GDI nesneleri eşit değilse mantıksal olarak belirler.  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `obj`  
 Var olan bir işaretçi `CGdiObject`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sol tarafta GDI nesnesi sağ tarafında GDI nesnesine eşit olup olmadığını belirler.  
  
##  <a name="operator_eq_eq"></a>  CGdiObject::operator ==  
 İki GDI nesneleri mantıksal olarak eşit olup olmadığını belirler.  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `obj`  
 Var olan bir başvuru `CGdiObject`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sol tarafta GDI nesnesi sağ tarafında GDI nesnesine eşit olup olmadığını belirler.  
  
##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ  
 Alır bir `HANDLE` nesnesine ekli Windows GDI; Aksi halde **NULL** hiçbir nesne bağlıysa.  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>  CGdiObject::UnrealizeObject  
 Fırça kökeni sıfırlar veya bir mantıksal paleti sıfırlar.  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sırada `UnrealizeObject` bir üye işlevidir `CGdiObject` sınıfı, onu çağrılabilir yalnızca `CBrush` veya `CPalette` nesneleri.  
  
 İçin `CBrush` nesneleri `UnrealizeObject` verilen fırça kökeni, seçili bir cihaz bağlamına sonraki saatini sıfırlamak için yönlendirir. Nesne ise bir `CPalette` nesnesi `UnrealizeObject` onu değil daha önce gerçekleşen gibi sorgulamanıza palet hayata geçirmek için sistem yönlendirir. Uygulama başlatıldığında [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) işlevi için belirtilen palet, sistem tamamen sistem paleti mantıksal paletindeki remaps.  
  
 `UnrealizeObject` İşlevi stok nesneleriyle kullanılmamalıdır. `UnrealizeObject` Yeni fırça kaynak her işlev'in çağrılabilir gerekir (yoluyla [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) işlevi). `UnrealizeObject` İşlevi, değil şu anda seçili fırça veya şu anda seçili paletini her görüntü bağlam için çağrılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CBitmap sınıfı](../../mfc/reference/cbitmap-class.md)   
 [CBrush sınıfı](../../mfc/reference/cbrush-class.md)   
 [CFont sınıfı](../../mfc/reference/cfont-class.md)   
 [CPalette sınıfı](../../mfc/reference/cpalette-class.md)   
 [CPen sınıfı](../../mfc/reference/cpen-class.md)   
 [CRgn Sınıfı](../../mfc/reference/crgn-class.md)
