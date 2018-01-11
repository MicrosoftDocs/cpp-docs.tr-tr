---
title: "CUtlProps::ısvalidvalue | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
dev_langs: C++
helpviewer_keywords: IsValidValue method
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 06193b8c560c5ac6006698813222e698a98bccc3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropsisvalidvalue"></a>CUtlProps::IsValidValue
Bir özelliğini ayarlamadan önce bir değer doğrulamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `iCurSet`  
 Özellik kümesi dizi dizine; yalnızca bir özellik kümesi ise sıfır.  
  
 `pDBProp`  
 Özellik kimliği ve yeni değer bir [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`. Varsayılan dönüş değeri: `S_OK`.  
  
## <a name="remarks"></a>Açıklamalar  
 Yaklaşık bir özelliği ayarlamak için kullanılacak olan değer üzerinde çalıştırmak istediğiniz herhangi bir doğrulama yordamları varsa, bu işlev üzerine yazması gerekir. Örneğin, doğrulama **DBPROP_AUTH_PASSWORD** geçerli bir değer belirlemek için bir parola tabloda.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CUtlProps Sınıfı](../../data/oledb/cutlprops-class.md)