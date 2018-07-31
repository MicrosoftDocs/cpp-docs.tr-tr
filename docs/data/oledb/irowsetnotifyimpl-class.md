---
title: IRowsetNotifyImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a20be1a92c93be38d901f58339bb02b24cf2661f
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339961"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl Sınıfı
Uygular ve kayıtları [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx) Tüketici (diğer adıyla "havuz") bildirimleri işleyebilmeniz.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[OnFieldChange](#onfieldchange)|Bir sütunun değeri herhangi bir değişiklik tüketicisinin bildirir.|  
|[OnRowChange](#onrowchange)|İlk değişiklik bir satır veya satırın tamamını etkileyen herhangi bir değişiklik tüketici bildirir.|  
|[OnRowsetChange](#onrowsetchange)|Tüm satır kümesini etkileyen herhangi bir değişiklik tüketicisinin bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [bildirimleri alma](../../data/oledb/receiving-notifications.md) tüketici üzerinde bağlantı noktası arabirimini uygulayan hakkında.  
  
 `IRowsetNotifyImpl` işlevsiz bir uygulamasını sağlar `IRowsetNotify`, için boş işlevlerle `IRowsetNotify` yöntemleri [OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx), ve [OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx). Varsa, uyguladığınızda bu sınıftan devralınan bir `IRowsetNotify` arabirimi, yalnızca gereksinim duyduğunuz yöntemleri uygulayabilirsiniz. Ayrıca diğer yöntemler için boş uygulamaları kendiniz vermeniz gerekir.  

## <a name="onfieldchange"></a> IRowsetNotifyImpl::onfieldchange
Bir sütunun değeri herhangi bir değişiklik tüketicisinin bildirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) parametre açıklamaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bkz: [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) dönüş değeri açıklamaları.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sarmalar [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.  

## <a name="onrowchange"></a> IRowsetNotifyImpl::onrowchange
İlk değişiklik bir satır veya satırın tamamını etkileyen herhangi bir değişiklik tüketici bildirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx) parametre açıklamaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bkz: [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx) dönüş değeri açıklamaları.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sarmalar [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın. 

## <a name="onrowsetchange"></a> IRowsetNotifyImpl::onrowsetchange
Tüm satır kümesini etkileyen herhangi bir değişiklik tüketicisinin bildirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) parametre açıklamaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bkz: [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) dönüş değeri açıklamaları.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sarmalar [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) yöntemi. Ayrıntılar için OLE DB Programcı Başvurusu bu yöntemin tanımı bakın.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx)   
 [IRowsetNotifyCP Sınıfı](../../data/oledb/irowsetnotifycp-class.md)