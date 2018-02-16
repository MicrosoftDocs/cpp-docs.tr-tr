---
title: "Icommandımpl::createrowset | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 45fcb53c6412f91c35ea26a5e7a732f5de2d3fcc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimplcreaterowset"></a>ICommandImpl::CreateRowset
Tarafından çağrılır [yürütme](../../data/oledb/icommandimpl-execute.md) tek bir satır kümesi oluşturmak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
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