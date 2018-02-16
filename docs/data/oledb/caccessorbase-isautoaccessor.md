---
title: "CAccessorBase::ısautoaccessor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
dev_langs:
- C++
helpviewer_keywords:
- IsAutoAccessor method
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 168956019b419f80e8d630e58960b9ba2d07a761
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="caccessorbaseisautoaccessor"></a>CAccessorBase::IsAutoAccessor
Veri taşıma işlemi sırasında otomatik olarak için erişimci alınır, true döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      bool IsAutoAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nAccessor`  
 [in] Erişimci sıfır uzaklığı numarası.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** erişimci erişimcinin ise. Aksi takdirde, döndürür **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAccessorBase Sınıfı](../../data/oledb/caccessorbase-class.md)