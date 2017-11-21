---
title: "CDefaultCharTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs: C++
helpviewer_keywords: CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 02595c426a631e15bf2f1b5baed2550a8befe20a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits sınıfı
Bu sınıf, büyük ve küçük harf karakter dönüştürme için iki statik işlevler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(Statik) Bir karakterin büyük harfe dönüştürülecek bu işlevini çağırın.|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Statik) Bir karakteri küçük harfe dönüştürmek için bu işlevini çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf sınıfı tarafından kullanılan işlevleri sağlayan [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="chartolower"></a>CDefaultCharTraits::CharToLower  
 Bir karakteri küçük harfe dönüştürmek için bu işlevini çağırın.  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Küçük harfe dönüştürmek için karakter.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="chartoupper"></a>CDefaultCharTraits::CharToUpper  
 Bir karakterin büyük harfe dönüştürülecek bu işlevini çağırın.  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Büyük harfe dönüştürülecek karakter.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
