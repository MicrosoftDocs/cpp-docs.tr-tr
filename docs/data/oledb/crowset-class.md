---
title: CRowset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>
- CRowset
- ATL::CRowset
- ATL::CRowset<TAccessor>
- ATL.CRowset
dev_langs:
- C++
helpviewer_keywords:
- CRowset class
ms.assetid: b0228a90-b8dd-47cc-b397-8d4c15c1e7f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5c9a23c2e879f0d2fe1add1a970c64f6fbcc27b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="crowset-class"></a>CRowset Sınıfı
OLE DB satır kümesi nesnesi ve birkaç ilgili yalıtır arabirimleri ve satır kümesi veri işleme yöntemlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CAccessorBase>  
class CRowset  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Bir erişimci sınıfı. Varsayılan, `CAccessorBase` değeridir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/crowset-addrefrows.md)|Artışlarla başvuru sayısı geçerli satır ile ilişkilendirilmiş.|  
|[Kapat](../../data/oledb/crowset-close.md)|Satır ve geçerli serbest `IRowset` arabirimi.|  
|[Karşılaştırma](../../data/oledb/crowset-compare.md)|Karşılaştırır iki yer işaret kullanarak [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).|  
|[CRowset](../../data/oledb/crowset-crowset.md)|Yeni bir `CRowset` nesne ve (isteğe bağlı olarak) ile ilişkilendirir bir **IRowset** parametre olarak sağlanan arabirim.|  
|[Sil](../../data/oledb/crowset-delete.md)|Satır kümesi kullanımından satırları siler [IRowsetChange:DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx).|  
|[FindNextRow](../../data/oledb/crowset-findnextrow.md)|Sonraki eşleşen satır sonra belirtilen yer işareti bulur.|  
|[GetApproximatePosition](../../data/oledb/crowset-getapproximateposition.md)|Yaklaşık bir yer işaretine karşılık gelen bir satır konumunu döndürür.|  
|[GetData](../../data/oledb/crowset-getdata.md)|Satır satır kümesinin kopyadan verileri alır.|  
|[GetDataHere](../../data/oledb/crowset-getdatahere.md)|Verileri belirtilen arabelleğinden alır.|  
|[GetOriginalData](../../data/oledb/crowset-getoriginaldata.md)|En son öğesinden alınan veya bekleyen değişiklikleri yoksayılıyor veri kaynağına aktarılan verileri alır.|  
|[GetRowStatus](../../data/oledb/crowset-getrowstatus.md)|Tüm satırları durumunu döndürür.|  
|[Ekle](../../data/oledb/crowset-insert.md)|Oluşturur ve kullanarak yeni bir satır ekler [IRowsetChange:InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx).|  
|[Issamerow](../../data/oledb/crowset-issamerow.md)|Geçerli satır belirtilen satır karşılaştırır.|  
|[MoveFirst](../../data/oledb/crowset-movefirst.md)|Sonraki getirme konumunu ilk konumuna yeniden konumlandırır.|  
|[MoveLast](../../data/oledb/crowset-movelast.md)|Son kayıt taşır.|  
|[MoveNext](../../data/oledb/crowset-movenext.md)|Bir sonraki sıralı satır veya sonraki satıra ötesinde konumlar belirtilen sayıda gelen verileri getirir.|  
|[MovePrev](../../data/oledb/crowset-moveprev.md)|Önceki kaydın taşır.|  
|[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)|Yer işareti tarafından işaretlenen satırı veya belirtilen kayma satırındaki bu yer işaretinin getirir.|  
|[MoveToRatio](../../data/oledb/crowset-movetoratio.md)|Satır satır kümesindeki bir kesir konumundan başlayarak getirir.|  
|[ReleaseRows](../../data/oledb/crowset-releaserows.md)|Çağrıları [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) geçerli satır tanıtıcısı serbest bırakmak için.|  
|[SetData](../../data/oledb/crowset-setdata.md)|Veri değerlerini kullanarak bir satır, bir veya daha fazla sütun ayarlar [IRowsetChange:SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx).|  
|[Geri alma](../../data/oledb/crowset-undo.md)|Bir satır için son fetch itibaren yapılan tüm değişiklikler geri alır veya [güncelleştirme](../../data/oledb/crowset-update.md).|  
|[Güncelleştir](../../data/oledb/crowset-update.md)|Bekleyen tüm geçerli satırda son getirme veya güncelleştirme yaptığınız değişiklikleri iletir.|  
|[UpdateAll](../../data/oledb/crowset-updateall.md)|Bekleyen tüm satırları son getirme veya güncelleştirme yapılan değişiklikler iletir.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE DB'de satır içinden, bir program ayarlar'ı ve verileri alır nesnesidir.  
  
 Bu sınıf örneği ancak bunun yerine bir şablon parametre olarak geçirilen değiştirilmemelidir `CTable` veya `CCommand` (`CRowset` varsayılandır).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DBVIEWER örneği](../../visual-cpp-samples.md)   
 [MultiRead örnek](../../visual-cpp-samples.md)   
 [Örnek multiRead öznitelikleri](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)