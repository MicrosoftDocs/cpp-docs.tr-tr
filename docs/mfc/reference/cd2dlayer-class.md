---
title: "CD2DLayer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
dev_langs: C++
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94345f4784254addce0deaf8bdb5061dbde6a8cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dlayer-class"></a>CD2DLayer sınıfı
ID2D1Layer için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DLayer::CD2DLayer](#cd2dlayer)|CD2DLayer nesnesi oluşturur.|  
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Yok Edicisi. D2D katman nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DLayer::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DLayer::Create](#create)|Bir CD2DLayer oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLayer::Destroy](#destroy)|CD2DLayer nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DLayer::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DLayer::get](#get)|Döndürür ID2D1Layer arabirimi|  
|[CD2DLayer::GetSize](#getsize)|CİHAZDAN bağımsız piksel cinsinden işleme hedef boyutunu döndürür|  
|[CD2DLayer::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DLayer::operator ID2D1Layer *](#operator_id2d1layer_star)|Döndürür ID2D1Layer arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DLayer::m_pLayer](#m_player)|ID2D1Layer nesneyi gösteren bir işaretçi depolar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DLayer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dlayer"></a>CD2DLayer:: ~ CD2DLayer  
 Yok Edicisi. D2D katman nesnesi yok çağrılır.  
  
```  
virtual ~CD2DLayer();
```  
  
##  <a name="attach"></a>CD2DLayer::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1Layer* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dlayer"></a>CD2DLayer::CD2DLayer  
 CD2DLayer nesnesi oluşturur.  
  
```  
CD2DLayer(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
##  <a name="create"></a>CD2DLayer::Create  
 Bir CD2DLayer oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 İşleme hedefi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>CD2DLayer::Destroy  
 CD2DLayer nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DLayer::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1Layer* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="get"></a>CD2DLayer::get  
 Döndürür ID2D1Layer arabirimi  
  
```  
ID2D1Layer* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Layer arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getsize"></a>CD2DLayer::GetSize  
 CİHAZDAN bağımsız piksel cinsinden işleme hedef boyutunu döndürür  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleme hedef aygıttan bağımsız piksel cinsinden geçerli boyutu  
  
##  <a name="isvalid"></a>CD2DLayer::IsValid  
 Denetimleri kaynak geçerlilik  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynağın geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_player"></a>CD2DLayer::m_pLayer  
 ID2D1Layer nesneyi gösteren bir işaretçi depolar.  
  
```  
ID2D1Layer* m_pLayer;  
```  
  
##  <a name="operator_id2d1layer_star"></a>CD2DLayer::operator ID2D1Layer *  
 Döndürür ID2D1Layer arabirimi  
  
```  
operator ID2D1Layer* ();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Layer arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
