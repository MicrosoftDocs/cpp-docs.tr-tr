---
title: CD2DBrush sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 324e6411673a509bdf75954634ff9c6dffc5ce1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354432"
---
# <a name="cd2dbrush-class"></a>CD2DBrush sınıfı
ID2D1Brush için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|CD2DBrush nesnesi oluşturur.|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Yok Edicisi. D2D fırça nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DBrush::Destroy](#destroy)|CD2DBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DBrush::get](#get)|Döndürür ID2D1Brush arabirimi|  
|[CD2DBrush::GetOpacity](#getopacity)|Bu fırça geçirgenliğini derecesini alır|  
|[CD2DBrush::GetTransform](#gettransform)|Geçerli dönüştürme işleme hedef alır|  
|[CD2DBrush::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|Bu fırça geçirgenliğini derecesini ayarlar|  
|[CD2DBrush::SetTransform](#settransform)|Belirtilen dönüşüm varolan dönüştürme değiştirme işleme hedef için geçerlidir. Tüm sonraki çizim işlemleri dönüştürülmüş alanı oluşur|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|Döndürür ID2D1Brush arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|ID2D1Brush nesneyi gösteren bir işaretçi depolar.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Fırça özellikleri.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>  CD2DBrush:: ~ CD2DBrush  
 Yok Edicisi. D2D fırça nesnesi yok çağrılır.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>  CD2DBrush::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dbrush"></a>  CD2DBrush::CD2DBrush  
 CD2DBrush nesnesi oluşturur.  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `pBrushProperties`  
 Opaklık ve fırça dönüşümü için bir işaretçi.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
##  <a name="destroy"></a>  CD2DBrush::Destroy  
 CD2DBrush nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DBrush::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="get"></a>  CD2DBrush::get  
 Döndürür ID2D1Brush arabirimi  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Brush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getopacity"></a>  CD2DBrush::GetOpacity  
 Bu fırça geçirgenliğini derecesini alır  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır fırça geçirgenliğini gösteren 1 arasında bir değer. Bu değer tüm pikselleri fırça tarafından doldurulmuş alfa değeri doğrusal olarak ölçeklendirir sabit bir çarpanı olur. Birlikte çarpıldığı önce opaklık değerleri aralığı 0'dan 1 clamped  
  
##  <a name="gettransform"></a>  CD2DBrush::GetTransform  
 Geçerli dönüştürme işleme hedef alır  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `transform`  
 Bu geri döndüğünde, işleme hedef geçerli dönüştürme içerir. Bu parametre, başlatmadan iletilir  
  
##  <a name="isvalid"></a>  CD2DBrush::IsValid  
 Denetimleri kaynak geçerlilik  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynağın geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_pbrush"></a>  CD2DBrush::m_pBrush  
 ID2D1Brush nesneyi gösteren bir işaretçi depolar.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>  CD2DBrush::m_pBrushProperties  
 Fırça özellikleri.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>  CD2DBrush::operator ID2D1Brush *  
 Döndürür ID2D1Brush arabirimi  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Brush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="setopacity"></a>  CD2DBrush::SetOpacity  
 Bu fırça geçirgenliğini derecesini ayarlar  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>Parametreler  
 `opacity`  
 Sıfır fırça geçirgenliğini gösteren 1 arasında bir değer. Bu değer tüm pikselleri fırça tarafından doldurulmuş alfa değeri doğrusal olarak ölçeklendirir sabit bir çarpanı olur. Birlikte çarpıldığı önce opaklık değerleri aralığı 0'dan 1 clamped  
  
##  <a name="settransform"></a>  CD2DBrush::SetTransform  
 Belirtilen dönüşüm varolan dönüştürme değiştirme işleme hedef için geçerlidir. Tüm sonraki çizim işlemleri dönüştürülmüş alanı oluşur  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Parametreler  
 `transform`  
 İşleme hedefe uygulanacak dönüşümü  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
