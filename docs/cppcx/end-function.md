---
title: end işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::end
dev_langs:
- C++
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec25b92ca9ce21f72ff2fb573aae316ef1c19eac
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596656"
---
# <a name="end-function"></a>end işlevi
Bir koleksiyonun belirtilen arabirim parametresi tarafından erişilen ötesinde gösteren bir yineleyici döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template <typename T>  
    ::Platform::Collections::VectorIterator<T>   
    end(  
        IVector<T>^ v       );  
  
template <typename T>  
    ::Platform::Collections::VectorViewIterator<T>   
    end(  
        IVectorView<T>^ v  
       );  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    end(  
        IIterable<T>^ i  
       );  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir şablon türü parametresine.  
  
 `v`  
 Vektör koleksiyonunu\<T > ya da VectorView\<T > bir Ivector tarafından erişilen nesneler\<T >, veya IVectorView\<T > arabirimini.  
  
 `i`  
 Windows çalışma zamanı arbitraty koleksiyonunu bir Iıterable tarafından erişilen nesneler\<T > arabirimini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Koleksiyonun sonunu gösteren bir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk iki şablon işlevi Yineleyicilerin dönün ve üçüncü şablon işlevi bir giriş yineleyici döndürür.  
  
 [Platform::Collections:: vectorviewıterator](../cppcx/platform-collections-vectorviewiterator-class.md) tarafından döndürülen nesne `end` türünde öğeler depolayan bir ara sunucu yineleyici `VectorProxy<T>`. Ancak, proxy neredeyse hiç kullanıcı kodu tarafından nesnedir. Daha fazla bilgi için [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Windows::Foundation:: Collections  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation:: Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)