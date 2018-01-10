---
title: "Icommandımpl::createrowset | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs: C++
helpviewer_keywords: CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4fecb21b35e3941862cc38edc28a2b1e25ff6bcc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="icommandimplcreaterowset"></a>ICommandImpl::CreateRowset
Tarafından çağrılır [yürütme](../../data/oledb/icommandimpl-execute.md) tek bir satır kümesi oluşturmak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `RowsetClass`  
 Kullanıcının satır kümesi sınıfı temsil eden bir şablon sınıfı üyesi. Genellikle sihirbaz tarafından oluşturulan.  
  
 `pUnkOuter`  
 [in] Bir işaretçi denetleme **IUnknown** satır bir toplama bir parçası olarak oluşturulursa arabirim; Aksi takdirde NULL'dur.  
  
 `riid`  
 [in] Karşılık gelen `riid` içinde `ICommand::Execute`.  
  
 `pParams`  
 [Giriş/Çıkış] Karşılık gelen `pParams` içinde `ICommand::Execute`.  
  
 `pcRowsAffected`  
 Karşılık gelen `pcRowsAffected` içinde `ICommand::Execute`.  
  
 `ppRowset`  
 [Giriş/Çıkış] Karşılık gelen `ppRowset` içinde `ICommand::Execute`.  
  
 `pRowsetObj`  
 [out] Satır kümesi nesnesi için bir işaretçi. Genellikle bu parametre kullanılmaz, ancak bir COM nesnesi geçirmeden önce satır kümesi üzerinde daha fazla iş gerçekleştirmelisiniz değilse kullanılabilir. Yaşam süresi `pRowsetObj` tarafından bağlı `ppRowset`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri. Bkz: `ICommand::Execute` tipik değerleri listesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden fazla satır kümesi oluşturun veya farklı satır kümeleri oluşturmak için kendi koşullar sağlamak amacıyla yerleştirmek için farklı çağrıları `CreateRowset` içinden **yürütme**.  
  
 Bkz: [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) içinde *OLE DB Programcının Başvurusu.*  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICommandImpl Sınıfı](../../data/oledb/icommandimpl-class.md)