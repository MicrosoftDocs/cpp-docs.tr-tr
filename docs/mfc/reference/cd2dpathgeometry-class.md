---
title: "CD2DPathGeometry sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
dev_langs: C++
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9142b268c5f09a88883d048c35287966d9ef8aab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry sınıfı
ID2D1PathGeometry için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|CD2DPathGeometry nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DPathGeometry::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DPathGeometry::Create](#create)|Bir CD2DPathGeometry oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DPathGeometry::Destroy](#destroy)|CD2DPathGeometry nesnesini yok eder. (Geçersiz kılmaları [CD2DGeometry::Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|  
|[CD2DPathGeometry::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Yol geometri rakamı sayısını alır.|  
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Yol geometri bölümlerinin sayısını alır.|  
|[CD2DPathGeometry::Open](#open)|Şekiller ve kesimleri ile yolu geometri doldurmak için kullanılan geometri havuz alır.|  
|[CD2DPathGeometry::Stream](#stream)|Yol geometri içeriğini belirtilen ID2D1GeometrySink kopyalar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|Bir ID2D1PathGeometry gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 `CD2DPathGeometry`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="attach"></a>CD2DPathGeometry::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1PathGeometry* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dpathgeometry"></a>CD2DPathGeometry::CD2DPathGeometry  
 CD2DPathGeometry nesnesi oluşturur.  
  
```  
CD2DPathGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
##  <a name="create"></a>CD2DPathGeometry::Create  
 Bir CD2DPathGeometry oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 İşleme hedefi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>CD2DPathGeometry::Destroy  
 CD2DPathGeometry nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DPathGeometry::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1PathGeometry* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="getfigurecount"></a>CD2DPathGeometry::GetFigureCount  
 Yol geometri rakamı sayısını alır.  
  
```  
int GetFigureCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yol geometri rakamları sayısını döndürür.  
  
##  <a name="getsegmentcount"></a>CD2DPathGeometry::GetSegmentCount  
 Yol geometri bölümlerinin sayısını alır.  
  
```  
int GetSegmentCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yol geometri bölümlerinin sayısını döndürür.  
  
##  <a name="m_ppathgeometry"></a>CD2DPathGeometry::m_pPathGeometry  
 Bir ID2D1PathGeometry gösteren bir işaretçi.  
  
```  
ID2D1PathGeometry* m_pPathGeometry;  
```  
  
##  <a name="open"></a>CD2DPathGeometry::Open  
 Şekiller ve kesimleri ile yolu geometri doldurmak için kullanılan geometri havuz alır.  
  
```  
ID2D1GeometrySink* Open();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şekiller ve kesimleri ile yolu geometri doldurmak için kullanılan ID2D1GeometrySink gösteren bir işaretçi.  
  
##  <a name="stream"></a>CD2DPathGeometry::Stream  
 Yol geometri içeriğini belirtilen ID2D1GeometrySink kopyalar.  
  
```  
BOOL Stream(ID2D1GeometrySink* geometrySink);
```  
  
### <a name="parameters"></a>Parametreler  
 `geometrySink`  
 Havuz için yol geometri 's içeriği kopyalanır. Bu havuz değiştirerek bu yolu geometri içeriğini değiştirmez.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
