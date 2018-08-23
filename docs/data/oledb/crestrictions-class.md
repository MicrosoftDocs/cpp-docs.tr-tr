---
title: CRestrictions sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b9dc35df928d53d7d5ca5d833db8e87c96e1c7f4
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465182"
---
# <a name="crestrictions-class"></a>CRestrictions Sınıfı
Şema satır kümeleri için kısıtlamaları belirlemenizi sağlayan genel bir sınıf.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, short nRestrictions, const GUID* pguid>  
class CRestrictions : 
   public CSchemaRowset <T, nRestrictions>  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Erişimci için kullanılan sınıf.  
  
 *nRestrictions*  
 Şema satır kümesi için kısıtlama sütun sayısı.  
  
 *pguid*  
 GUID şema için bir işaretçi.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h 
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[açın](#open)|Kullanıcı tarafından sağlanan kısıtlamalar göre bir sonuç döndürür.|   

## <a name="open"></a> CRestrictions::Open
Kullanıcı tarafından sağlanan kısıtlamalar göre bir sonuç döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Oturumu*  
 [in] Veri kaynağına bağlanmak için kullanılan var olan bir oturum nesnesi olarak belirtir.  
  
 *lpszParam*  
 [in] Şema satır kümesi kısıtlamaları belirtir.  
  
 *bBind*  
 [in] Sütun eşlemesi otomatik olarak bağlamak belirtir. Varsayılan değer **true**, otomatik olarak bağlanacak sütun eşlemesi neden olur. Ayarı *bBind* için **false** el ile bağlayabilirsiniz böylece sütun eşlemesi otomatik bağlama engeller. (El ile OLAP kullanıcılara belirli ilgilenilen bağlamadır.)  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Şema satır kümesinde en fazla yedi kısıtlamaları belirtebilirsiniz.  
  
 Bkz: [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) her şeması satır kümesi tanımlanmış kısıtlamalar hakkında bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)    
 [Şema Satır Kümesi Sınıfları ve Typedef Sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)