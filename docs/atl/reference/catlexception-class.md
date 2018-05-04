---
title: CAtlException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaafdf42d218e2c3bca1e8ee28c27898f80bcf40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
  
##  <a name="catlexception"></a>  CAtlException::CAtlException  
 Oluşturucu.  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hr`  
 `HRESULT` Hata kodu.  
  
##  <a name="operator_hresult"></a>  CAtlException::operator HRESULT 
 Geçerli nesne HRESULT değerine çevirir.  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>  CAtlException::m_hr  
 `HRESULT` Veri üyesi.  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hata koşulu depolar veri üyesi. HRESULT değer oluşturucusu tarafından ayarlanır [CAtlException::CAtlException](#catlexception).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
