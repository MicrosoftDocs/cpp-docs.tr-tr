---
title: "CD2DRadialGradientBrush sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cdac3e2d2df31840ae90b79755b68d916033990
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush sınıfı
ID2D1RadialGradientBrush için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DRadialGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|CD2DLinearGradientBrush nesnesi oluşturur.|  
|[CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Yok Edicisi. D2D Radyal gradyan fırçası nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DRadialGradientBrush::Create](#create)|Bir CD2DRadialGradientBrush oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DRadialGradientBrush::Destroy](#destroy)|CD2DRadialGradientBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DRadialGradientBrush::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DRadialGradientBrush::get](#get)|Döndürür ID2D1RadialGradientBrush arabirimi|  
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|Gradyan elips merkezini alır.|  
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Gradyan elips 's merkezi göre gradyan başlangıç uzaklığını alır.|  
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Gradyan elipsin x RADIUS alır.|  
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|Gradyan elipsin y RADIUS alır.|  
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|Gradyan elips merkezi fırça koordinat alanında belirtir|  
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Gradyan kaynak gradyan elips 's merkezi göre uzaklığını belirtir|  
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Gradyan elipsin x RADIUS fırça koordinat alanında belirtir|  
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|Gradyan elipsin y RADIUS fırça koordinat alanında belirtir|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|Döndürür ID2D1RadialGradientBrush arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|Bir ID2D1RadialGradientBrush gösteren bir işaretçi.|  
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Center, gradyan başlangıç uzaklığı ve x-radius ve y-radius fırça gradyan.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DRadialGradientBrush`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dradialgradientbrush"></a>CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush  
 Yok Edicisi. D2D Radyal gradyan fırçası nesnesi yok çağrılır.  
  
```  
virtual ~CD2DRadialGradientBrush();
```  
  
##  <a name="attach"></a>CD2DRadialGradientBrush::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1RadialGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush  
 CD2DLinearGradientBrush nesnesi oluşturur.  
  
```  
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `gradientStops`  
 Bir dizi D2D1_GRADIENT_STOP yapıları için bir işaretçi.  
  
 `gradientStopsCount`  
 Gradyan durakları sayısını gradientStops dizisinde belirtir 1'e eşit veya daha büyük değer.  
  
 `RadialGradientBrushProperties`  
 Center, gradyan başlangıç uzaklığı ve x-radius ve y-radius fırça gradyan.  
  
 `colorInterpolationGamma`  
 Hangi renkte gradyan durakları arasında ilişkilendirme gerçekleştirilir alanı.  
  
 `extendMode`  
 [0,1] normalleştirilmiş aralığın dışında geçişin davranışı.  
  
 `pBrushProperties`  
 Opaklık ve fırça dönüşümü için bir işaretçi.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
##  <a name="create"></a>CD2DRadialGradientBrush::Create  
 Bir CD2DRadialGradientBrush oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 İşleme hedefi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>CD2DRadialGradientBrush::Destroy  
 CD2DRadialGradientBrush nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DRadialGradientBrush::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1RadialGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="get"></a>CD2DRadialGradientBrush::get  
 Döndürür ID2D1RadialGradientBrush arabirimi  
  
```  
ID2D1RadialGradientBrush* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1RadialGradientBrush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getcenter"></a>CD2DRadialGradientBrush::GetCenter  
 Gradyan elips merkezini alır.  
  
```  
CD2DPointF GetCenter() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gradyan elips Merkezi. Bu değer fırça koordinat ifade edilir  
  
##  <a name="getgradientoriginoffset"></a>CD2DRadialGradientBrush::GetGradientOriginOffset  
 Gradyan elips 's merkezi göre gradyan başlangıç uzaklığını alır.  
  
```  
CD2DPointF GetGradientOriginOffset() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gradyan elipsin Merkezi'nden gradyan başlangıç uzaklığı. Bu değer fırça koordinat ifade edilir  
  
##  <a name="getradiusx"></a>CD2DRadialGradientBrush::GetRadiusX  
 Gradyan elipsin x RADIUS alır.  
  
```  
FLOAT GetRadiusX() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gradyan elips x-radius. Bu değer fırça koordinat ifade edilir  
  
##  <a name="getradiusy"></a>CD2DRadialGradientBrush::GetRadiusY  
 Gradyan elipsin y RADIUS alır.  
  
```  
FLOAT GetRadiusY() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gradyan elips y-radius. Bu değer fırça koordinat ifade edilir  
  
##  <a name="m_pradialgradientbrush"></a>CD2DRadialGradientBrush::m_pRadialGradientBrush  
 Bir ID2D1RadialGradientBrush gösteren bir işaretçi.  
  
```  
ID2D1RadialGradientBrush* m_pRadialGradientBrush;  
```  
  
##  <a name="m_radialgradientbrushproperties"></a>CD2DRadialGradientBrush::m_RadialGradientBrushProperties  
 Center, gradyan başlangıç uzaklığı ve x-radius ve y-radius fırça gradyan.  
  
```  
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;  
```  
  
##  <a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *  
 Döndürür ID2D1RadialGradientBrush arabirimi  
  
```  
operator ID2D1RadialGradientBrush*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1RadialGradientBrush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="setcenter"></a>CD2DRadialGradientBrush::SetCenter  
 Gradyan elips merkezi fırça koordinat alanında belirtir  
  
```  
void SetCenter(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parametreler  
 `point`  
 Gradyan elipsin fırça koordinat içinde merkezi  
  
##  <a name="setgradientoriginoffset"></a>CD2DRadialGradientBrush::SetGradientOriginOffset  
 Gradyan kaynak gradyan elips 's merkezi göre uzaklığını belirtir  
  
```  
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 `gradientOriginOffset`  
 Gradyan elipsin Merkezi'nden gradyan başlangıç uzaklığı  
  
##  <a name="setradiusx"></a>CD2DRadialGradientBrush::SetRadiusX  
 Gradyan elipsin x RADIUS fırça koordinat alanında belirtir  
  
```  
void SetRadiusX(FLOAT radiusX);
```  
  
### <a name="parameters"></a>Parametreler  
 `radiusX`  
 Gradyan elips x-radius. Bu değer fırça koordinat alan olmalıdır  
  
##  <a name="setradiusy"></a>CD2DRadialGradientBrush::SetRadiusY  
 Gradyan elipsin y RADIUS fırça koordinat alanında belirtir  
  
```  
void SetRadiusY(FLOAT radiusY);
```  
  
### <a name="parameters"></a>Parametreler  
 `radiusY`  
 Gradyan elips y-radius. Bu değer fırça koordinat alan olmalıdır  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
