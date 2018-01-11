---
title: CRowset::Compare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset<TAccessor>.Compare
- CRowset<TAccessor>::Compare
- ATL.CRowset<TAccessor>.Compare
- ATL::CRowset<TAccessor>::Compare
- CRowset.Compare
- ATL::CRowset::Compare
- ATL.CRowset.Compare
- CRowset::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: a8117b40-7abd-4867-b0ba-eb9e9808204e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9d7e69c168489fcfe71c14fbbfe2b2aca8e28f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetcompare"></a>CRowset::Compare
Karşılaştırır iki yer işaret kullanarak [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT Compare(   
   const CBookmarkBase& bookmark1,   
   const CBookmarkBase& bookmark2,   
   DBCOMPARE* pComparison    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Bookmark1*  
 [in] Karşılaştırma yapılacak ilk yer işareti.  
  
 *Bookmark2*  
 [in] Karşılaştırılacak ikinci yer işareti.  
  
 `pComparison`  
 [out] Karşılaştırmanın sonucu için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem isteğe bağlı bir arabirim gerektirir `IRowsetLocate`, hangi desteklenmeyebilir tüm sağlayıcılarının; bu durumda, yöntem **E_NOINTERFACE**. De ayarlamalısınız **DBPROP_IRowsetLocate** için `VARIANT_TRUE` çağırmadan önce **açık** tablodaki veya satır kümesi içeren komutu.  
  
 Tüketici yer işaretlerini kullanma hakkında daha fazla bilgi için bkz: [kullanarak yer işaretleri](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset Sınıfı](../../data/oledb/crowset-class.md)