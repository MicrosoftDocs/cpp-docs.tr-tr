---
title: ComPtr::operator Microsoft::WRL::Details::BoolType işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a4ec737c3f24899e50220c3e862283b88a826b9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461170"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType İşleci
Belirtir olup olmadığını bir **ComPtr** bir arabirimin nesne ömrü yönetimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir arabirim ile ilişkili ise **ComPtr**, adresini [BoolStruct::Member](../windows/boolstruct-member-data-member.md) veri üyesi; Aksi takdirde **nullptr**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr sınıfı](../windows/comptr-class.md)   
 [ComPtr::Get Metodu](../windows/comptr-get-method.md)