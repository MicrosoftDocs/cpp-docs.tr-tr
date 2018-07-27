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
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
- ATL.IRowsetUpdateImpl.GetRowStatus
- IRowsetUpdateImpl::GetRowStatus
- IRowsetUpdateImpl.GetRowStatus
- ATL::IRowsetUpdateImpl::GetRowStatus
- GetRowStatus
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
- SetData method
- GetOriginalData method
- GetPendingRows method
- GetRowStatus method
- Undo method
- Update method
- IsUpdateAllowed method
- m_mapCachedData
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d58709e9a2b5bd86102e8323456c6bf9ca72fa1
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322143"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl Sınıfı
OLE DB Şablonları uygulamasının [IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx) arabirimi.  
  
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
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Öğesinden türetilen bir sınıf `IRowsetUpdateImpl`.  
  
 *Depolama*  
 Kullanıcı kayıt.  
  
 *UpdateArray*  
 Satır kümesini güncelleştirmek için önbelleğe alınmış verileri içeren bir dizi.  
  
 *RowClass*  
 Depolama birimi için `HROW`.  
  
 *MapClass*  
 Sağlayıcı tarafından tutulan tüm olan satır işleyicilerini depolama birimi.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Arabirim yöntemleri (IRowsetChange ile kullanılır)  
  
