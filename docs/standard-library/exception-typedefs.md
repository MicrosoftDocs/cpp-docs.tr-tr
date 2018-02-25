---
title: "&lt;özel durum&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 24f4fc5d30a95d55b5a4241d9c70eca31255fc18
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltexceptiongt-typedefs"></a>&lt;özel durum&gt; tür tanımları
||||  
|-|-|-|  
|[exception_ptr](#exception_ptr)|[terminate_handler](#terminate_handler)|[unexpected_handler](#unexpected_handler)|  
  
##  <a name="exception_ptr"></a>  exception_ptr  
 Bir özel duruma bir işaretçi tanımlayan tür.  
  
```cpp  
typedef unspecified exception_ptr;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamak için kullanılan belirtilmeyen bir iç sınıf `exception_ptr` türü.  
  
 Kullanım bir `exception_ptr` geçerli özel durumun veya bir kullanıcı tarafından belirtilen özel örneği başvurmak için nesne. Microsoft uygulama, bir özel durum tarafından temsil edilen bir [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) yapısı. Her `exception_ptr` nesne içeren bir kopyasına işaret eden bir özel durum başvuru alanı `EXCEPTION_RECORD` yapısı özel durumu temsil eder.  
  
 Ne zaman bildirdiğiniz bir `exception_ptr` değişkeni, değişken herhangi bir özel durum ile ilişkili değil. Diğer bir deyişle, özel durum başvuru alanı NULL olur. Bu tür bir `exception_ptr` nesne adlı bir *null exception_ptr*.  
  
 Kullanım `current_exception` veya `make_exception_ptr` işlevi bir özel durum olarak atamak için bir `exception_ptr` nesnesi. Bir özel durum atadığınızda bir `exception_ptr` değişken, değişkenin özel durum başvurusu alan özel bir kopyasını gösterir. Özel durum kopyalamak için yeterli bellek varsa, özel durum başvurusu alan bir kopyasına işaret eden bir [std::bad_alloc](../standard-library/bad-alloc-class.md) özel durum. Varsa `current_exception` veya `make_exception_ptr` işlevi başka bir nedenle, işlev çağrıları özel kopyalayamıyor **sonlandırmak** geçerli işleminden çıkmak için CRT işlevi.  
  
 Adını rağmen bir `exception_ptr` nesne kendisi gösteren bir işaretçidir. İşaretçi semantiği uyma değil ve işaretçi üye erişimle kullanılamaz ( `->`) veya (*) yöneltme işleçleri. `exception_ptr` Nesneyi, hiçbir ortak veri üyeleri veya üye işlevleri sahiptir.  
  
 **Karşılaştırmaları:**  
  
 Eşittir kullanabilirsiniz ( `==`) ve eşit değil ( `!=`) iki Karşılaştırılacak işleçleri `exception_ptr` nesneleri. İşleçler ikili değeri (bit desenini) ile karşılaştırın değil `EXCEPTION_RECORD` özel durumları temsil eden yapılar. Bunun yerine, özel durum başvurusu alanına adresleri işleçleri karşılaştırmak `exception_ptr` nesneleri. Sonuç olarak, bir null `exception_ptr` ve eşit olarak karşılaştırmak NULL değer.  
  
##  <a name="terminate_handler"></a>  terminate_handler  
 Bir işlevi olarak kullanım için uygun bir işaretçi türü tanımlayan bir `terminate_handler`.  
  
```
typedef void (*terminate_handler)();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sonlandırıcı işleyici olarak kullanım için bir işleve işaretçi tanımlayan tür.  
  
### <a name="example"></a>Örnek  
  Bkz: [set_terminate](../standard-library/exception-functions.md#set_terminate) kullanımına ilişkin bir örnek `terminate_handler`.  
  
##  <a name="unexpected_handler"></a>  unexpected_handler  
 Bir işlevi olarak kullanım için uygun bir işaretçi türü tanımlayan bir `unexpected_handler`.  
  
```
typedef void (*unexpected_handler)();
```  
  
### <a name="example"></a>Örnek  
  Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek `unexpected_handler`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Özel Durum >](../standard-library/exception.md)



