---
title: CRowsetImpl::GetColumnInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a989b31d672c9019d2ed5e61490f4e0042ab4c47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096473"
---
# <a name="crowsetimplgetcolumninfo"></a>CRowsetImpl::GetColumnInfo
Belirli bir istemci isteği için sütun bilgileri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,  
   ULONG* pcCols);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pv`  
 [in] Kullanıcının bir işaretçi `CRowsetImpl` türetilmiş sınıf.  
  
 `pcCols`  
 [in] \(Sayıya çıktı) bir işaretçi sütun döndürdü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir statik **ATLCOLUMNINFO** yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, Gelişmiş bir geçersiz kılma kullanılır.  
  
 Bu yöntem, belirli bir istemci isteği için sütun bilgileri almak için birkaç temel uygulamayı sınıflar tarafından çağrılır. Genellikle, bu yöntemin çağrılması `IColumnsInfoImpl`. Bu yöntemi geçersiz kılarsanız yönteminde sürümü yerleştirmeniz gerekir, `CRowsetImpl`-türetilmiş sınıf. Şablonlaştırılmış olmayan bir sınıfta yöntemi konup çünkü değiştirmelisiniz `pv` uygun `CRowsetImpl`-türetilmiş sınıf.  
  
 Aşağıdaki örnekte gösterilmiştir **GetColumnInfo'nın** kullanımı. Bu örnekte, **CMyRowset** olan bir `CRowsetImpl`-türetilmiş sınıf. Geçersiz kılmak için `GetColumnInfo` bu sınıfın tüm örnekleri için aşağıdaki yöntemi yerleştirin **CMyRowset** sınıf tanımı:  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowsetImpl Sınıfı](../../data/oledb/crowsetimpl-class.md)