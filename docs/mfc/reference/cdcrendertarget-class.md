---
title: "CDCRenderTarget sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 502c9d7cedf782c6ce23ebaf22d30c9b0e5e7409
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget sınıfı
ID2D1DCRenderTarget için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|CDCRenderTarget nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDCRenderTarget::Attach](#attach)|Hedef arabirimini nesneye ekler varolan oluşturmak|  
|[CDCRenderTarget::BindDC](#binddc)|Çizim komutları ermesinin cihaz bağlamı işleme hedefi bağlar|  
|[CDCRenderTarget::Create](#create)|Bir CDCRenderTarget oluşturur.|  
|[CDCRenderTarget::Detach](#detach)|İşleme hedef arabirimi nesneden çıkarır|  
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Döndürür ID2D1DCRenderTarget arabirimi|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|Döndürür ID2D1DCRenderTarget arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget nesneyi gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="attach"></a>CDCRenderTarget::Attach  
 Hedef arabirimini nesneye ekler varolan oluşturmak  
  
```  
void Attach(ID2D1DCRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTarget`  
 Varolan işleme hedefi arabirimi. NULL olamaz  
  
##  <a name="binddc"></a>CDCRenderTarget::BindDC  
 Çizim komutları ermesinin cihaz bağlamı işleme hedefi bağlar  
  
```  
BOOL BindDC(
    const CDC& dc,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `dc`  
 İşleme hedefi çizim komutları sorunların cihaz bağlamı  
  
 `rect`  
 İşleme hedefi bağlı olduğu bir cihaz bağlamı (HDC) tanıtıcısını boyutları  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="cdcrendertarget"></a>CDCRenderTarget::CDCRenderTarget  
 CDCRenderTarget nesnesi oluşturur.  
  
```  
CDCRenderTarget();
```  
  
##  <a name="create"></a>CDCRenderTarget::Create  
 Bir CDCRenderTarget oluşturur.  
  
```  
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```  
  
### <a name="parameters"></a>Parametreler  
 `props`  
 İşleme modunu, piksel biçimi, uzaktan iletişim seçenekleri, DPI bilgi ve donanım işleme için gereken en düşük DirectX desteği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="detach"></a>CDCRenderTarget::Detach  
 İşleme hedef arabirimi nesneden çıkarır  
  
```  
ID2D1DCRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi ayrılmış hedef arabirimi işleyebilir.  
  
##  <a name="getdcrendertarget"></a>CDCRenderTarget::GetDCRenderTarget  
 Döndürür ID2D1DCRenderTarget arabirimi  
  
```  
ID2D1DCRenderTarget* GetDCRenderTarget();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1DCRenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="m_pdcrendertarget"></a>CDCRenderTarget::m_pDCRenderTarget  
 ID2D1DCRenderTarget nesneyi gösteren bir işaretçi.  
  
```  
ID2D1DCRenderTarget* m_pDCRenderTarget;  
```  
  
##  <a name="operator_id2d1dcrendertarget_star"></a>CDCRenderTarget::operator ID2D1DCRenderTarget *  
 Döndürür ID2D1DCRenderTarget arabirimi  
  
```  
operator ID2D1DCRenderTarget*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1DCRenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
