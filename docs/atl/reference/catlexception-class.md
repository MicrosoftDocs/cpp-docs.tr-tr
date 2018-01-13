---
title: "CAtlException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs: C++
helpviewer_keywords: CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0af7fa5a0bc78043e0eac204255f30ab1b9672c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlexception-class"></a>CAtlException sınıfı
Bu sınıf ATL istisna tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlException
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlException::CAtlException](#catlexception)|Oluşturucu.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlException::operator HRESULT](#operator_hresult)|Geçerli nesne HRESULT değerine çevirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|Türündeki değişken HRESULT nesne tarafından oluşturulan ve hata durumunu depolamak için kullanılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CAtlException` nesnesi bir ATL işlemle ilişkili bir özel durumu temsil eder. `CAtlException` Sınıfı özel durumu ve HRESULT değilmiş gibi özel durumu işlemek izin veren bir atama işleci nedeni gösteren durum kodunu depolar ortak veri üyesi içerir.  
  
 Genel olarak, çağıracaksınız `AtlThrow` oluşturmak yerine bir `CAtlException` doğrudan nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlexcept.h  
  
##  <a name="catlexception"></a>CAtlException::CAtlException  
 Oluşturucu.  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hr`  
 `HRESULT` Hata kodu.  
  
##  <a name="operator_hresult"></a>CAtlException::operator HRESULT 
 Geçerli nesne HRESULT değerine çevirir.  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>CAtlException::m_hr  
 `HRESULT` Veri üyesi.  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hata koşulu depolar veri üyesi. HRESULT değer oluşturucusu tarafından ayarlanır [CAtlException::CAtlException](#catlexception).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
