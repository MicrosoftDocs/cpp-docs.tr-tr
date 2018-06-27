---
title: CBitmapRenderTarget sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0eece5c7ba74f523836ab5916b8817671dac287
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956758"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget sınıfı
ID2D1BitmapRenderTarget için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|CBitmapRenderTarget nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmapRenderTarget::Attach](#attach)|Hedef arabirimini nesneye ekler varolan oluşturmak|  
|[CBitmapRenderTarget::Detach](#detach)|İşleme hedef arabirimi nesneden çıkarır|  
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Bu işleme hedefi için bit eşlemde alır. Döndürülen bit eşlem işlemleri çizim için kullanılabilir.|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Döndürür ID2D1BitmapRenderTarget arabirimi|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Döndürür ID2D1BitmapRenderTarget arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|ID2D1BitmapRenderTarget nesneyi gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 `CBitmapRenderTarget` 
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="attach"></a>  CBitmapRenderTarget::Attach  
 Hedef arabirimini nesneye ekler varolan oluşturmak  
  
```  
void Attach(ID2D1BitmapRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 *pTarget*  
 Varolan işleme hedefi arabirimi. NULL olamaz  
  
##  <a name="cbitmaprendertarget"></a>  CBitmapRenderTarget::CBitmapRenderTarget  
 CBitmapRenderTarget nesnesi oluşturur.  
  
```  
CBitmapRenderTarget();
```  
  
##  <a name="detach"></a>  CBitmapRenderTarget::Detach  
 İşleme hedef arabirimi nesneden çıkarır  
  
```  
ID2D1BitmapRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi ayrılmış hedef arabirimi işleyebilir.  
  
##  <a name="getbitmap"></a>  CBitmapRenderTarget::GetBitmap  
 Bu işleme hedefi için bit eşlemde alır. Döndürülen bit eşlem işlemleri çizim için kullanılabilir.  
  
```  
BOOL GetBitmap(CD2DBitmap& bitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 *bit eşlem*  
 Bu yöntem döndürüldüğünde, bu işleme hedefi için geçerli bit eşlemi içerir. Bu bit eşlemi işlemleri çizim için kullanılabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
##  <a name="getbitmaprendertarget"></a>  CBitmapRenderTarget::GetBitmapRenderTarget  
 Döndürür ID2D1BitmapRenderTarget arabirimi  
  
```  
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1BitmapRenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="m_pbitmaprendertarget"></a>  CBitmapRenderTarget::m_pBitmapRenderTarget  
 ID2D1BitmapRenderTarget nesneyi gösteren bir işaretçi.  
  
```  
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;  
```  
  
##  <a name="operator_id2d1bitmaprendertarget_star"></a>  CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *  
 Döndürür ID2D1BitmapRenderTarget arabirimi  
  
```  
operator ID2D1BitmapRenderTarget*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1BitmapRenderTarget arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
