---
title: "CD2DSolidColorBrush sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
dev_langs: C++
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd1f4d6de1565ae4c457a562d9056c020d44f771
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush sınıfı
ID2D1SolidColorBrush için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DSolidColorBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Fazla Yüklendi. CD2DSolidColorBrush nesnesi oluşturur.|  
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#cd2dsolidcolorbrush__~cd2dsolidcolorbrush)|Yok Edicisi. D2D düz fırça nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DSolidColorBrush::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DSolidColorBrush::Create](#create)|Bir CD2DSolidColorBrush oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DSolidColorBrush::Destroy](#destroy)|CD2DSolidColorBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DSolidColorBrush::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DSolidColorBrush::get](#get)|Döndürür ID2D1SolidColorBrush arabirimi|  
|[CD2DSolidColorBrush::GetColor](#getcolor)|Düz renk fırça rengi alır.|  
|[CD2DSolidColorBrush::SetColor](#setcolor)|Bu düz renk fırça rengini belirtir|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|Döndürür ID2D1SolidColorBrush arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|Düz renk fırça.|  
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|ID2D1SolidColorBrush nesneyi gösteren bir işaretçi depolar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dsolidcolorbrush"></a>CD2DSolidColorBrush:: ~ CD2DSolidColorBrush  
 Yok Edicisi. D2D düz fırça nesnesi yok çağrılır.  
  
```  
virtual ~CD2DSolidColorBrush();
```  
  
##  <a name="attach"></a>CD2DSolidColorBrush::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1SolidColorBrush* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dsolidcolorbrush"></a>CD2DSolidColorBrush::CD2DSolidColorBrush  
 CD2DSolidColorBrush nesnesi oluşturur.  
  
```  
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    D2D1_COLOR_F color,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    COLORREF color,  
    int nAlpha = 255,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `color`  
 Fırça rengi kırmızı, yeşil, mavi ve alfa değerleri.  
  
 `pBrushProperties`  
 Opaklık ve fırça dönüşümü için bir işaretçi.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
 `nAlpha`  
 Fırça rengin geçirgenliğini.  
  
##  <a name="create"></a>CD2DSolidColorBrush::Create  
 Bir CD2DSolidColorBrush oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 İşleme hedefi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>CD2DSolidColorBrush::Destroy  
 CD2DSolidColorBrush nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DSolidColorBrush::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1SolidColorBrush* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="get"></a>CD2DSolidColorBrush::get  
 Döndürür ID2D1SolidColorBrush arabirimi  
  
```  
ID2D1SolidColorBrush* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1SolidColorBrush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getcolor"></a>CD2DSolidColorBrush::GetColor  
 Düz renk fırça rengi alır.  
  
```  
D2D1_COLOR_F GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu düz renk fırça rengi  
  
##  <a name="m_colorsolid"></a>CD2DSolidColorBrush::m_colorSolid  
 Düz renk fırça.  
  
```  
D2D1_COLOR_F m_colorSolid;  
```  
  
##  <a name="m_psolidcolorbrush"></a>CD2DSolidColorBrush::m_pSolidColorBrush  
 ID2D1SolidColorBrush nesneyi gösteren bir işaretçi depolar.  
  
```  
ID2D1SolidColorBrush* m_pSolidColorBrush;  
```  
  
##  <a name="operator_id2d1solidcolorbrush_star"></a>CD2DSolidColorBrush::operator ID2D1SolidColorBrush *  
 Döndürür ID2D1SolidColorBrush arabirimi  
  
```  
operator ID2D1SolidColorBrush*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1SolidColorBrush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="setcolor"></a>CD2DSolidColorBrush::SetColor  
 Bu düz renk fırça rengini belirtir  
  
```  
void SetColor(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 Bu düz renk fırça rengi  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
