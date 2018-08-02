---
title: ComPtr::ReleaseAndGetAddressOf yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d55241ddefce0e4fcd7f72698779d6e4ec97e20
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464999"
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf Yöntemi
Şununla ilişkili arabirimini yayımlar **ComPtr** ve adresini alır. [ptr_](../windows/comptr-ptr-data-member.md) yayımlanan arabirimi için bir işaretçi içeren veri üyesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Adresini [ptr_](../windows/comptr-ptr-data-member.md) veri üyesi bu **ComPtr**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr sınıfı](../windows/comptr-class.md)   
 [ComPtr::ptr_ Veri Üyesi](../windows/comptr-ptr-data-member.md)