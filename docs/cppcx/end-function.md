---
title: end Function | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Windows::Foundation::Collections::end
dev_langs: C++
helpviewer_keywords: end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: f4030728c296a6dd234b6ad181d83ef072b06dd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="end-function"></a>Son işlevi
Belirtilen arabirim parametresi tarafından erişilebilen bir koleksiyon ötesinde işaret yineleyici döndürür.  
  
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
 Şablon türü parametresi.  
  
 `v`  
 Vektör koleksiyonu\<T > veya VectorView\<T > bir IVector tarafından erişilen nesneler\<T >, veya IVectorView\<T > arabirimini.  
  
 `i`  
 Bir IIterable tarafından erişilen nesneleri arbitraty Windows çalışma zamanı topluluğu\<T > arabirimini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Topluluğun sonuna işaret yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk iki şablon işlevleri yineleyiciler dönün ve giriş yineleyici üçüncü şablon işlevi döndürür.  
  
 [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) tarafından döndürülen nesne `end` türündeki öğeler depolayan bir proxy yineleyici olduğu `VectorProxy<T>`. Ancak, proxy nesnesi neredeyse hiç kullanıcı kodu görünür olur. Daha fazla bilgi için bkz: [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation::Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)