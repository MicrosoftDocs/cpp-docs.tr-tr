---
title: CArrayRowset::operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs:
- C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0921ad4c574c496656ec616d1d569158c596c5ad
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
Satır kümesindeki erişmek için dizi benzeri bir sözdizimi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Satır kümesinde depolanan erişimcisi türünü belirtir. şablonlu parametresi.  
  
 `nRow`  
 [in] Erişmek istediğiniz satır (dizi öğesi) sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İstenen satır içerikleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `nRow` satır kümesinde satır sayısını aşıyor, bir özel durum.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CArrayRowset Sınıfı](../../data/oledb/carrayrowset-class.md)