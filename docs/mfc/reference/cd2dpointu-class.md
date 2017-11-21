---
title: "CD2DPointU sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs: C++
helpviewer_keywords: CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d2c7525e5b4626fa2075c5f609ca2fa3affcfc4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cd2dpointu-class"></a>CD2DPointU sınıfı
İçin sarmalayıcı `D2D1_POINT_2U`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DPointU : public D2D1_POINT_2U;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Fazla Yüklendi. Oluşturan bir `CD2DPointU` nesnesinden `D2D1_POINT_2U` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DPointU::operator CPoint](#operator_cpoint)|Dönüştürür `CD2DPointU` için `CPoint` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_POINT_2U`  
  
 `CD2DPointU`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2dpointu"></a>CD2DPointU::CD2DPointU  
 CPoint nesnesinden CD2DPointU nesnesi oluşturur.  
  
```  
CD2DPointU(const CPoint& pt);  
CD2DPointU(const D2D1_POINT_2U& pt);  
  CD2DPointU(const D2D1_POINT_2U* pt);  
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 Kaynak noktası  
  
 `uX`  
 Kaynak X  
  
 `uY`  
 Kaynak Y  
  
##  <a name="operator_cpoint"></a>CD2DPointU::operator CPoint  
 CD2DPointU CPoint nesnesine dönüştürür.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D noktanın geçerli değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
