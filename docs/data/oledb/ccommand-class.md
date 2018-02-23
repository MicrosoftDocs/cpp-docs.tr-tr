---
title: "CCommand sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
dev_langs:
- C++
helpviewer_keywords:
- CCommand class
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5ec786bff30745a986ecc643cd42f0d8975b0ccf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ccommand-class"></a>CCommand Sınıfı
Ayarlama ve bir komut yürütmek için yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CNoAccessor,  
          template <typename T> class TRowset = CRowset,  
          class TMultiple = CNoMultipleResults>  
class CCommand :   
           public CAccessorRowset <TAccessor, TRowset>,  
           public CCommandBase,  
           public TMultiple  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TAccessor`  
 Erişimci sınıfı tür (gibi `CDynamicParameterAccessor`, `CDynamicStringAccessor`, veya `CEnumeratorAccessor`) kullanmak için komutu istiyor. Varsayılan değer `CNoAccessor`, sınıf desteklemez parametreleri veya çıkış sütunları olduğunu belirtir.  
  
 `TRowset`  
 Satır kümesi sınıfı tür (gibi `CArrayRowset` veya `CNoRowset`) komutunu kullanmak istiyor. Varsayılan, `CRowset` değeridir.  
  
 `TMultiple`  
 Birden çok sonuç döndüren bir OLE DB komutu kullanmak için [CMultipleResults](../../data/oledb/cmultipleresults-class.md). Aksi takdirde kullanın [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Ayrıntılar için bkz [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx).  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Kapat](../../data/oledb/ccommand-close.md)|Geçerli komutu kapatır.|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|Birden çok sonuç kullanarak ayarladığında sonraki sonuç getirir.|  
|[Açık](../../data/oledb/ccommand-open.md)|Yürütür ve isteğe bağlı olarak komut bağlar.|  
  
### <a name="inherited-methods"></a>Devralınan yöntemleri  
  
|||  
|-|-|  
|[Oluşturma](../../data/oledb/ccommand-create.md)|Belirtilen oturumu için yeni bir komut oluşturur ve ardından komut metni ayarlar.|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|Yeni bir komut oluşturur.|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|Komut parametreleri, adlarını ve türlerini listesini alır.|  
|[Hazırlama](../../data/oledb/ccommand-prepare.md)|Doğrular ve geçerli komutu en iyi duruma getirir.|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|Gerekirse, parametre erişimcisi serbest bırakır ve ardından komut serbest bırakır.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|Her komut parametresi yerel türünü belirtir.|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|Geçerli komut yürütme planı atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre tabanlı işlemi gerçekleştirin veya bir komut yürütün gerektiğinde bu sınıfı kullanın. Yalnızca basit bir satır kümesinde açmak gerekiyorsa kullanın [CTable](../../data/oledb/ctable-class.md) yerine.  
  
 Kullanmakta olduğunuz erişimci sınıfı parametre ve veri bağlama yöntemini belirler.  
  
 Saklı yordamlar (yalnızca sabitleri sorgu dizelerine izin verilir), sağlayıcıyı desteklemiyor saklı yordamları OLE DB sağlayıcısı ile Jet için kullanamazsınız, çünkü olduğunu unutmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)