|||  
|-|-|  
|[SetData](#setdata)|Bir veya daha fazla sütun veri değerlerini ayarlar.|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>Arabirim yöntemleri (IRowsetUpdate ile kullanılır)  
  
|||  
|-|-|  
|[GetOriginalData](#getoriginaldata)|En son için iletilen veya bekleyen değişiklikleri yoksayma veri kaynağından alınan verileri alır.|  
|[GetPendingRows](#getpendingrows)|Satırları bekleyen değişiklikler listesi döndürür.|  
|[GetRowStatus](#getrowstatus)|Belirtilen satırları durumunu döndürür.|  
|[Geri alma](#undo)|Herhangi bir değişiklik satırın son getirme veya güncelleştirme iptal eder.|  
|[Güncelleştir](#update)|Satırın son getirme veya güncelleştirme yapılan değişiklikleri iletir.|  
  
### <a name="implementation-methods-callback"></a>Uygulama yöntemlerinin (geri çağırma)  
  
|||  
|-|-|  
|[Isupdateallowed](#isupdateallowed)|Güncelleştirmeleri izin vermeden önce vb. güvenlik için bütünlüğünü denetlemek için kullanılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_mapCachedData](#mapcacheddata)|Ertelenmiş işlem için özgün veriler içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Önce okumanız ve belgelerine anlamanız [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx), burada açıklanan her şeyin de burada geçerlidir. Bölüm 6 de okumalıdır *OLE DB Programcının Başvurusu* veri ayarlama.  
  
 `IRowsetUpdateImpl` OLE DB uygulayan `IRowsetUpdate` yapılan değişikliklerle iletimini gecikme tüketiciler sağlayan arabirimi `IRowsetChange` için veri kaynağını seçin ve iletimden önce değişiklikleri geri al.  
  
> [!IMPORTANT]
>  Sağlayıcınız uygulamak denemeden önce aşağıdaki belgeleri okumanız önemle tavsiye edilir:  
  
-   [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Bölüm 6 *OLE DB Programcının Başvurusu*  
  
-   Ayrıca bkz: nasıl `RUpdateRowset` UpdatePV örnekte kullanılan sınıf  

## <a name="setdata"></a> IRowsetUpdateImpl::SetData
Bir veya daha fazla sütun veri değerlerini ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetChange::SetData](https://msdn.microsoft.com/library/ms721232.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu metot geçersiz kılmaları [IRowsetChangeImpl::SetData](../../data/oledb/irowsetchangeimpl-setdata.md) yöntemi içerir ancak önbelleğe alma işlemi hemen veya ertelenmiş işlenmesini izin vermek için özgün veriler.

## <a name="getoriginaldata"></a> IRowsetUpdateImpl::getoriginaldata
En son için iletilen veya bekleyen değişiklikleri yoksayma veri kaynağından alınan verileri alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (GetOriginalData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pData);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/library/ms709947.aspx) içinde *OLE DB Programcının Başvurusu*.   

## <a name="getpendingrows"></a> IRowsetUpdateImpl::getpendingrows
Satırları bekleyen değişiklikler listesi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hReserved*  
 [in] Karşılık gelen *hChapter* parametresinde [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx).  
  
 Diğer parametreler için bkz: [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx) içinde *OLE DB Programcının Başvurusu*.  

## <a name="getrowstatus"></a> IRowsetUpdateImpl::getrowstatus
Belirtilen satırları durumunu döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBPENDINGSTATUS rgPendingStatus[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hReserved*  
 [in] Karşılık gelen *hChapter* parametresinde [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx).  
  
 Diğer parametreler için bkz: [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx) içinde *OLE DB Programcının Başvurusu*.  

## <a name="undo"></a> IRowsetUpdateImpl::Undo
Herhangi bir değişiklik satırın son getirme veya güncelleştirme iptal eder.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (Undo )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hReserved*  
 [in] Karşılık gelen *hChapter* parametresinde [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 *pcRowsUndone*  
 [out] Karşılık gelen *pcRows* parametresinde [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 *prgRowsUndone*  
 [in] Karşılık gelen *prgRows* parametresinde [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 Diğer parametreler için bkz: [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx) içinde *OLE DB Programcının Başvurusu*. 

## <a name="update"></a> IRowsetUpdateImpl::Update
Satırın son getirme veya güncelleştirme yapılan değişiklikleri iletir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hReserved*  
 [in] Karşılık gelen *hChapter* parametresinde [IRowsetUpdate::Update](https://msdn.microsoft.com/library/ms719709.aspx).  
  
 Diğer parametreler için bkz: [IRowsetUpdate::Update](https://msdn.microsoft.com/library/ms719709.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Değişiklikleri çağırarak aktarılır [IRowsetChangeImpl::flushdata](../../data/oledb/irowsetchangeimpl-flushdata.md). Tüketici çağırmalıdır [CRowset::Update](../../data/oledb/crowset-update.md) değişikliklerin etkili olması. Ayarlama *prgRowstatus* açıklandığı gibi uygun bir değere [satır durumları](https://msdn.microsoft.com/library/ms722752.aspx) içinde *OLE DB Programcının Başvurusu*. 
  
## <a name="isupdateallowed"></a> IRowsetUpdateImpl::ısupdateallowed
Güvenlik güncelleştirmeleri ve benzeri önce bütünlüğünü denetlemek için bu yöntemi yok sayın.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Durumu*  
 [in] Bekleyen işlemler satırlarda durumu.  
  
 *hRowUpdate*  
 [in] Satırları güncelleştirmek için kullanıcının istediği işleyin.  
  
 *pRowStatus*  
 [out] Kullanıcı tarafından döndürülen durum.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir güncelleştirme izin verilmesi gerektiğini belirlerseniz, S_OK döndürür; Aksi takdirde E_FAIL döndürür. Bir güncelleştirme izin verirseniz, ayrıca ayarlamanız gerekir `DBROWSTATUS` içinde [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) uygun bir [satır durumu](https://msdn.microsoft.com/library/ms722752.aspx).  

## <a name="mapcacheddata"></a> IRowsetUpdateImpl::m_mapcacheddata
Ertelenmiş işlem için özgün veriler içeren bir harita.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hRow*  
 Veri satırları için işleyin.  
  
 *pData*  
 Önbelleğe alınacak veri için bir işaretçi. Veri türünde *depolama* (kullanıcı kayıt sınıfı). Bkz: *depolama* şablon bağımsız değişkeni [IRowsetUpdateImpl sınıfı](../../data/oledb/irowsetupdateimpl-class.md).  

## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)
