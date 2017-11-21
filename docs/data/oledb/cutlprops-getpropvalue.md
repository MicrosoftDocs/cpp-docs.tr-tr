---
title: CUtlProps::GetPropValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs: C++
helpviewer_keywords: GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 857738960ff6a141bbde363a7db1193e6f5e21f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
Bir özelliği bir özellik kümesinden alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      OUT_OF_LINE HRESULT GetPropValue(  
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
 [out] Yeni özellik değerini içeren bir değişken için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `Failure`hatasında ve `S_OK` başarılı olursa.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CUtlProps sınıfı](../../data/oledb/cutlprops-class.md)