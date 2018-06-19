---
title: CUtlProps::OnPropertyChanged | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
dev_langs:
- C++
helpviewer_keywords:
- OnPropertyChanged method
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c9b52949db714206b6118000d004c6248b7d6235
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100505"
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