---
title: CRestrictions::Open | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbb0b175a6fa5a6cf93b4fe107884d5bb84f2487
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crestrictionsopen"></a>CRestrictions::Open
Kullanıcı tarafından sağlanan göre sınırlamalar bir sonuç döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `session`  
 [in] Veri kaynağına bağlanmak için kullanılan var olan bir oturum nesnesi belirtir.  
  
 *lpszParam*  
 [in] Şema satır kümesi kısıtlamaları belirtir.  
  
 `bBind`  
 [in] Sütun eşlemesi otomatik olarak bağlamak belirtir. Varsayılan değer **doğru**, otomatik olarak bağlanacak sütun eşlemesi neden olur. Ayarı `bBind` için **false** böylece el ile bağlayabilirsiniz sütun eşlemesi otomatik bağlama engeller. (El ile bağlama belirli OLAP kullanıcılara ilgilendirir.)  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Şema satır kümesinde en fazla yedi kısıtlamaları belirtebilirsiniz.  
  
 Bkz: [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) her şeması satır kümesi tanımlı kısıtlamalar hakkında bilgi için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions sınıfı](../../data/oledb/crestrictions-class.md)   
 [Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)