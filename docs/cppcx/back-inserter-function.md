---
title: back_inserter işlevi | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
dev_langs:
- C++
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6142255c00d9764e4a1a18dab094899b5e9d9e1d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767253"
---
# <a name="backinserter-function"></a>back_inserter işlevi
Belirli bir koleksiyondaki sonunda öğe eklemek için kullanılan bir yineleyici döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template <typename T>
Platform::BackInsertIterator<T>   
    back_inserter(IVector<T>^ v);  
  
template<typename T>  
Platform::BackInsertIterator<T>   
   back_inserter(IObservableVector<T>^ v);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir şablon türü parametresine.  
  
 `v`  
 Altta yatan seçki erişim sağlayan bir arabirim işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir yineleyici.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Windows::Foundation:: Collections  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation:: Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)