---
title: Ierrorrecordsımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0d0425e7765cf09abb870cb39720cf43c8c74174
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105471"
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
|[Geterrorguıd](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|GUID hata bir hata kayıttan alır.|  
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