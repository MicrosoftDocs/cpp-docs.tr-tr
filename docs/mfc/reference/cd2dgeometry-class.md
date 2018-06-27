---
title: CD2DGeometry sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51e3c24464ff74ab262cd241dcdce68037d530f9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955108"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry sınıfı
ID2D1Geometry için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|CD2DGeometry nesnesi oluşturur.|  
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Yok Edicisi. D2D geometri nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometry::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Belirtilen geometri ile bu geometri birleştirir ve sonucu bir ID2D1SimplifiedGeometrySink depolar.|  
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Bu geometri ve belirtilen geometri kesişimi açıklar. Karşılaştırma belirtilen düzleştirme dayanıklılık kullanılarak gerçekleştirilir.|  
|[CD2DGeometry::ComputeArea](#computearea)|Alan geometrinin edildikten sonra hesaplar tarafından belirtilen matris dönüştürülen ve belirtilen tolerans kullanarak düzleştirilmiş.|  
|[CD2DGeometry::ComputeLength](#computelength)|Her segment gibi davranarak bir satıra unrolled geometri uzunluğunu hesaplar.|  
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Edildikten sonra geometri boyunca belirtilen uzaklıkta noktası ve tanjantını vektör hesaplar tarafından belirtilen matris dönüştürülen ve belirtilen tolerans kullanarak düzleştirilmiş.|  
|[CD2DGeometry::Destroy](#destroy)|CD2DGeometry nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DGeometry::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Geometri tarafından doldurulmuş alanı belirtilen düzleştirme tolerans verilen belirtilen nokta içerecektir olup olmadığını gösterir.|  
|[CD2DGeometry::get](#get)|Döndürür ID2D1Geometry arabirimi|  
|[CD2DGeometry::GetBounds](#getbounds)||  
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Stil ve belirtilen vuruşun genişliğini devam ve tarafından belirtilen matris dönüştürülmüş sonra geometri sınırları alır.|  
|[CD2DGeometry::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DGeometry::Outline](#outline)|Anahat geometrinin hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink yazar.|  
|[CD2DGeometry::Simplify](#simplify)|Yalnızca çizgileri ve (isteğe bağlı) küp Bezier eğrileri içeren ve sonucu bir ID2D1SimplifiedGeometrySink Yazar geometri basitleştirilmiş bir sürümünü oluşturur.|  
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Geometri 's vuruş verilen belirtilen vuruş kalınlığı, stil ve dönüştürme belirtilen noktası içerip içermediğini belirler.|  
|[CD2DGeometry::Tessellate](#tessellate)|Belirtilen matrisi kullanarak dönüştürüldükten sonra geometri kapsar ve belirtilen tolerans kullanarak düzleştirilmiş sargılı yönünde üçgenler kümesi oluşturur.|  
|[CD2DGeometry::Widen](#widen)|Geometri tarafından belirtilen vuruşun widens ve edildikten sonra sonucu bir ID2D1SimplifiedGeometrySink yazar tarafından belirtilen matris dönüştürülen ve belirtilen tolerans kullanarak düzleştirilmiş.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|Döndürür ID2D1Geometry arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|Bir ID2D1Geometry gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DGeometry`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometry"></a>  CD2DGeometry:: ~ CD2DGeometry  
 Yok Edicisi. D2D geometri nesnesi yok çağrılır.  
  
```  
virtual ~CD2DGeometry();
```  
  
##  <a name="attach"></a>  CD2DGeometry::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1Geometry* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 *pResource*  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry  
 CD2DGeometry nesnesi oluşturur.  
  
```  
CD2DGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentTarget*  
 İşleme hedefi için bir işaretçi.  
  
 *bAutoDestroy*  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry  
 Belirtilen geometri ile bu geometri birleştirir ve sonucu bir ID2D1SimplifiedGeometrySink depolar.  
  
```  
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,  
    D2D1_COMBINE_MODE combineMode,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *inputGeometry*  
 Bu örnekle birleştirmek için geometri.  
  
 *combineMode*  
 Birleştirme işlemi gerçekleştirmek için türü.  
  
 *inputGeometryTransform*  
 Birleştirme önce inputGeometry uygulanacak dönüşüm.  
  
 *geometrySink*  
 Birleştirme işleminin sonucu.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık olarak geometri noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry  
 Bu geometri ve belirtilen geometri kesişimi açıklar. Karşılaştırma belirtilen düzleştirme dayanıklılık kullanılarak gerçekleştirilir.  
  
```  
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *inputGeometry*  
 Test etmek için geometri.  
  
 *inputGeometryTransform*  
 İnputGeometry için uygulanacak dönüşüm.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık olarak geometri noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="computearea"></a>  CD2DGeometry::ComputeArea  
 Alan geometrinin edildikten sonra hesaplar tarafından belirtilen matris dönüştürülen ve belirtilen tolerans kullanarak düzleştirilmiş.  
  
```  
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& area,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *worldTransform*  
 Kendi alanı computing önce bu geometriye uygulanacak dönüşüm.  
  
 *alan*  
 Bu yöntem döndürüldüğünde, bu geometri dönüştürülmüş, düzleştirilmiş sürümü alanı için bir işaretçi içeriyor. Bu parametre için depolama ayırmanız gerekir.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık geometrinin noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="computelength"></a>  CD2DGeometry::ComputeLength  
 Her segment gibi davranarak bir satıra unrolled geometri uzunluğunu hesaplar.  
  
```  
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& length,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *worldTransform*  
 Uzunluğu hesaplanması önce geometriye uygulanacak dönüşüm.  
  
 *uzunluğu*  
 Bu yöntem döndürüldüğünde, geometri uzunluğu için bir işaretçi içeriyor. Kapalı geometri için örtük kapanış segment uzunluğu içerir. Bu parametre için depolama ayırmanız gerekir.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık geometrinin noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength  
 Edildikten sonra geometri boyunca belirtilen uzaklıkta noktası ve tanjantını vektör hesaplar tarafından belirtilen matris dönüştürülen ve belirtilen tolerans kullanarak düzleştirilmiş.  
  
```  
BOOL ComputePointAtLength(
    FLOAT length,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DPointF& point,  
    CD2DPointF& unitTangentVector,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *uzunluğu*  
 Geometri noktasının ve bulmak için tanjantını boyunca uzaklığı. Bu uzaklık daha az sonra 0 ise, bu yöntem geometri ilk noktanın hesaplar. Bu uzaklık geometri uzunluğundan daha büyük ise, bu yöntem geometri son noktanın hesaplar.  
  
 *worldTransform*  
 Belirtilen noktası ve tanjantını hesaplanmadan önce geometriye uygulanacak dönüşüm.  
  
 *Noktası*  
 Geometri boyunca belirtilen uzaklıkta konumu. Geometri boşsa, bu nokta NaN x ve y içeren değerleri.  
  
 *unitTangentVector*  
 Bu yöntem döndürüldüğünde, geometri boyunca belirtilen uzaklıkta Eğim vektör gösteren bir işaretçi içeriyor. Geometri boşsa, bu vektörü NaN x ve y içeren değerleri. Bu parametre için depolama ayırmanız gerekir.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık geometrinin noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="destroy"></a>  CD2DGeometry::Destroy  
 CD2DGeometry nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DGeometry::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1Geometry* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint  
 Geometri tarafından doldurulmuş alanı belirtilen düzleştirme tolerans verilen belirtilen nokta içerecektir olup olmadığını gösterir.  
  
```  
BOOL FillContainsPoint(
    CD2DPointF point,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *Noktası*  
 Test noktası.  
  
 *worldTransform*  
 Kapsama için test önce geometri uygulanacak dönüşüm.  
  
 *İçerir*  
 Bu yöntem döndürüldüğünde, geometri tarafından doldurulmuş alan noktası içeriyorsa TRUE bir Boole değeri içeriyor; Aksi takdirde FALSE. Bu parametre için depolama ayırmanız gerekir.  
  
 *flatteningTolerance*  
 Hangi sayısal doğruluğu yolu kesişim ve kesin geometrik yolunu hesaplanır. Tolerans değerinden tarafından dolgu eksik noktaları hala içinde olarak kabul edilir. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="get"></a>  CD2DGeometry::get  
 Döndürür ID2D1Geometry arabirimi  
  
```  
ID2D1Geometry* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Geometry arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getbounds"></a>  CD2DGeometry::GetBounds  
  
```   
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,  
CD2DRectF& bounds) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 *worldTransform*  
 *sınırları*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds  
 Stil ve belirtilen vuruşun genişliğini devam ve tarafından belirtilen matris dönüştürülmüş sonra geometri sınırları alır.  
  
```  
BOOL GetWidenedBounds(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DRectF& bounds,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *strokeWidth*  
 Geometri anahattı vuruş yapması genişletmek üzere tutar.  
  
 *strokeStyle*  
 Geometri widens vuruşun stili.  
  
 *worldTransform*  
 Geometri dönüştürüldükten sonra ve geometri vuruş sonra geometriye uygulanacak dönüşüm.  
  
 *sınırları*  
 Bu yöntem döndürüldüğünde, genişletmiştir geometri sınırları içerir. Bu parametre için depolama ayırmanız gerekir.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık olarak geometri noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="isvalid"></a>  CD2DGeometry::IsValid  
 Denetimleri kaynak geçerlilik  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynağın geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_pgeometry"></a>  CD2DGeometry::m_pGeometry  
 Bir ID2D1Geometry gösteren bir işaretçi.  
  
```  
ID2D1Geometry* m_pGeometry;  
```  
  
##  <a name="operator_id2d1geometry_star"></a>  CD2DGeometry::operator ID2D1Geometry *  
 Döndürür ID2D1Geometry arabirimi  
  
```  
operator ID2D1Geometry*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Geometry arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="outline"></a>  CD2DGeometry::Outline  
 Anahat geometrinin hesaplar ve sonucu bir ID2D1SimplifiedGeometrySink yazar.  
  
```  
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *worldTransform*  
 Geometri anahattına uygulanacak dönüşüm.  
  
 *geometrySink*  
 Geometri dönüştürülmüş anahat eklenmiş ID2D1SimplifiedGeometrySink.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık geometrinin noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="simplify"></a>  CD2DGeometry::Simplify  
 Yalnızca çizgileri ve (isteğe bağlı) küp Bezier eğrileri içeren ve sonucu bir ID2D1SimplifiedGeometrySink Yazar geometri basitleştirilmiş bir sürümünü oluşturur.  
  
```  
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *simplificationOption*  
 Basitleştirilmiş geometri Eğriler olup olmayacağını belirten bir değer.  
  
 *worldTransform*  
 Basitleştirilmiş geometriye uygulanacak dönüşüm.  
  
 *geometrySink*  
 Basitleştirilmiş geometri eklenmiş ID2D1SimplifiedGeometrySink.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık geometrinin noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint  
 Geometri 's vuruş verilen belirtilen vuruş kalınlığı, stil ve dönüştürme belirtilen noktası içerip içermediğini belirler.  
  
```  
BOOL StrokeContainsPoint(
    CD2DPointF point,  
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *Noktası*  
 Kapsama için test noktası.  
  
 *strokeWidth*  
 Uygulanacak vuruş kalınlığı.  
  
 *strokeStyle*  
 Uygulanacak vuruşun stili.  
  
 *worldTransform*  
 Konturlu geometriye uygulanacak dönüşüm.  
  
 *İçerir*  
 Bu yöntem döndürüldüğünde, geometri 's vuruş belirtilen noktası içeriyorsa TRUE değerine ayarlayın bir boolean değeri içerir; Aksi takdirde FALSE. Bu parametre için depolama ayırmanız gerekir.  
  
 *flatteningTolerance*  
 Hangi sayısal doğruluğu yolu kesişim ve kesin geometrik yolunu hesaplanır. Tolerans değerinden tarafından vuruşun eksik noktaları hala içinde olarak kabul edilir. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="tessellate"></a>  CD2DGeometry::Tessellate  
 Belirtilen matrisi kullanarak dönüştürüldükten sonra geometri kapsar ve belirtilen tolerans kullanarak düzleştirilmiş sargılı yönünde üçgenler kümesi oluşturur.  
  
```  
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1TessellationSink* tessellationSink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *worldTransform*  
 Bu geometri ya da NULL için uygulanacak dönüşüm.  
  
 *tessellationSink*  
 ID2D1TessellationSink için grubun Mozaik eklenir.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık geometrinin noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="widen"></a>  CD2DGeometry::Widen  
 Geometri tarafından belirtilen vuruşun widens ve edildikten sonra sonucu bir ID2D1SimplifiedGeometrySink yazar tarafından belirtilen matris dönüştürülen ve belirtilen tolerans kullanarak düzleştirilmiş.  
  
```  
BOOL Widen(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *strokeWidth*  
 Geometri genişletmek üzere tutar.  
  
 *strokeStyle*  
 Geometri veya NULL uygulamak için vuruş stili.  
  
 *worldTransform*  
 Genişletme sonra geometriye uygulanacak dönüşüm.  
  
 *geometrySink*  
 Genişletmiştir geometri eklenmiş ID2D1SimplifiedGeometrySink.  
  
 *flatteningTolerance*  
 Çokgen yaklaşık geometrinin noktaları arasında en fazla sınırları mesafeye. Küçük değerler daha doğru sonuçlar ancak yavaş yürütülmesine neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
