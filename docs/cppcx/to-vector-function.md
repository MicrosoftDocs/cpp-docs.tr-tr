---
title: to_vector işlevi | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
dev_langs:
- C++
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00ecb00a890629c69994019c9232ff559ea93c96
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609744"
---
# <a name="tovector-function"></a>to_vector işlevi
Döndürür bir `std::vector` değeri olan belirtilen Ivector veya IVectorView parametre temel koleksiyon ile aynı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename T>  
inline ::std::vector<T> to_vector(IVector<T>^ v); 
 
template <typename T>  
inline ::std::vector<T> to_vector(IVectorView<T>^ v);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon tür parametresi.  
  
 `v`  
 Temel alınan bir vektör veya VectorView nesneye erişim sağlayan bir Ivector veya IVectorView arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Windows::Foundation:: Collections  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation:: Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)