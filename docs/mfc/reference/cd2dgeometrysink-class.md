---
title: "CD2DGeometrySink sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
dev_langs: C++
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 89286aaccd2c59efb2bac14978a2d8838af7a4e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink sınıfı
ID2D1GeometrySink için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DGeometrySink;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry nesnesinden CD2DGeometrySink nesnesi oluşturur.|  
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Yok Edicisi. D2D geometri havuz nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](#addarc)|Tek bir yay yolu geometriye ekler|  
|[CD2DGeometrySink::AddBezier](#addbezier)|Güncel nokta ve belirtilen bitiş noktası arasında küp Bezier eğrisi oluşturur.|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Küp Bezier eğrileri dizisi oluşturur ve bunları geometri havuz ekler.|  
|[CD2DGeometrySink::AddLine](#addline)|Güncel nokta ve belirtilen bitiş noktası arasında satır bir segment oluşturur ve geometri havuz ekler.|  
|[CD2DGeometrySink::AddLines](#addlines)|Bir dizi satır belirtilen noktalarını kullanarak oluşturur ve bunları geometri havuz ekler.|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Güncel nokta ve belirtilen bitiş noktası arasında ikinci derece Bezier eğrisi oluşturur.|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Tek bir çağrı bir dizi olarak bir dizi ikinci derece Bezier kesimleri ekler.|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Yeni bir şekil, belirli bir noktada başlatır.|  
|[CD2DGeometrySink::Close](#close)|Geometri havuz kapatır|  
|[CD2DGeometrySink::EndFigure](#endfigure)|Geçerli şekil sonlandırır; İsteğe bağlı olarak kapatılır.|  
|[CD2DGeometrySink::get](#get)|Döndürür ID2D1GeometrySink arabirimi|  
|[CD2DGeometrySink::IsValid](#isvalid)|Geometri havuz geçerlilik denetler|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|İçinde bu geometri havuzu tarafından açıklanan geometri noktaları olan noktaları dışında olan ve belirlemek için kullanılan yöntemi belirtir.|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Geometri havuzuna eklenen yeni kesimleri uygulanacak vuruş ve birleştirme seçeneklerini belirtir.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|Döndürür ID2D1GeometrySink arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometrySink::m_pSink](#m_psink)|Bir ID2D1GeometrySink gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CD2DGeometrySink`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink:: ~ CD2DGeometrySink  
 Yok Edicisi. D2D geometri havuz nesnesi yok çağrılır.  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="addarc"></a>CD2DGeometrySink::AddArc  
 Tek bir yay yolu geometriye ekler  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>Parametreler  
 `arc`  
 Yay segment şekle eklemek için  
  
##  <a name="addbezier"></a>CD2DGeometrySink::AddBezier  
 Güncel nokta ve belirtilen bitiş noktası arasında küp Bezier eğrisi oluşturur.  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Parametreler  
 `bezier`  
 Denetim noktalarını ve uç noktası eklemek için Bezier eğrisinin açıklar yapısı.  
  
##  <a name="addbeziers"></a>CD2DGeometrySink::AddBeziers  
 Küp Bezier eğrileri dizisi oluşturur ve bunları geometri havuz ekler.  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Parametreler  
 `beziers`  
 Bezier kesimleri oluşturmak için Bezier eğrileri açıklayan dizisi. Bir eğri dizideki ilk Bezier kesiminin uç noktasına geometri havuz ait geçerli noktası (bitiş noktası çizilmiş son kesimi veya BeginFigure tarafından belirtilen konumda) çizilir. dizi ek Bezier kesimleri içeriyorsa, her alt Bezier segment önceki Bezier kesiminin uç noktası, başlangıç noktası olarak kullanır.  
  
##  <a name="addline"></a>CD2DGeometrySink::AddLine  
 Güncel nokta ve belirtilen bitiş noktası arasında satır bir segment oluşturur ve geometri havuz ekler.  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parametreler  
 `point`  
 Çizgiyi çizmek için bitiş noktası.  
  
##  <a name="addlines"></a>CD2DGeometrySink::AddLines  
 Bir dizi satır belirtilen noktalarını kullanarak oluşturur ve bunları geometri havuz ekler.  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>Parametreler  
 `points`  
 Satırlar çizme açıklayan bir veya daha fazla noktalar dizisi. Bir satır, geometri havuz ait geçerli noktası (bitiş noktası çizilmiş son kesimi veya BeginFigure tarafından belirtilen konumda), dizinin ilk noktanın kadar çizilir. dizi ek noktaları içeriyorsa, bir çizgi dizi ikinci noktaya üçüncü noktası vb. için ikinci noktasından ilk noktasından çizilir. Uç noktaları çizmek için satırlarının bir dizi bir dizi.  
  
##  <a name="addquadraticbezier"></a>CD2DGeometrySink::AddQuadraticBezier  
 Güncel nokta ve belirtilen bitiş noktası arasında ikinci derece Bezier eğrisi oluşturur.  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Parametreler  
 `bezier`  
 Denetim noktası ve bitiş noktası eklemek için ikinci derece Bezier eğrisinin açıklar yapısı.  
  
##  <a name="addquadraticbeziers"></a>CD2DGeometrySink::AddQuadraticBeziers  
 Tek bir çağrı bir dizi olarak bir dizi ikinci derece Bezier kesimleri ekler.  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Parametreler  
 `beziers`  
 İkinci derece Bezier kesimleri bir dizi bir dizi.  
  
##  <a name="beginfigure"></a>CD2DGeometrySink::BeginFigure  
 Yeni bir şekil, belirli bir noktada başlatır.  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>Parametreler  
 `startPoint`  
 Yeni şekil başlanan noktası.  
  
 `figureBegin`  
 Yeni şekil boş veya dolu olması gerekir.  
  
##  <a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink  
 CD2DPathGeometry nesnesinden CD2DGeometrySink nesnesi oluşturur.  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>Parametreler  
 `pathGeometry`  
 Varolan bir CD2DPathGeometry nesne.  
  
##  <a name="close"></a>CD2DGeometrySink::Close  
 Geometri havuz kapatır  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde FALSE.  
  
##  <a name="endfigure"></a>CD2DGeometrySink::EndFigure  
 Geçerli şekil sonlandırır; İsteğe bağlı olarak kapatılır.  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `figureEnd`  
 Geçerli şekil kapalı olup olmadığını belirten bir değer. Şekil kapattıysanız, bir çizgi geçerli noktası BeginFigure tarafından belirtilen başlangıç noktası arasındaki çizilir.  
  
##  <a name="get"></a>CD2DGeometrySink::get  
 Döndürür ID2D1GeometrySink arabirimi  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1GeometrySink arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="isvalid"></a>CD2DGeometrySink::IsValid  
 Geometri havuz geçerlilik denetler  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geometri havuz geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_psink"></a>CD2DGeometrySink::m_pSink  
 Bir ID2D1GeometrySink gösteren bir işaretçi.  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::operator ID2D1GeometrySink *  
 Döndürür ID2D1GeometrySink arabirimi  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1GeometrySink arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="setfillmode"></a>CD2DGeometrySink::SetFillMode  
 İçinde bu geometri havuzu tarafından açıklanan geometri noktaları olan noktaları dışında olan ve belirlemek için kullanılan yöntemi belirtir.  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `fillMode`  
 Verilen bir noktaya geometrinin parçası olup olmadığını belirlemek için kullanılan yöntem.  
  
##  <a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags  
 Geometri havuzuna eklenen yeni kesimleri uygulanacak vuruş ve birleştirme seçeneklerini belirtir.  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `vertexFlags`  
 Geometri havuzuna eklenen yeni kesimleri uygulanacak vuruş ve Birleştirme Seçenekleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
