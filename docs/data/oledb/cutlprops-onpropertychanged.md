---
title: CUtlProps::OnPropertyChanged | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
dev_langs: C++
helpviewer_keywords: OnPropertyChanged method
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b517bfe6ef3cc93b6edf647d137491ef78c0f716
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cutlpropsonpropertychanged"></a>CUtlProps::OnPropertyChanged
Zincirleme özellikleri işlemek üzere bir özelliğe ayarladıktan sonra çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      virtual HRESULT OnPropertyChanged(  
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
 Yer işaretleri veya değerleri başka bir özelliğin değeri, bağımlı olan güncelleştirmeleri gibi zincirleme özellikleri işlemek istiyorsanız, bu işlev üzerine yazması gerekir.  
  
## <a name="example"></a>Örnek  
 Bu işlevde kullanıcı özelliği Kimliğinden alır `DBPROP*` parametresi. Artık, Kimliğine zinciri özelliğine karşı karşılaştırmak mümkündür. Özellik bulunduğunda, `SetProperties` diğer özelliği ile bağlantılı şimdi ayarlanacak özelliği ile adlandırılır. Bu durumda, bir alırsa `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, veya `DBPROP_ORDEREDBOOKMARKS` özelliği, bir ayarlayabilirsiniz `DBPROP_BOOKMARKS` özelliği.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CUtlProps sınıfı](../../data/oledb/cutlprops-class.md)