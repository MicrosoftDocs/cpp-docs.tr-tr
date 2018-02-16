---
title: CDBPropSet::AddProperty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
dev_langs:
- C++
helpviewer_keywords:
- AddProperty method
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d71e3e2b86c631cc2e9d0a3516c46cb418737d7b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdbpropsetaddproperty"></a>CDBPropSet::AddProperty
Bir özellik için özellik kümesi ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
bool AddProperty(DWORD dwPropertyID,   
   constVARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *dwPropertyID*  
 [in] Eklenecek özellik kimliği. Başlatmak için kullanılan **dwPropertyID** , `DBPROP` yapısı özellik kümesine eklenir.  
  
 `var`  
 [in] Özellik değeri başlatmak için kullanılan bir değişken `DBPROP` yapısı özellik kümesine eklenir.  
  
 `szValue`  
 [in] Özellik değeri başlatmak için kullanılan bir dize `DBPROP` yapısı özellik kümesine eklenir.  
  
 `bValue`  
 [in] A **bayt** veya boolean değeri için özellik değeri başlatmak için kullanılan `DBPROP` yapısı özellik kümesine eklenir.  
  
 `nValue`  
 [in] Özellik değeri başlatmak için kullanılan bir tamsayı değeri `DBPROP` yapısı özellik kümesine eklenir.  
  
 *fltValue*  
 [in] Özellik değeri başlatmak için kullanılan bir kayan nokta değer `DBPROP` yapısı özellik kümesine eklenir.  
  
 `dblValue`  
 [in] Özellik değeri başlatmak için kullanılan bir çift duyarlıklı kayan noktalı değeri `DBPROP` yapısı özellik kümesine eklenir.  
  
 `cyValue`  
 [in] Özellik değeri başlatmak için kullanılan CY para birimi değeri `DBPROP` yapısı özellik kümesine eklenir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** özelliği başarıyla eklenmişse. Aksi takdirde, **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDBPropSet sınıfı](../../data/oledb/cdbpropset-class.md)   
 [DBPROP yapısı](https://msdn.microsoft.com/en-us/library/ms717970.aspx)