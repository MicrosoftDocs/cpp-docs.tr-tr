---
title: CDynamicParameterAccessor::GetParam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
dev_langs:
- C++
helpviewer_keywords:
- GetParam method
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3596cf8fc445a5607c008be687c44cafb713049b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090907"
---
# <a name="cdynamicparameteraccessorgetparam"></a>CDynamicParameterAccessor::GetParam
Belirtilen parametre dize olmayan verileri parametresi arabelleğinden alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,   
  ctype* pData) const throw();  

template <class ctype> bool GetParam(TCHAR* pParamName,   
   ctype* pData) const throw();  

void* GetParam(DBORDINAL nParam) const throw();  

void* GetParam(TCHAR* pParamName) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ctype`  
 Veri türü şablonlu parametresi.  
  
 `nParam`  
 [in] Parametre numarası (1 uzaklığı). Parametre 0 dönüş değerleri için ayrılmıştır. Numaralı parametre SQL veya saklı yordam çağrısı, sırayla göre parametre dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) bir örnek.  
  
 `pParamName`  
 [in] Parametre adı.  
  
 `pData`  
 [out] Arabellekteki alınan verileri içeren bellek işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Nontemplated sürümleri için verileri içeren bellek noktalarına arabelleğinden aldı. Şablonlu sürümleri için döndürür **true** başarı veya **false** hatasında.  
  
 Kullanım `GetParam` arabelleğinden dize olmayan parametre veri alınamadı. Kullanım [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) arabelleğinden dizesi parametre verilerini almak için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)