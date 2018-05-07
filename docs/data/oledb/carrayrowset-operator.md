---
title: CArrayRowset::operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 755e484f430f47eb072e3c590bfbee8471984bb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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