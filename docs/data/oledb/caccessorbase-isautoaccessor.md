---
title: "CAccessorBase::ısautoaccessor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
dev_langs: C++
helpviewer_keywords: IsAutoAccessor method
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a08251ddf32f815390c28677f03536e1c2cec7d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="caccessorbaseisautoaccessor"></a>CAccessorBase::IsAutoAccessor
Veri taşıma işlemi sırasında otomatik olarak için erişimci alınır, true döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      bool IsAutoAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nAccessor`  
 [in] Erişimci sıfır uzaklığı numarası.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** erişimci erişimcinin ise. Aksi takdirde, döndürür **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAccessorBase sınıfı](../../data/oledb/caccessorbase-class.md)