---
title: CUtlProps::OnPropertyChanged | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
dev_langs:
- C++
helpviewer_keywords:
- OnPropertyChanged method
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3117a22a2b08b95528692d88cfb6e136d209e346
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cutlpropsonpropertychanged"></a>CUtlProps::OnPropertyChanged
Zincirleme özellikleri işlemek üzere bir özelliğe ayarladıktan sonra çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `iCurSet`  
 Özellik kümesi dizi dizine; yalnızca bir özellik kümesi ise sıfır.  
  
 `pDBProp`  
 Özellik kimliği ve yeni değer bir [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`. Varsayılan dönüş değeri: `S_OK`.  
  
## <a name="remarks"></a>Açıklamalar  
 Yer işaretleri veya değerleri başka bir özelliğin değeri, bağımlı olan güncelleştirmeleri gibi zincirleme özellikleri işlemek istiyorsanız, bu işlev üzerine yazması gerekir.  
  
## <a name="example"></a>Örnek  
 Bu işlevde kullanıcı özelliği Kimliğinden alır `DBPROP*` parametresi. Artık, Kimliğine zinciri özelliğine karşı karşılaştırmak mümkündür. Özellik bulunduğunda, `SetProperties` diğer özelliği ile bağlantılı şimdi ayarlanacak özelliği ile adlandırılır. Bu durumda, bir alırsa `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, veya `DBPROP_ORDEREDBOOKMARKS` özelliği, bir ayarlayabilirsiniz `DBPROP_BOOKMARKS` özelliği.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CUtlProps Sınıfı](../../data/oledb/cutlprops-class.md)