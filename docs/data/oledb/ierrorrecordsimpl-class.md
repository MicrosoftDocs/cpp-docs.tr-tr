---
title: "Ierrorrecordsımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e69db8c89a60b7dee543bbdf87997514ba5f0cd7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl Sınıfı
OLE DB uygulayan [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) kayıtları ekleme ve veri üyeden kayıtları almak arabirimi ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) türü **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden türetilmiş bir sınıf `IErrorRecordsImpl`.  
  
 `RecordClass`  
 OLE DB hata nesneyi temsil eden sınıf.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Hata açıklama dizesi bir hata kayıttan alır.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|GUID hata bir hata kayıttan alır.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Yardım içerik kimliği bir hata kayıttan alır.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Yardım dosyasının tam yol adı bir hata kayıttan alır.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Hata kaynak kodu bir hata kayıttan alır.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|Bir kayıt için OLE DB hata nesnesi ekler.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Dönüş kodu ve sağlayıcıya özgü hata numarası gibi hata ile ilgili temel bilgileri döndürür.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Bir işaretçi bir arabirim için bir özel hata nesnesi döndürür.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Döndürür bir [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) belirtilen kayıt arabirimi işaretçisi.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Hata parametrelerini döndürür.|  
|[GetRecordCount](../../mfc/reference/cdaorecordset-class.md#getrecordcount)|OLE DB kayıt nesnesinde kayıt sayısını döndürür.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|Hata kaydı dizisi.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)