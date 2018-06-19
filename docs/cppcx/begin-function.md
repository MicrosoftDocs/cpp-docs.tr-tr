---
title: İşlev başlayın | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::begin
dev_langs:
- C++
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1a8c09e43613014b43ef4e3c075a54cdd90e08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33086518"
---
# <a name="begin-function"></a>İşlev başlayın
Belirtilen arabirim parametresi tarafından erişilebilen bir koleksiyon başlangıcına işaret yineleyici döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon türü parametresi.  
  
 `v`  
 Vektör koleksiyonu\<T > veya VectorView\<T > bir IVector tarafından erişilen nesneler\<T > veya IVectorView\<T > arabirimini.  
  
 `i`  
 Bir IIterable tarafından erişilen rasgele Windows çalışma zamanı nesneleri koleksiyonu\<T > arabirimini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Koleksiyon başlangıcına işaret yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk iki şablon işlevleri yineleyiciler dönün ve giriş yineleyici üçüncü şablon işlevi döndürür.  
  
 Tarafından döndürülen nesne başlamak VectorIterator VectorProxy türündeki öğeler depolayan bir proxy yineleyici olduğu\<T >. Ancak, proxy nesnesi neredeyse hiç kullanıcı kodu görünür olur. Daha fazla bilgi için bkz: [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation::Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)