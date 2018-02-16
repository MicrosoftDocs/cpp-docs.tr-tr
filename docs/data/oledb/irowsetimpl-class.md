---
title: "Irowsetımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetImpl class
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 54b9fd321c4240e9ba02cc63d809a492ffa4d439
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimpl-class"></a>IRowsetImpl Sınıfı
Bir uygulamasını sağlar `IRowset` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*>>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IRowsetImpl`.  
  
 `RowsetInterface`  
 Öğesinden türetilmiş bir sınıf `IRowsetImpl`.  
  
 `RowClass`  
 Depolama birimi için **HROW**.  
  
 `MapClass`  
 Sağlayıcı tarafından tutulan tüm satır işleyicileri için depolama birimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|Bir başvuru sayısı varolan bir satır tanıtıcı ekler.|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|Tarafından çağrılır [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) yeni ayırmak için **HROW**. Doğrudan kullanıcı tarafından adı değil.|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|Satır satır kümesinin kopyadan verileri alır.|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|Belirtilen alan durumunu döndürür.|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|Satırları ardışık olarak önceki konumdan hatırlamak getirir.|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|Oluşturucu. Doğrudan kullanıcı tarafından adı değil.|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|Tarafından çağrılır [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ve [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md). Doğrudan kullanıcı tarafından adı değil.|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|Satır serbest bırakır.|  
|[RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)|Sonraki getirme konumunu ilk konumuna yeniden konumlandırır; diğer bir deyişle, satır ilk kez yüklendiğinde konumuna oluşturulur.|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|Belirtilen alan için durumu bayrakları ayarlar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|Bir sağlayıcı geri getirme destekleyip desteklemediğini belirtir.|  
|[m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|Bir sağlayıcı, imleç kaydırma geriye doğru sahip olup olmadığını gösterir.|  
|[m_bReset](../../data/oledb/irowsetimpl-m-breset.md)|Bir sağlayıcı İmleç konumuna sıfırladı olup olmadığını gösterir. Bu geriye doğru kaydırma veya geriye dönük olarak getirme özel bir anlamı yoktur [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|  
|[m_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|İmleç temsil eden satır kümesi için bir dizin.|  
|[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|Satır işleyicilerini listesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) temel satır kümesi arabirimidir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)