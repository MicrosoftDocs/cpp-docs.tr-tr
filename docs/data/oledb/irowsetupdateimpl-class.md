---
title: IRowsetUpdateImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34efd252f67a0e3da9827ef97cff8bcab0a45532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl Sınıfı
OLE DB Şablonları uyarlamasını [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  

class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden türetilmiş bir sınıf `IRowsetUpdateImpl`.  
  
 `Storage`  
 Kullanıcı kaydı.  
  
 `UpdateArray`  
 Satır kümesi güncelleştirmek için önbelleğe alınan veriler içeren bir dizi.  
  
 `RowClass`  
 Depolama birimi için **HROW**.  
  
 `MapClass`  
 Sağlayıcı tarafından tutulan tüm satır işleyicilerini depolama birimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Arabirim yöntemleri (IRowsetChange ile kullanılır)  
  
|||  
|-|-|  
|[SetData](../../data/oledb/irowsetupdateimpl-setdata.md)|Bir veya daha fazla sütun veri değerlerini ayarlar.|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>Arabirim yöntemleri (IRowsetUpdate ile kullanılır)  
  
|||  
|-|-|  
|[GetOriginalData](../../data/oledb/irowsetupdateimpl-getoriginaldata.md)|En son için iletilen veya bekleyen değişiklikleri yoksayılıyor veri kaynağından alınan veriler alır.|  
|[GetPendingRows](../../data/oledb/irowsetupdateimpl-getpendingrows.md)|Satırları bekleyen değişiklikler listesini döndürür.|  
|[GetRowStatus](../../data/oledb/irowsetupdateimpl-getrowstatus.md)|Belirtilen satır durumunu döndürür.|  
|[Geri alma](../../data/oledb/irowsetupdateimpl-undo.md)|Son getirme veya güncelleştirme satır değişiklikleri geri alır.|  
|[Güncelleştir](../../data/oledb/irowsetupdateimpl-update.md)|Satırın son getirme veya güncelleştirme yapılan değişiklikler iletir.|  
  
### <a name="implementation-methods-callback"></a>Uygulama yöntemleri (geri arama)  
  
|||  
|-|-|  
|[Isupdateallowed](../../data/oledb/irowsetupdateimpl-isupdateallowed.md)|Güvenlik için bütünlük ve benzeri güncelleştirmeleri izin vermeden önce denetlemek için kullanılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_mapCachedData](../../data/oledb/irowsetupdateimpl-m-mapcacheddata.md)|Ertelenmiş işlemi için orijinal verilerini içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 İlk okuyup belgelerine anlamanız [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx), her şeyi var. açıklanan de burada geçerlidir. Bölüm 6 okumanız gereken *OLE DB Programcının Başvurusu* veri ayarlama.  
  
 `IRowsetUpdateImpl` OLE DB uygulayan `IRowsetUpdate` yapılan değişikliklerle iletimini gecikme tüketicileri sağlayan arabirim `IRowsetChange` için veri kaynağı ve iletimden önce değişiklikleri geri almak.  
  
> [!IMPORTANT]
>  Sağlayıcınız uygulamak denemeden önce aşağıdaki belgeleri okuyun önerilir:  
  
-   [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Bölüm 6'da *OLE DB Programcının Başvurusu*  
  
-   Ayrıca bkz. nasıl `RUpdateRowset` UpdatePV örnekte kullanılan sınıf  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)