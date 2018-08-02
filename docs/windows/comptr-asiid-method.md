---
title: Comptr::asııd yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1de2bedf9a582d0adbb5b99c9e719327f3b8b90a
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466000"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID Yöntemi
Döndürür bir **ComPtr** belirtilen arabirim kimliği. tarafından belirlenen arabirimi temsil eden nesne  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *riid*  
 Bir arabirim kimliği.  
  
 *p*  
 Nesne Kimliğine eşit bir arabirim varsa *riid*, karakteriyle dolaylı tarafından belirtilen arabirim işaretçisi *riid* parametre; Aksi takdirde, bir işaretçi `IUnknown`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)