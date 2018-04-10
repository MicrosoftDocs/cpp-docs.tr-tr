---
title: CHwndRenderTarget sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f11f7e329b623639fb1441e4d9e18720a6b6b94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget sınıfı
ID2D1HwndRenderTarget için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|HWND CHwndRenderTarget nesnesinden oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](#attach)|Hedef arabirimini nesneye ekler varolan oluşturmak|  
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Bu işleme hedefle ilişkili HWND occluded olup olmadığını gösterir.|  
|[CHwndRenderTarget::Create](#create)|Pencerenin ile ilişkili bir işleme hedef oluşturur.|  
|[CHwndRenderTarget::Detach](#detach)|İşleme hedef arabirimi nesneden çıkarır|  
|[CHwndRenderTarget::GetHwnd](#gethwnd)|Bu ile ilişkili HWND döndürür hedef işleyebilir.|  
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget arabirimi döndürür.|  
|[CHwndRenderTarget::ReCreate](#recreate)|Pencerenin ile ilişkili bir işleme hedef yeniden oluşturur.|  
|[CHwndRenderTarget::Resize](#resize)|Belirtilen piksel boyutuna işleme hedef boyutunu değiştirir|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget arabirimi döndürür.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget nesneyi gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="attach"></a>CHwndRenderTarget::Attach  
 Hedef arabirimini nesneye ekler varolan oluşturmak  
  
```  
void Attach(ID2D1HwndRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTarget`  
 Varolan işleme hedefi arabirimi. NULL olamaz  
  
##  <a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState  
 Bu işleme hedefle ilişkili HWND occluded olup olmadığını gösterir.  
  
```  
D2D1_WINDOW_STATE CheckWindowState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu ile ilişkili HWND hedef işlenip işlenmeyeceğini belirten bir değer occluded.  
  
##  <a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget  
 HWND CHwndRenderTarget nesnesinden oluşturur.  
  
```  
CHwndRenderTarget(HWND hwnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `hwnd`  
 Bu ile ilişkili HWND hedef işleme  
  
##  <a name="create"></a>CHwndRenderTarget::Create  
 Pencerenin ile ilişkili bir işleme hedef oluşturur.  
  
```  
BOOL Create(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 Bu ile ilişkili HWND hedef işleme  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür  
  
##  <a name="detach"></a>CHwndRenderTarget::Detach  
 İşleme hedef arabirimi nesneden çıkarır  
  
```  
ID2D1HwndRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi ayrılmış hedef arabirimi işleyebilir.  
  
##  <a name="gethwnd"></a>CHwndRenderTarget::GetHwnd  
 Bu ile ilişkili HWND döndürür hedef işleyebilir.  
  
```  
HWND GetHwnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu ile ilişkili HWND hedef işleyebilir.  
  
##  <a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget  
 ID2D1HwndRenderTarget arabirimi döndürür.  
  
```  
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1HwndRenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget  
 ID2D1HwndRenderTarget nesneyi gösteren bir işaretçi.  
  
```  
ID2D1HwndRenderTarget* m_pHwndRenderTarget;  
```  
  
##  <a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::operator ID2D1HwndRenderTarget *  
 ID2D1HwndRenderTarget arabirimi döndürür.  
  
```  
operator ID2D1HwndRenderTarget*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1HwndRenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="recreate"></a>CHwndRenderTarget::ReCreate  
 Pencerenin ile ilişkili bir işleme hedef yeniden oluşturur.  
  
```  
BOOL ReCreate(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 Bu ile ilişkili HWND hedef işleme  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="resize"></a>CHwndRenderTarget::Resize  
 Belirtilen piksel boyutuna işleme hedef boyutunu değiştirir  
  
```  
BOOL Resize(const CD2DSizeU& size);
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 Yeni işleme hedef aygıt piksel cinsinden boyutu  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
