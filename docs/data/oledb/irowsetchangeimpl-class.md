---
title: "IRowsetChangeImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
dev_langs: C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4dc31fc66f28f6fd9a8d9e9bc7122bf2aa7b2b73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl Sınıfı
OLE DB Şablonları uyarlamasını [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) OLE DB belirtiminde arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >   
>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden türetilmiş bir sınıf `IRowsetChangeImpl`.  
  
 `Storage`  
 Kullanıcı kaydı.  
  
 `BaseInterface`  
 Taban sınıf arabirim için gibi `IRowsetChange`.  
  
 `RowClass`  
 Satır tanıtıcısı depolama birimi.  
  
 `MapClass`  
 Sağlayıcı tarafından tutulan tüm satır işleyicilerini depolama birimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Arabirim yöntemleri (IRowsetChange ile kullanılır)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|Satır satır kümesinden siler.|  
|[Insertrow](../../data/oledb/irowsetchangeimpl-insertrow.md)|Satır kümesine bir satır ekler.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|Bir veya daha fazla sütun veri değerlerini ayarlar.|  
  
### <a name="implementation-method-callback"></a>Uygulama yöntemi (geri arama)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|Verileri, depolama alanına kaydetmeye sağlayıcısı tarafından Overidden.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, bir veri deposu anında yazma işlemlerinin sorumludur. "Hemen" anlamına gelir (tüketici kullanan kişi) son kullanıcı herhangi bir değişiklik yaptığında, bu değişiklikleri hemen verilere iletilirken depolamak (ve geri alınamaz).  
  
 `IRowsetChangeImpl`OLE DB uygulayan `IRowsetChange` satırları silme ve yeni satırlar ekleme varolan satırları, sütunları değerlerinin güncelleştirme sağlayan arabirim.  
  
 OLE DB Şablonları uygulaması tüm taban yöntemi destekler (`SetData`, `InsertRow`, ve `DeleteRows`).  
  
> [!IMPORTANT]
>  Sağlayıcınız uygulamak denemeden önce aşağıdaki belgeleri okuyun önerilir:  
  
-   [Güncelleştirilebilir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Bölüm 6'da *OLE DB Programcının Başvurusu*  
  
-   Ayrıca bkz. nasıl `RUpdateRowset` UpdatePV örnekte kullanılan sınıf  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)