---
title: CDynamicParameterAccessor::SetParamString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
dev_langs: C++
helpviewer_keywords: SetParamString method
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff96f451bc60469df0469d6a002ec51d91743b89
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessorsetparamstring"></a>CDynamicParameterAccessor::SetParamString
Arabellekte depolanan belirtilen parametresinin dize verilerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nParam`  
 [in] Parametre numarası (1 uzaklığı). Parametre 0 dönüş değerleri için ayrılmıştır. Numaralı parametre SQL veya saklı yordam çağrısı, sırayla göre parametre dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) bir örnek.  
  
 `pString`  
 [in] ANSI işaretçisine (**CHAR**) veya Unicode (**WCHAR**) dize belirtilen parametre verileri. Bkz: `DBSTATUS` biçim içinde.  
  
 *durumu*  
 [in] `DBSTATUS` Belirtilen parametre durumu. Hakkında bilgi için `DBSTATUS` değerler, bakın [durum](https://msdn.microsoft.com/en-us/library/ms722617.aspx) içinde *OLE DB Programcının Başvurusu*, veya arama `DBSTATUS` biçim içinde.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürür **true** başarı veya **false** hatasında.  
  
 `SetParamString`Belirtilen Maksimum boyuttan daha büyük olan bir dize ayarlamaya çalışırsanız başarısız olur `pString`.  
  
 Kullanım `SetParamString` dizesi parametre verilerini arabellekte ayarlamak için. Kullanım [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) arabellekte dize olmayan parametre veri kümesi için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)