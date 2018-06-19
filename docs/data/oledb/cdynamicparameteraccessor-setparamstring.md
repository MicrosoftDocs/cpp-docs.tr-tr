---
title: CDynamicParameterAccessor::SetParamString | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs:
- C++
helpviewer_keywords:
- SetParamString method
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0b8c435fea707317c1f8de798796f49cb8b048ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095735"
---
# <a name="cdynamicparameteraccessorsetparamstring"></a>CDynamicParameterAccessor::SetParamString
Arabellekte depolanan belirtilen parametresinin dize verilerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
bool SetParamString(DBORDINAL nParam,   
   constCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,   
   constWCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nParam`  
 [in] Parametre numarası (1 uzaklığı). Parametre 0 dönüş değerleri için ayrılmıştır. Numaralı parametre SQL veya saklı yordam çağrısı, sırayla göre parametre dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) bir örnek.  
  
 `pString`  
 [in] ANSI işaretçisine (**CHAR**) veya Unicode (**WCHAR**) dize belirtilen parametre verileri. Bkz: `DBSTATUS` biçim içinde.  
  
 *Durumu*  
 [in] `DBSTATUS` Belirtilen parametre durumu. Hakkında bilgi için `DBSTATUS` değerler, bakın [durum](https://msdn.microsoft.com/en-us/library/ms722617.aspx) içinde *OLE DB Programcının Başvurusu*, veya arama `DBSTATUS` biçim içinde.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürür **true** başarı veya **false** hatasında.  
  
 `SetParamString` Belirtilen Maksimum boyuttan daha büyük olan bir dize ayarlamaya çalışırsanız başarısız olur `pString`.  
  
 Kullanım `SetParamString` dizesi parametre verilerini arabellekte ayarlamak için. Kullanım [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) arabellekte dize olmayan parametre veri kümesi için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)