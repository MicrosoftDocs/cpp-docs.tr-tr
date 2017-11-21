---
title: CUtlProps::SetPropValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a137420383f4084a1795e4f28d58f36b0825feb8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
Bir özelliği bir özellik kümesi ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT SetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pguidPropSet`  
 [in] PropSet için GUID.  
  
 `dwPropId`  
 [in] Özellik dizini.  
  
 `pvValue`  
 [in] Yeni özellik değerini içeren bir değişken için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `Failure`hatasında ve `S_OK` başarılı olursa.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CUtlProps sınıfı](../../data/oledb/cutlprops-class.md)