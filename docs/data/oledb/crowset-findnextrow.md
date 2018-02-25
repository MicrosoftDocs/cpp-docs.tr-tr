---
title: CRowset::FindNextRow | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CRowset.FindNextRow
- CRowset<TAccessor>.FindNextRow
- ATL::CRowset::FindNextRow
- CRowset::FindNextRow
- CRowset<TAccessor>::FindNextRow
- CRowset.FindNextRow
- ATL.CRowset<TAccessor>.FindNextRow
- ATL::CRowset<TAccessor>::FindNextRow
- FindNextRow
dev_langs:
- C++
helpviewer_keywords:
- FindNextRow method
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3808666693d9a134d6ebcf12333c090cb2ff8ba3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetfindnextrow"></a>CRowset::FindNextRow
Sonraki eşleşen satır sonra belirtilen yer işareti bulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT FindNextRow(DBCOMPAREOP op,   
  BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `op`  
 [in] Satır değerleri karşılaştırma kullanmak için işlem. Değerleri için bkz: [IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx).  
  
 `pData`  
 [in] Eşleştirilecek değeri için bir işaretçi.  
  
 `wType`  
 [in] Arabellek değer bölümünü veri türünü belirtir. Türü göstergeleri hakkında daha fazla bilgi için bkz: [veri türleri](https://msdn.microsoft.com/en-us/library/ms723969.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK'sındaki.  
  
 `nLength`  
 [in] , Bayt cinsinden uzunluğu, veri değeri ayrılmış tüketici veri yapısı. Açıklamasını Ayrıntılar için bkz **cbMaxLen** içinde [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/en-us/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu.*  
  
 `bPrecision`  
 [in] Veri alınırken kullanılan en yüksek duyarlık. Kullanılan eksikse `wType` olan `DBTYPE_NUMERIC`. Daha fazla bilgi için bkz: [DBTYPE_NUMERIC veya DBTYPE_DECIMAL içeren dönüşümleri](https://msdn.microsoft.com/en-us/library/ms719714.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 `bScale`  
 [in] Veri alırken kullanılan ölçeği. Kullanılan eksikse `wType` olan `DBTYPE_NUMERIC` veya **DBTYPE_DECIMAL**. Daha fazla bilgi için bkz: [DBTYPE_NUMERIC veya DBTYPE_DECIMAL içeren dönüşümleri](https://msdn.microsoft.com/en-us/library/ms719714.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *bSkipCurrent*  
 [in] Bir arama başlatılacağı yer işareti satırları sayısı.  
  
 `pBookmark`  
 [in] Bir arama başlatılacağı konumunun yer işareti.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem isteğe bağlı bir arabirim gerektirir **IRowsetFind**, hangi desteklenmeyebilir tüm sağlayıcılarının; bu durumda, yöntem **E_NOINTERFACE**. De ayarlamalısınız **DBPROP_IRowsetFind** için `VARIANT_TRUE` çağırmadan önce **açık** tablodaki veya satır kümesi içeren komutu.  
  
 Tüketici yer işaretlerini kullanma hakkında daha fazla bilgi için bkz: [kullanarak yer işaretleri](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/en-us/library/ms716845.aspx)