---
title: CRgn sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRgn
- AFXWIN/CRgn
- AFXWIN/CRgn::CRgn
- AFXWIN/CRgn::CombineRgn
- AFXWIN/CRgn::CopyRgn
- AFXWIN/CRgn::CreateEllipticRgn
- AFXWIN/CRgn::CreateEllipticRgnIndirect
- AFXWIN/CRgn::CreateFromData
- AFXWIN/CRgn::CreateFromPath
- AFXWIN/CRgn::CreatePolygonRgn
- AFXWIN/CRgn::CreatePolyPolygonRgn
- AFXWIN/CRgn::CreateRectRgn
- AFXWIN/CRgn::CreateRectRgnIndirect
- AFXWIN/CRgn::CreateRoundRectRgn
- AFXWIN/CRgn::EqualRgn
- AFXWIN/CRgn::FromHandle
- AFXWIN/CRgn::GetRegionData
- AFXWIN/CRgn::GetRgnBox
- AFXWIN/CRgn::OffsetRgn
- AFXWIN/CRgn::PtInRegion
- AFXWIN/CRgn::RectInRegion
- AFXWIN/CRgn::SetRectRgn
dev_langs:
- C++
helpviewer_keywords:
- CRgn [MFC], CRgn
- CRgn [MFC], CombineRgn
- CRgn [MFC], CopyRgn
- CRgn [MFC], CreateEllipticRgn
- CRgn [MFC], CreateEllipticRgnIndirect
- CRgn [MFC], CreateFromData
- CRgn [MFC], CreateFromPath
- CRgn [MFC], CreatePolygonRgn
- CRgn [MFC], CreatePolyPolygonRgn
- CRgn [MFC], CreateRectRgn
- CRgn [MFC], CreateRectRgnIndirect
- CRgn [MFC], CreateRoundRectRgn
- CRgn [MFC], EqualRgn
- CRgn [MFC], FromHandle
- CRgn [MFC], GetRegionData
- CRgn [MFC], GetRgnBox
- CRgn [MFC], OffsetRgn
- CRgn [MFC], PtInRegion
- CRgn [MFC], RectInRegion
- CRgn [MFC], SetRectRgn
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b569efb201f95ade8987aaa89bb6cea1bc0c15c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="crgn-class"></a>CRgn sınıfı
Bir Windows grafik cihaz arabirimi (GDI) bölge yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRgn : public CGdiObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRgn::CRgn](#crgn)|Oluşturan bir `CRgn` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRgn::CombineRgn](#combinergn)|Ayarlar bir `CRgn` böylece iki belirtilen birleşimi eşdeğer nesne `CRgn` nesneleri.|  
|[CRgn::CopyRgn](#copyrgn)|Ayarlar bir `CRgn` belirtilen bir kopyası olan nesnesini `CRgn` nesne.|  
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Başlatır bir `CRgn` elips bölgesi olan nesne.|  
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Başlatır bir `CRgn` nesnesi tarafından tanımlanan bir elips bölge ile bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.|  
|[CRgn::CreateFromData](#createfromdata)|Bir bölge verilen bölge ve dönüştürme veri oluşturur.|  
|[CRgn::CreateFromPath](#createfrompath)|Bir bölge verilen cihaz bağlamına seçili yol oluşturur.|  
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Başlatır bir `CRgn` nesnesi bir Çokgen bölge ile. Sistem Çokgen otomatik olarak, gerekirse, bir satırı son köşe ilk çizerek kapatır.|  
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Başlatır bir `CRgn` nesnesi kapalı çokgenler bir dizi oluşan bir bölge ile. Çokgenler ayrık olabilir veya çakışıyor.|  
|[CRgn::CreateRectRgn](#createrectrgn)|Başlatır bir `CRgn` dikdörtgen bir bölgesi ile nesne.|  
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|Başlatır bir `CRgn` nesnesi tarafından tanımlanan dikdörtgen bir bölgesi olan bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.|  
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Başlatır bir `CRgn` yuvarlak köşeli dikdörtgen bir bölgesi nesnesiyle.|  
|[CRgn::EqualRgn](#equalrgn)|İki denetler `CRgn` nesneleri eşdeğer olup olmadıklarını belirlemek için.|  
|[CRgn::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CRgn` nesnesi tanıtıcı Windows bölgesine verildiğinde.|  
|[CRgn::GetRegionData](#getregiondata)|Belirtilen arabellek verilen bölge açıklayan verileri ile doldurur.|  
|[CRgn::GetRgnBox](#getrgnbox)|Sınırlayıcı dikdörtgenini koordinatlarını alır bir `CRgn` nesnesi.|  
|[CRgn::OffsetRgn](#offsetrgn)|Taşır bir `CRgn` nesnesi tarafından belirtilen uzaklık.|  
|[CRgn::PtInRegion](#ptinregion)|Belirli bir noktaya bölgede olup olmadığını belirler.|  
|[CRgn::RectInRegion](#rectinregion)|Belirtilen bir dikdörtgen herhangi bir kısmını bölge sınırları içinde olup olmadığını belirler.|  
|[CRgn::SetRectRgn](#setrectrgn)|Ayarlar `CRgn` belirtilen dikdörtgen bölge nesnesine.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRgn::operator HRGN](#operator_hrgn)|İçinde yer alan Windows işleyici döner `CRgn` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir bölge içinde bir pencere elips veya Çokgen bir alandır. Bölgeleri kullanmak için sınıf üyesi işlevleri kullanın `CRgn` sınıfı bir üyesi olarak tanımlanan kırpma işlevlerle `CDC`.  
  
 Üye işlevlerini `CRgn` oluşturmak, alter ve için bunlar denir bölge nesne hakkında bilgi alın.  
  
 Kullanma hakkında daha fazla bilgi için `CRgn`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="combinergn"></a>  CRgn::CombineRgn  
 Var olan iki bölgede birleştirerek yeni GDI bölgesi oluşturur.  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRgn1`  
 Varolan bir bölge tanımlar.  
  
 `pRgn2`  
 Varolan bir bölge tanımlar.  
  
 `nCombineMode`  
 İki kaynak bölgelerine birleştirilirken gerçekleştirilecek işlemi belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **RGN_AND** çakışan alanlarının her iki bölgeler (kesişim) kullanır.  
  
- **RGN_COPY** bölge 1 bir kopyasını oluşturur (tarafından tanımlanan `pRgn1`).  
  
- **RGN_DIFF** bölge 1 alanlarının oluşan bir bölge oluşturur (tarafından tanımlanan `pRgn1`) 2 bölgesinin bir parçası olmayan (tarafından tanımlanan `pRgn2`).  
  
- **RGN_OR** tamamıyla (Birliği) hem bölgelerde birleştirir.  
  
- **RGN_XOR** hem bölgeler birleştirir ancak çakışan alanlarını kaldırır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuçta elde edilen bölge türünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **COMPLEXREGION** yeni bölge sahip çakışan sınırlar.  
  
- **HATA** oluşturulan yeni bölge.  
  
- **NULLREGION** yeni bölge boştur.  
  
- **SIMPLEREGION** yeni bölge sahip çakışan kenarlık yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölgeler birleştirilir belirtildiği gibi `nCombineMode`.  
  
 Belirtilen iki bölgeler birleştirilir ve sonuçta elde edilen Bölge tanıtıcısı depolanan `CRgn` nesnesi. Bu nedenle, her bölge depolanan `CRgn` nesne birleşik bölgeye göre değiştirilir.  
  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Kullanım [CopyRgn](#copyrgn) yalnızca tek bir bölge başka bir bölgeye kopyalamak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]  
  
##  <a name="copyrgn"></a>  CRgn::CopyRgn  
 Tarafından tanımlanan bir bölgeyi kopyalar `pRgnSrc` içine `CRgn` nesnesi.  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRgnSrc`  
 Varolan bir bölge tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuçta elde edilen bölge türünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **COMPLEXREGION** yeni bölge sahip çakışan sınırlar.  
  
- **HATA** oluşturulan yeni bölge.  
  
- **NULLREGION** yeni bölge boştur.  
  
- **SIMPLEREGION** yeni bölge sahip çakışan kenarlık yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bölge önceden depolanan bölgesi değiştirir `CRgn` nesnesi. Bu işlev, özel bir durumdur [CombineRgn](#combinergn) üye işlevi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRgn::CreateEllipticRgn](#createellipticrgn).  
  
##  <a name="createellipticrgn"></a>  CRgn::CreateEllipticRgn  
 Elips bölgesi oluşturur.  
  
```  
BOOL CreateEllipticRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>Parametreler  
 `x1`  
 Mantıksal x koordinatını elipsin sınırlayıcı dikdörtgenini sol üst köşesindeki belirtir.  
  
 `y1`  
 Sınırlayıcı dikdörtgenini elipsin sol üst köşesinin mantıksal y koordinatını belirtir.  
  
 `x2`  
 Mantıksal x koordinatını elipsin sınırlayıcı dikdörtgenini sağ alt köşesindeki belirtir.  
  
 `y2`  
 Mantıksal y koordinatını elipsin sınırlayıcı dikdörtgenini sağ alt köşesindeki belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölge tarafından belirtilen sınırlayıcı dikdörtgenini tarafından tanımlanan `x1`, `y1`, `x2`, ve `y2`. Bölge depolanan `CRgn` nesnesi.  
  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Olduğunda tamamlandı ile oluşturulan bir bölge kullanarak `CreateEllipticRgn` işlevi, bir uygulama kullanın ve cihaz bağlamı çıkışı bölgesini seçmelisiniz `DeleteObject` kaldırmaya işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]  
  
##  <a name="createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect  
 Elips bölgesi oluşturur.  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir `RECT` yapısı veya `CRect` elipsin sınırlayıcı dikdörtgenini sol üst ve sağ alt köşe mantıksal koordinatlarını içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölge yapısı veya gösterdiği nesne tarafından tanımlanan `lpRect` ve depolanan `CRgn` nesnesi.  
  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Olduğunda tamamlandı ile oluşturulan bir bölge kullanarak `CreateEllipticRgnIndirect` işlevi, bir uygulama kullanın ve cihaz bağlamı çıkışı bölgesini seçmelisiniz `DeleteObject` kaldırmaya işlevi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRgn::CreateRectRgnIndirect](#createrectrgnindirect).  
  
##  <a name="createfromdata"></a>  CRgn::CreateFromData  
 Bir bölge verilen bölge ve dönüştürme veri oluşturur.  
  
```  
BOOL CreateFromData(
    const XFORM* lpXForm,  
    int nCount,  
    const RGNDATA* pRgnData);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpXForm*  
 İşaret eden bir [XFORM](../../mfc/reference/xform-structure.md) bölgesi üzerinde gerçekleştirilecek dönüşümünü tanımlar veri yapısı. Bu işaretçi ise **NULL**, kimlik dönüştürme kullanılır.  
  
 `nCount`  
 Gösterdiği bayt sayısını belirtir `pRgnData`.  
  
 `pRgnData`  
 İşaret eden bir [RGNDATA](../../mfc/reference/rgndata-structure.md) bölge verileri içeren veri yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uygulama için bir bölge çağırarak verileri `CRgn::GetRegionData` işlevi.  
  
##  <a name="createfrompath"></a>  CRgn::CreateFromPath  
 Bir bölge verilen cihaz bağlamına seçili yol oluşturur.  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Kapalı bir yolu içeren bir cihaz bağlamı tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından tanımlanan cihaz bağlamı `pDC` parametresi kapalı bir yolu içermesi gerekir. Sonra `CreateFromPath` bir bölge Windows yola bir cihaz bağlamı kapalı yolundan atar.  
  
##  <a name="createpolygonrgn"></a>  CRgn::CreatePolygonRgn  
 Çokgen bölge oluşturur.  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpPoints`  
 Noktaları için bir dizi **noktası** yapıları veya bir dizi `CPoint` nesneleri. Her yapısı çokgenin bir köşesinin y koordinatını ve x koordinatını belirtir. **Noktası** yapısı aşağıdaki biçime sahiptir:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `nCount`  
 Sayısını belirtir **noktası** yapıları veya `CPoint` tarafından dizideki nesneleri işaret için `lpPoints`.  
  
 `nMode`  
 Bölge için doldurma modunu belirtir. Bu parametre ya da olabilir **ALTERNATİF** veya **sarma**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sistem Çokgen otomatik olarak, gerekirse, bir satırı son köşe ilk çizerek kapatır. Sonuçta elde edilen bölge depolanan `CRgn` nesnesi.  
  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Çokgen doldurma modu olduğunda **ALTERNATİF**, her tarama satırındaki tek sayılı ve sayılı Çokgen kenarı arasındaki alan sistem doldurur. Diğer bir deyişle, sistem alanın ilk ve ikinci tarafı arasında üçüncü ve dördüncü yan vb. arasında doldurur.  
  
 Çokgen doldurma modu olduğunda **sarma**, içinde bir şekil çizilen bir alanı dolduracak şekilde belirlemek için yönü sistemi kullanır. Her bir Çokgen satır kesimdeki bir saat yönünde veya saatin aksi yönünde çizilir. Kapalı bir alandan bir şekil dıştan çizilmiş hayali bir çizgi bir saat yönünde çizgi kesimi geçirir her bir sayısı artırılır. Satır saatin aksi yönünde satır kesimi geçtiğinde, sayısı azaltılır. Satır şekil dışına ulaştığında sayısı sıfır değilse alan doldurulur.  
  
 Bir uygulama bittiği ile oluşturulan bir bölge kullanarak `CreatePolygonRgn` işlevi, bunu kullanın ve cihaz bağlamı çıkışı bölgesini seçmelisiniz `DeleteObject` kaldırmaya işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]  
  
##  <a name="createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn  
 Kapalı çokgenler bir dizi oluşan bir bölge oluşturur.  
  
```  
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount,  
    int nPolyFillMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpPoints`  
 Noktaları için bir dizi **noktası** yapıları veya bir dizi `CPoint` çokgenler köşeleri tanımlar nesneleri. Sistem otomatik olarak onları kapatmaz çünkü her bir Çokgen açıkça kapatılması gerekir. Çokgenler art arda belirtilir. **Noktası** yapısı aşağıdaki biçime sahiptir:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `lpPolyCounts`  
 Tamsayıların noktaları bir dizi. Tepe sayısı ilk Çokgendeki ilk tamsayı belirtir `lpPoints` dizi, ikinci tamsayı ikinci Çokgen ve benzeri köşeleri sayısını belirtir.  
  
 `nCount`  
 Tamsayılar toplam sayısını belirtir `lpPolyCounts` dizi.  
  
 `nPolyFillMode`  
 Çokgen doldurma modunu belirtir. Bu değer ya da olabilir **ALTERNATİF** veya **sarma**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuçta elde edilen bölge depolanan `CRgn` nesnesi.  
  
 Çokgenler ayrık olabilir veya çakışıyor.  
  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Çokgen doldurma modu olduğunda **ALTERNATİF**, her tarama satırındaki tek sayılı ve sayılı Çokgen kenarı arasındaki alan sistem doldurur. Diğer bir deyişle, sistem alanın ilk ve ikinci tarafı arasında üçüncü ve dördüncü yan vb. arasında doldurur.  
  
 Çokgen doldurma modu olduğunda **sarma**, içinde bir şekil çizilen bir alanı dolduracak şekilde belirlemek için yönü sistemi kullanır. Her bir Çokgen satır kesimdeki bir saat yönünde veya saatin aksi yönünde çizilir. Kapalı bir alandan bir şekil dıştan çizilmiş hayali bir çizgi bir saat yönünde çizgi kesimi geçirir her bir sayısı artırılır. Satır saatin aksi yönünde satır kesimi geçtiğinde, sayısı azaltılır. Satır şekil dışına ulaştığında sayısı sıfır değilse alan doldurulur.  
  
 Bir uygulama bittiği ile oluşturulan bir bölge kullanarak `CreatePolyPolygonRgn` işlevi, bunu kullanın ve cihaz bağlamı çıkışı bölgesini seçmelisiniz [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) kaldırmak için üye işlevi.  
  
##  <a name="createrectrgn"></a>  CRgn::CreateRectRgn  
 Depolanan dikdörtgen bir bölgesi oluşturur `CRgn` nesnesi.  
  
```  
BOOL CreateRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>Parametreler  
 `x1`  
 Mantıksal x koordinatını bölge sol üst köşesindeki belirtir.  
  
 `y1`  
 Bölge sol üst köşesinin mantıksal y koordinatını belirtir.  
  
 `x2`  
 Mantıksal x koordinatını alanının sağ alt köşedeki belirtir.  
  
 `y2`  
 Mantıksal y koordinatını alanının sağ alt köşedeki belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Olduğunda tamamlandı tarafından oluşturulan bir bölge kullanarak `CreateRectRgn`, bir uygulama kullanması gereken [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) bölgeyi kaldırmak için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]  
  
 Ek bir örnek için bkz: [CRgn::CombineRgn](#combinergn).  
  
##  <a name="createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect  
 Depolanan dikdörtgen bir bölgesi oluşturur `CRgn` nesnesi.  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir `RECT` yapısı veya `CRect` bölgenin sol üst ve sağ alt köşe mantıksal koordinatlarını içeren nesne. `RECT` Yapısı aşağıdaki biçime sahiptir:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Olduğunda tamamlandı tarafından oluşturulan bir bölge kullanarak `CreateRectRgnIndirect`, bir uygulama kullanması gereken [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) bölgeyi kaldırmak için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]  
  
##  <a name="createroundrectrgn"></a>  CRgn::CreateRoundRectRgn  
 Depolanan yuvarlak köşeli dikdörtgen bir bölgesi oluşturur `CRgn` nesnesi.  
  
```  
BOOL CreateRoundRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3);
```  
  
### <a name="parameters"></a>Parametreler  
 `x1`  
 Mantıksal x koordinatını bölge sol üst köşesindeki belirtir.  
  
 `y1`  
 Bölge sol üst köşesinin mantıksal y koordinatını belirtir.  
  
 `x2`  
 Mantıksal x koordinatını alanının sağ alt köşedeki belirtir.  
  
 `y2`  
 Mantıksal y koordinatını alanının sağ alt köşedeki belirtir.  
  
 *x3*  
 Yuvarlak köşeleri oluşturmak için kullanılan elips genişliğini belirtir.  
  
 `y3`  
 Yuvarlak köşeleri oluşturmak için kullanılan elips yüksekliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölgenin boyutunu 32.767 tarafından 32.767 mantıksal birimler veya bellek 64 K ile sınırlı, hangisi daha küçük.  
  
 Bir uygulama bittiği ile oluşturulan bir bölge kullanarak `CreateRoundRectRgn` işlevi, bunu kullanın ve cihaz bağlamı çıkışı bölgesini seçmelisiniz [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) kaldırmak için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]  
  
##  <a name="crgn"></a>  CRgn::CRgn  
 Oluşturan bir `CRgn` nesnesi.  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hObject` Nesnesi bir veya daha fazla diğer başlatılana dek veri üyesi geçerli bir Windows GDI bölge içermiyor `CRgn` üye işlevleri.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRgn::CreateRoundRectRgn](#createroundrectrgn).  
  
##  <a name="equalrgn"></a>  CRgn::EqualRgn  
 Verilen bölge içinde depolanan bölgeye eşdeğer olup olmadığını belirler `CRgn` nesnesi.  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pRgn`  
 Bir bölge tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki bölgede eşdeğer olup olmadığını sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]  
  
##  <a name="fromhandle"></a>  CRgn::FromHandle  
 Bir işaretçi döndüren bir `CRgn` nesnesi tanıtıcı Windows bölgesine verildiğinde.  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>Parametreler  
 `hRgn`  
 Bir Windows bölge için bir tanıtıcı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CRgn` nesnesi. İşlev başarılı olmadıysa dönüş değeri olan **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CRgn` nesne zaten iliştirilmemiş tanıtıcıyı, geçici bir `CRgn` nesnesi oluşturulur ve bağlı. Bu geçici `CRgn` nesnesi, hangi tüm geçici grafiği zaman durdurulacağını sonraki açışınızda uygulama boşta kalma süresi, olay döngüde olana kadar nesneler silinir yalnızca geçerli. Bu bildiren başka bir şekilde geçici nesne yalnızca bir pencere ileti işleme sırasında geçerli olmasıdır.  
  
##  <a name="getregiondata"></a>  CRgn::GetRegionData  
 Belirtilen arabellek bölge açıklayan verileri ile doldurur.  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRgnData`  
 İşaret eden bir [RGNDATA](../../mfc/reference/rgndata-structure.md) bilgileri aldığı veri yapısı. Bu parametre ise **NULL**, dönüş değeri bölge verileri için gereken bayt sayısını içerir.  
  
 `nCount`  
 Bayt cinsinden boyutu belirtir `lpRgnData` arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa ve `nCount` yeterli numarasını belirtir, dönüş değeri her zaman bayttır `nCount`. İşlev başarısız olursa veya `nCount` daha az belirtir yeterli bayt sayısından dönüş değeri 0 (hata)'dır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu veriler bölgesini olun dikdörtgenler boyutları içerir. Bu işlev ile birlikte kullanılan `CRgn::CreateFromData` işlevi.  
  
##  <a name="getrgnbox"></a>  CRgn::GetRgnBox  
 Sınırlayıcı dikdörtgenini koordinatlarını alır `CRgn` nesnesi.  
  
```  
int GetRgnBox(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir `RECT` yapısı veya `CRect` sınırlayıcı dikdörtgenini koordinatlarını almak için nesne. `RECT` Yapısı aşağıdaki biçime sahiptir:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölgenin türünü belirtir. Aşağıdaki değerlerden herhangi birini olabilir:  
  
- **COMPLEXREGION** bölge sahip çakışan sınırlar.  
  
- **NULLREGION** bölgedir boş.  
  
- **HATA** `CRgn` nesne geçerli bir bölge belirtmiyor.  
  
- **SIMPLEREGION** bölge sahip çakışan kenarlık yok.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRgn::CreatePolygonRgn](#createpolygonrgn).  
  
##  <a name="offsetrgn"></a>  CRgn::OffsetRgn  
 Depolanan bölge taşır `CRgn` nesnesi tarafından belirtilen uzaklık.  
  
```  
int OffsetRgn(
    int x,  
    int y);  
  
int OffsetRgn(POINT point);
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Sol taşımak için veya sağa birim sayısını belirtir.  
  
 *Y*  
 Yukarı veya aşağı taşımak için kullanılacak birim sayısını belirtir.  
  
 `point`  
 X koordinatını `point` sol taşımak için veya sağa birim sayısını belirtir. Y koordinatını `point` yukarı veya aşağı taşımak için kullanılacak birim sayısını belirtir. `point` Parametresi olabilir ya da bir **noktası** yapısı veya `CPoint` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bölgenin türü. Aşağıdaki değerlerden biri olabilir:  
  
- **COMPLEXREGION** bölge sahip çakışan sınırlar.  
  
- **HATA** Bölge tanıtıcısı geçerli değil.  
  
- **NULLREGION** bölgedir boş.  
  
- **SIMPLEREGION** bölge sahip çakışan kenarlık yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölge işlevi taşır *x* birim x ekseni boyunca ve *y* birim y ekseni boyunca.  
  
 Bir bölge koordinat değerlerini 32.767 ve sıfırdan büyük veya eşit -32.768 eşit veya daha az olmalıdır. *x* ve *y* parametreleri gerekir dikkatle seçilebilir geçersiz bölge koordinatları önlemek için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRgn::CreateEllipticRgn](#createellipticrgn).  
  
##  <a name="operator_hrgn"></a>  CRgn::operator HRGN  
 Ekli Windows GDI işleyicisini almak için bu işleci kullanın `CRgn` nesnesi.  
  
```  
operator HRGN() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CRgn` nesne; Aksi halde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç doğrudan kullanımını destekleyen bir atama işleci olan bir **HRGN** nesnesi.  
  
 Grafik nesneleri kullanma hakkında daha fazla bilgi için bkz: [grafik nesneleri](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows SDK.  
  
##  <a name="ptinregion"></a>  CRgn::PtInRegion  
 Denetler olup olmadığını tarafından verilen nokta *x* ve *y* depolanan bölge içinde `CRgn` nesnesi.  
  
```  
BOOL PtInRegion(
    int x,  
    int y) const;  
  
BOOL PtInRegion(POINT point) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Mantıksal x koordinatını sınamak için noktasının belirtir.  
  
 *Y*  
 Test etmek için noktasının mantıksal y koordinatını belirtir.  
  
 `point`  
 X - ve y koordinatlarını `point` x ve y-koordinatları değerini test için noktasının belirtin. `point` Parametresi olabilir ya da bir **noktası** yapısı veya `CPoint` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Noktası bölgede ise sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="rectinregion"></a>  CRgn::RectInRegion  
 Dikdörtgen herhangi bir kısmını tarafından belirtilen olup olmadığını belirler `lpRect` depolanan bölge sınırlarının içinde `CRgn` nesnesi.  
  
```  
BOOL RectInRegion(LPCRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir `RECT` yapısı veya `CRect` nesnesi. `RECT` Yapısı aşağıdaki biçime sahiptir:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dikdörtgenin herhangi bir kısmını bölge sınırlar içinde yer alıyorsa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="setrectrgn"></a>  CRgn::SetRectRgn  
 Dikdörtgen bir bölgesi oluşturur.  
  
```  
void SetRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
void SetRectRgn(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `x1`  
 Dikdörtgen bölgesini sol üst köşesindeki x koordinatını belirtir.  
  
 `y1`  
 Dikdörtgen bölgesini sol üst köşesindeki y koordinatını belirtir.  
  
 `x2`  
 Dikdörtgen bölgesini sağ alt köşesindeki x koordinatını belirtir.  
  
 `y2`  
 Dikdörtgen bölgesini sağ alt köşesindeki y koordinatını belirtir.  
  
 `lpRect`  
 Dikdörtgen bölgesini belirtir. İçin bir işaretçi olabilir bir `RECT` yapısı veya `CRect` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı [CreateRectRgn](#createrectrgn), ancak bunu diğer ek bellek yerel Windows uygulama yığınından bırakmaz. Bunun yerine, bölge içinde depolanan için ayrılan alanı kullanır `CRgn` nesnesi. Bunun anlamı `CRgn` nesne gerekir zaten başlatılmış çağırmadan önce geçerli bir Windows bölgesiyle `SetRectRgn`. Tarafından verilen noktaları `x1`, `y1`, `x2`, ve `y2` ayrılan alan minimum boyutu belirtin.  
  
 Yerine bu işlevi kullanın `CreateRectRgn` yerel bellek yöneticisi çağrıları önlemek için üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



