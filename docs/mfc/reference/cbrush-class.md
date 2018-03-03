---
title: "CBrush sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
dev_langs:
- C++
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2c60be4501e14c1a3b55789905be1fb6e753731
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cbrush-class"></a>CBrush sınıfı
Bir Windows grafik cihaz arabirimi (GDI) fırça yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|Oluşturan bir `CBrush` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Fırça stil, renk ve belirtilen desen ile başlatır bir [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) yapısı.|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|CİHAZDAN bağımsız bit eşlem (DIB) tarafından belirtilen desenle fırça başlatır.|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|Fırça belirtilen taranmış desen ve renk ile başlatır.|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|Bir bit eşlem tarafından belirtilen desenle fırça başlatır.|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|Fırça belirtilen düz renk ile başlatır.|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Varsayılan sistem renkli fırça oluşturur.|  
|[CBrush::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CBrush` nesnesi tanıtıcı Windows verildiğinde `HBRUSH` nesnesi.|  
|[CBrush::GetLogBrush](#getlogbrush)|Alır bir [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) yapısı.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](#operator_hbrush)|Bağlı Windows işleyici döner `CBrush` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılacak bir `CBrush` nesne, oluşturmak bir `CBrush` nesne ve herhangi bir ağa geçirin `CDC` fırça gerektirir üye işlevi.  
  
 Fırçalar çizgili veya desenleri düz, olabilir.  
  
 Daha fazla bilgi için `CBrush`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cbrush"></a>CBrush::CBrush  
 Oluşturan bir `CBrush` nesnesi.  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `crColor`  
 RGB renk olarak fırça ön plan rengini belirtir. Fırça çizgili varsa, bu parametre tarama rengini belirtir.  
  
 `nIndex`  
 Fırça tarama stilini belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- `HS_BDIAGONAL`Aşağı tarama 45 derecede (soldan sağa)  
  
- `HS_CROSS`Yatay ve dikey bir çapraz tarama  
  
- `HS_DIAGCROSS`45 derecede çapraz tarama  
  
- `HS_FDIAGONAL`45 derecede yukarı tarama (soldan sağa)  
  
- `HS_HORIZONTAL`Yatay tarama  
  
- `HS_VERTICAL`Dikey tarama  
  
 `pBitmap`  
 İşaret eden bir `CBitmap` ile fırça boyar bir bit eşlem belirtir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CBrush`Oluşturucular dört aşırı yüklü. Oluşturucu bağımsız değişken içermeyen bir başlatılmamış yapıları `CBrush` nesnesi, kullanılmadan önce başlatılması gerekir.  
  
 Bağımsız değişkenler olmadan Oluşturucusu kullanırsanız, sonuç başlatmalıdır `CBrush` nesnesi ile [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), veya [CreateDIBPatternBrush](#createdibpatternbrush). Bağımsız değişken almayan oluşturucular birini kullanırsanız, daha sonra başka başlatma gereklidir. Bağımsız değişken içermeyen Oluşturucusu her zaman başarılı olur ancak, bir hatayla karşılaşılmazsa oluşturucular bağımsız değişkenlere sahip bir özel durum.  
  
 Tek bir oluşturucu [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) parametresi belirtilen renkle düz fırça oluşturur. Renk bir RGB değeri belirtir ve ile oluşturulan `RGB` makrosu Windows. H.  
  
 Yapıcı, iki parametre ile bir tarama fırça oluşturur. `nIndex` Parametresi, taranmış bir desen dizinini belirtir. `crColor` Parametresi rengi belirtir.  
  
 Oluşturucu bir `CBitmap` parametresi desenli fırça oluşturur. Parametre bir bit eşlem tanımlar. Bit eşlem kullanılarak oluşturulan varsayılır [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), veya [ CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). En az bir dolgu deseni kullanılacak bir bit eşlem için 8 x 8 piksel boyutudur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="createbrushindirect"></a>CBrush::CreateBrushIndirect  
 Fırça stil, renk ve belirtilen desen ile başlatır bir [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) yapısı.  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpLogBrush*  
 İşaret eden bir [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) fırça hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.  
  
 Geçerli metin ve arka plan renkleri kullanarak tek renkli (1 düzlemi, 1 bit / piksel) bit eşlem kullanılarak oluşturulan bir fırça çizilir. Geçerli metin rengiyle 0 olarak ayarlanmış bir bit tarafından temsil edilen piksel çizilir. 1 olarak ayarlanmış bir bit tarafından temsil edilen piksel geçerli arka plan rengiyle çizilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush  
 CİHAZDAN bağımsız bit eşlem (DIB) tarafından belirtilen desen ile fırça başlatır.  
  
```  
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,  
    UINT nUsage);

 
BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,  
    UINT nUsage);
```  
  
### <a name="parameters"></a>Parametreler  
 *hPackedDIB*  
 Paketlenmiş CİHAZDAN bağımsız bit eşlem (DIB) içeren bir genel bellek nesnesi tanımlar.  
  
 *nUsage*  
 Belirtir olup olmadığını **bmiColors []** alanlarının [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) veri yapısı ("DIB paketlenmiş" bir parçası), şu anda gerçekleşen mantıksal palet açık RGB değerleri veya dizinleri içerir. Parametresi şu değerlerden biri olmalıdır:  
  
- **DIB_PAL_COLORS** renk tablosu 16 bit dizinleri dizisi oluşur.  
  
- **DIB_RGB_COLORS** renk tablosu değişmez değer RGB değerleri içerir.  
  
 *lpPackedDIB*  
 İşaret oluşan bir paketlenmiş DIB bir `BITMAPINFO` bit eşlem piksel tanımlayan bir bayt dizisi tarafından hemen ardından yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Fırça sonradan tarama işlemlerini destekleyen herhangi bir cihaz bağlamı için seçilebilir.  
  
 İki sürüm DIB işleme yönteminde farklılık gösterir:  
  
-   İlk sürümünde bir tanıtıcı DIB elde etmek için Windows çağrısı **GlobalAlloc** işlevi bir genel bellek bloğu ayrılamadı ve ardından bellek paketlenmiş DIB ile doldurun.  
  
-   İkinci sürümünde çağırmak ise gerekli değildir **GlobalAlloc** paketlenmiş DIB için bellek ayrılamadı.  
  
 Paketlenmiş DIB oluşan bir `BITMAPINFO` bit eşlem piksel tanımlayan bayt dizisi tarafından hemen ardından veri yapısı. Bit eşlemler dolgu deseni olarak kullanılan 8 x 8 piksel olmalıdır. Bit eşlem büyükse, Windows yalnızca ilk 8 satır ve 8 bit eşlem sol üst köşesindeki piksel sütunlarının karşılık gelen BITS kullanarak dolgu deseni oluşturur.  
  
 Bir uygulama bir tek renkli cihaz bağlamına iki renkli DIB Desen fırçası seçtiğinde, Windows DIB belirtilen renkleri yoksayar ve bunun yerine cihaz bağlamı geçerli metin ve arka plan renklerini kullanarak Desen fırçası görüntüler. Metin rengi kullanarak DIB (uzaklığındaki 0 DIB renk tablosundaki) ilk rengi ile eşlenmiş piksel görüntülenir. İkinci rengi (1 uzaklığından renk tablosundaki) eşlenmiş piksel arka plan rengini kullanarak görüntülenir.  
  
 Aşağıdaki Windows işlevleri kullanma hakkında daha fazla bilgi için Windows SDK'sı bakın:  
  
- [CreateDIBPatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183492) (Bu işlev yalnızca 3.0'den önceki Windows sürümleri için yazılmış uygulamalarla uyumluluk için sağlanır; kullanın **CreateDIBPatternBrushPt** işlevi.)  
  
- [CreateDIBPatternBrushPt](http://msdn.microsoft.com/library/windows/desktop/dd183493) (Bu işlev Win32 tabanlı uygulamalar için kullanılmalıdır.)  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="createhatchbrush"></a>CBrush::CreateHatchBrush  
 Fırça belirtilen taranmış desen ve renk ile başlatır.  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Fırça tarama stilini belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- `HS_BDIAGONAL`Aşağı tarama 45 derecede (soldan sağa)  
  
- `HS_CROSS`Yatay ve dikey bir çapraz tarama  
  
- `HS_DIAGCROSS`45 derecede çapraz tarama  
  
- `HS_FDIAGONAL`45 derecede yukarı tarama (soldan sağa)  
  
- `HS_HORIZONTAL`Yatay tarama  
  
- `HS_VERTICAL`Dikey tarama  
  
 `crColor`  
 Bir RGB rengi (tarama rengi) fırça ön plan rengini belirtir. Bkz: [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) daha fazla bilgi için Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="createpatternbrush"></a>CBrush::CreatePatternBrush  
 Bir bit eşlem tarafından belirtilen desenle fırça başlatır.  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBitmap`  
 Bir bit eşlem tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Fırça sonradan tarama işlemlerini destekleyen herhangi bir cihaz bağlamı için seçilebilir. Tarafından tanımlanan bit eşlem `pBitmap` kullanarak normalde başlatılmamış [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), veya [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) işlevi.  
  
 Bit eşlemler dolgu deseni olarak kullanılan 8 x 8 piksel olmalıdır. Bit eşlem büyükse, Windows yalnızca ilk 8 satır ve sütun bit eşlemi sol üst köşesindeki piksel karşılık gelen BITS kullanın.  
  
 Bir desen Fırçası ilişkili bit eşlem etkilemeden silinebilir. Başka bir deyişle, bit eşlem Desen fırçaları herhangi bir sayıda oluşturmak için kullanılabilir.  
  
 Geçerli metin ve arka plan renkleri kullanarak tek renkli bit eşlem (1 Renk düzlemi, 1 bit / piksel) kullanılarak oluşturulmuş bir fırça çizilir. 0 olarak ayarlanmış bir bit tarafından temsil edilen piksel geçerli metin rengini ile çizilir. 1 olarak ayarlanmış bir bit tarafından temsil edilen piksel geçerli arka plan rengiyle çizilir.  
  
 Kullanma hakkında bilgi için [CreatePatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183508), bir Windows işlev, Windows SDK konusuna bakın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="createsolidbrush"></a>CBrush::CreateSolidBrush  
 Belirtilen bir düz renk ile fırça başlatır.  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>Parametreler  
 `crColor`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) yapısı fırça rengini belirtir. Renk bir RGB değeri belirtir ve ile oluşturulan `RGB` makrosu Windows. H.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.  
  
 Bir uygulama bittiği tarafından oluşturulan fırça kullanarak `CreateSolidBrush`, cihaz bağlamı dışında fırça seçmeniz gerekir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CBrush::CBrush](#cbrush).  
  
##  <a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush  
 Fırça Rengi başlatır.  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Bir renk dizini belirtir. Bu değer 21 pencere öğeleri birini boyamak için kullanılan renk karşılık gelir. Bkz: [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) değerler listesi için Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.  
  
 Bir uygulama bittiği tarafından oluşturulan fırça kullanarak `CreateSysColorBrush`, cihaz bağlamı dışında fırça seçmeniz gerekir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="fromhandle"></a>CBrush::FromHandle  
 Bir işaretçi döndüren bir `CBrush` nesnesi tanıtıcı Windows verildiğinde [HBRUSH](#operator_hbrush) nesnesi.  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 `hBrush`  
 `HANDLE`bir Windows GDI fırça.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CBrush` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CBrush` nesne zaten iliştirilmemiş tanıtıcıyı, geçici bir `CBrush` nesnesi oluşturulur ve bağlı. Bu geçici `CBrush` nesne geçerli uygulamanın kendi olay döngüde boşta kalma süresi varsa yalnızca zamana kadar. Şu anda tüm geçici grafik nesneler silinir. Diğer bir deyişle, yalnızca bir pencere ileti işleme sırasında geçici nesne geçerli değil.  
  
 Grafik nesneleri kullanma hakkında daha fazla bilgi için bkz: [grafik nesneleri](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows SDK.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CBrush::CBrush](#cbrush).  
  
##  <a name="getlogbrush"></a>CBrush::GetLogBrush  
 Almak için bu üye işlevini çağırın `LOGBRUSH` yapısı.  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>Parametreler  
 `pLogBrush`  
 İşaret eden bir [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) fırça hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa ve `pLogBrush` geçerli bir işaretçi dönüş değeri arabelleğe depolanan bayt sayısıdır.  
  
 İşlev başarılı olursa, ve `pLogBrush` olan **NULL**, dönüş değerdir işlevi bilgiyi tutmak için gereken bayt sayısını arabelleğe depolamak.  
  
 İşlev başarısız olursa, dönüş değeri 0'dır.  
  
### <a name="remarks"></a>Açıklamalar  
 `LOGBRUSH` Stili, renk ve fırça desenini yapısını tanımlar.  
  
 Örneğin, arama `GetLogBrush` belirli rengini veya desenini bir bit eşlem eşleşecek şekilde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="operator_hbrush"></a>CBrush::operator HBRUSH  
 Ekli Windows GDI işleyicisini almak için bu işleci kullanın `CBrush` nesnesi.  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CBrush` nesne; Aksi halde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç doğrudan kullanımını destekleyen bir atama işleci olan bir `HBRUSH` nesnesi.  
  
 Grafik nesneleri kullanma hakkında daha fazla bilgi için bkz: [grafik nesneleri](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek PROPDLG](../../visual-cpp-samples.md)   
 [CGdiObject sınıfı](../../mfc/reference/cgdiobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CBitmap sınıfı](../../mfc/reference/cbitmap-class.md)   
 [CDC Sınıfı](../../mfc/reference/cdc-class.md)
