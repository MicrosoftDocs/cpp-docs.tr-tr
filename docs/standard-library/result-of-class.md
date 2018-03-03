---
title: "result_of sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 256f24ad40234db2bbc191a50b0d7e05de39c073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resultof-class"></a>result_of Sınıfı
Belirtilen bağımsız değişken türleri alır aranabilir türü dönüş türünü belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class>  
struct result_of; // Causes a static assert  
  
template <class Fn, class... ArgTypes>  
struct result_of<Fn(ArgTypes...)>;

// Helper type  
template<class T>
   using result_of_t = typename result_of<T>::type;
```  
  
#### <a name="parameters"></a>Parametreler  
 `Fn`  
 Sorgu için aranabilir türü.  
  
 `ArgTypes`  
 Sorgulanacak aranabilir türü için bağımsız değişken listesi türleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Sonuç türü, derleme zamanında belirlemek için bu şablonu kullanmak `Fn`(`ArgTypes`), burada `Fn` aranabilir türü, işlev başvurusunu ya da bir bağımsız değişken listesi türlerini kullanarak çağrılan aranabilir türüne başvuru `ArgTypes`. `type` Şablon sınıfının üye adları sonuç türü `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` varsa değerlendirilmeyecek ifade `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` doğru oluşturulmamış. Aksi takdirde, Şablon sınıfı hiçbir üyenin `type`. Türü `Fn` ve parametre paketi içindeki tüm türler `ArgTypes` tam tür `void`, veya bilinmeyen bağlı dizileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



