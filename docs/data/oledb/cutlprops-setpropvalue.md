---
title: CUtlProps::SetPropValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs:
- C++
helpviewer_keywords:
- SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 73f2432a23adf8fe11f759c2caa85d9653040635
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099075"
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
Bir özelliği bir özellik kümesi ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pguidPropSet`  
 [in] PropSet için GUID.  
  
 `dwPropId`  
 [in] Özellik dizini.  
  
 `pvValue`  
 [in] Yeni özellik değerini içeren bir değişken için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `Failure` hatasında ve `S_OK` başarılı olursa.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CUtlProps Sınıfı](../../data/oledb/cutlprops-class.md)