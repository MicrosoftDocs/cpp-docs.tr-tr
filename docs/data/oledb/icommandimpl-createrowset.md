---
title: Icommandımpl::createrowset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6909f8f6825aacf55c000bfd87e0282365180559
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100648"
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