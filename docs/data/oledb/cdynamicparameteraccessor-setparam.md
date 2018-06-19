---
title: CDynamicParameterAccessor::SetParam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
dev_langs:
- C++
helpviewer_keywords:
- SetParam method
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 37f60999eb87d473fb51bb0a493a79d0edf96074
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096645"
---
# <a name="cdynamicparameteraccessorsetparam"></a>CDynamicParameterAccessor::SetParam
Belirtilen (dize olmayan) verileri kullanarak parametre arabelleği ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,  
               constctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  

template <class ctype>  
bool SetParam(TCHAR* pParamName,  
               const ctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ctype`  
 Veri türü şablonlu parametresi.  
  
 `nParam`  
 [in] Parametre numarası (1 uzaklığı). Parametre 0 dönüş değerleri için ayrılmıştır. Numaralı parametre SQL veya saklı yordam çağrısı, sırayla göre parametre dizinidir. Örneğin:  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 [in] Parametre adı.  
  
 `pData`  
 [in] Arabelleğe yazılacak veriler içeren bellek işaretçisi.  
  
 *Durumu*  
 [in] `DBSTATUS` Sütun durumu. Hakkında bilgi için `DBSTATUS` değerler, bakın [durum](https://msdn.microsoft.com/en-us/library/ms722617.aspx) içinde *OLE DB Programcının Başvurusu*, veya arama `DBSTATUS` biçim içinde.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** başarı veya **false** hatasında.  
  
 Kullanım `SetParam` arabellekte dize olmayan parametre veri kümesi için. Kullanım [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) dizesi parametre verilerini arabellekte ayarlamak için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)