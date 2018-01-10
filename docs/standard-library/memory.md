---
title: '&lt;bellek&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::<memory>
- <memory>
- std::<memory>
dev_langs: C++
helpviewer_keywords: memory header
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6133b5a2f60cba4554ac4a0f1a358380df0dc7c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltmemorygt"></a>&lt;bellek&gt;
Bir sınıfı, işleci ve nesneleri ayırmaya ve serbest bırakmaya yardımcı çeşitli şablonları tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <memory>  
  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[AddressOf](../standard-library/memory-functions.md#addressof)|Bir nesnenin doğru adresini alır.|  
|[Hizalama](../standard-library/memory-functions.md#align)|Sağlanan hizalama ve başlangıç adresini temel alarak belirli bir boyut aralığı için bir işaretçi döndürür.|  
|[allocate_shared](../standard-library/memory-functions.md#allocate_shared)|Oluşturur bir `shared_ptr` ayrılmış ve verilen bir tür için belirtilen ayırıcısı ile oluşturulan nesneleri.|  
|[const_pointer_cast](../standard-library/memory-functions.md#const_pointer_cast)|Const dönüştürme `shared_ptr`.|  
|[declare_no_pointers](../standard-library/memory-functions.md#declare_no_pointers)|Belirli bir adreste başlayan ve belirtilen blok boyutu içinde kalan karakterlerin izlenebilir işaretçi içermediğini atık toplayıcıya bildirir.|  
|[declare_reachable](../standard-library/memory-functions.md#declare_reachable)|Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.|  
|[default_delete](../standard-library/memory-functions.md#default_delete)|İle ayrılmış nesneleri siler `operator new`. İle kullanılmak üzere uygun `unique_ptr`.|  
|[dynamic_pointer_cast](../standard-library/memory-functions.md#dynamic_pointer_cast)|Dinamik atama için `shared_ptr`.|  
|[get_deleter](../standard-library/memory-functions.md#get_deleter)|Gelen Silici almak `shared_ptr`.|  
|[get_pointer_safety](../standard-library/memory-functions.md#get_pointer_safety)|Herhangi bir atık toplayıcısı tarafından kabul edilen işaretçi güvenlik türünü döndürür.|  
|[get_temporary_buffer](../standard-library/memory-functions.md#get_temporary_buffer)|Belirli sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.|  
|[make_shared](../standard-library/memory-functions.md#make_shared)|Oluşturur ve döndüren bir `shared_ptr` varsayılan ayırıcıyı kullanarak sıfır veya daha fazla bağımsız değişkenlerden oluşturulan ayrılmış nesne işaret.|  
|[make_unique](../standard-library/memory-functions.md#make_unique)|Oluşturur ve döndüren bir [unique_ptr](../standard-library/unique-ptr-class.md) sıfır veya daha fazla bağımsız değişkenlerden oluşturulan ayrılmış nesne işaret.|  
|[owner_less](../standard-library/memory-functions.md#owner_less)|Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar.|  
|[pointer_safety](../standard-library/memory-enums.md#pointer_safety)|Tüm olası dönüş değerleri numaralandırması `get_pointer_safety`.|  
|[return_temporary_buffer](../standard-library/memory-functions.md#return_temporary_buffer)|Kullanılarak ayrıldı geçici bellek kaldırır `get_temporary_buffer` şablon işlevi.|  
|[static_pointer_cast](../standard-library/memory-functions.md#static_pointer_cast)|Statik atama için `shared_ptr`.|  
|[değiştirme](../standard-library/memory-functions.md#swap)|İki takas `shared_ptr` veya `weak_ptr` nesneleri.|  
|[undeclare_no_pointers](../standard-library/memory-functions.md#undeclare_no_pointers)|Taban adresi işaretçisi ve blok boyutu tarafından bellek bloğuna tanımlanan Bellek bloğu karakterlerin artık izlenebilir işaretçileri içerebileceğini atık toplayıcıya bildirir.|  
|[undeclare_reachable](../standard-library/memory-functions.md#undeclare_reachable)|Bildiren bir `garbage_collector` belirtilen bellek konumuna erişilemiyor.|  
|[uninitialized_copy](../standard-library/memory-functions.md#uninitialized_copy)|Nesneleri belirli bir girdi aralığından başlatılmamış hedef aralığına kopyalar.|  
|[uninitialized_copy_n](../standard-library/memory-functions.md#uninitialized_copy_n)|Bir girdi yineleyicisinde belirtilen öğe sayısının bir kopyasını oluşturur. Kopyalar ileri doğru bir yineleyicinin içine yerleştirilir.|  
|[uninitialized_fill](../standard-library/memory-functions.md#uninitialized_fill)|Belirli bir değerin nesnelerini başlatılmamış hedef aralığına kopyalar.|  
|[uninitialized_fill_n](../standard-library/memory-functions.md#uninitialized_fill_n)|Belirli bir değerin nesnelerini belirli sayıda öğenin başlatılmamış hedef aralığına kopyalar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator!=](../standard-library/memory-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|  
|[operator ==](../standard-library/memory-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|  
|[operator>=](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden büyük veya eşit olmasını sınar.|  
|[operator <](../standard-library/memory-operators.md#op_lt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden küçük olmasını sınar.|  
|[işleci\<=](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden küçük veya eşit olmasını sınar.|  
|[operator >](../standard-library/memory-operators.md#op_gt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden büyük olmasını sınar.|  
|[işleç <<](../standard-library/memory-operators.md#op_lt_lt)|`shared_ptr`ekleyici.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[ayırıcısı](../standard-library/allocator-class.md)|Depolama ayırma ve nesne türü diziler için boşaltma yöneten bir nesne şablonu sınıf tanımlar **türü**.|  
|[allocator_traits](../standard-library/allocator-traits-class.md)|Ayırıcı tarafından etkinleştirilen kapsayıcı tarafından gerek duyulan bilgilerin tamamını belirleyen nesneyi tanımlar.|  
|[auto_ptr](../standard-library/auto-ptr-class.md)|Ayrılmış bir nesne türü için bir işaretçi depolayan bir nesne şablonu sınıf tanımlar **türü \***  hangi BT noktaları silinmiş kapsayan auto_ptr yok, nesne sağlar.|  
|[bad_weak_ptr](../standard-library/bad-weak-ptr-class.md)|Bozuk weak_ptr özel durumunu raporlar.|  
|[enabled_shared_from_this](../standard-library/enable-shared-from-this-class.md)|Oluştur yardımcı olan bir `shared_ptr`.|  
|[pointer_traits](../standard-library/pointer-traits-struct.md)|Şablon sınıfın bir nesnesi tarafından gereken tek bilgi sağlayan `allocator_traits` işaretçi türü ile bir ayırıcı açıklamak için `Ptr`.|  
|[raw_storage_iterator](../standard-library/raw-storage-iterator-class.md)|Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.|  
|[shared_ptr](../standard-library/shared-ptr-class.md)|Dinamik olarak tahsis edilen bir nesnenin çevresine bir başvuru sayılan akıllı işaretçi sarar.|  
|[unique_ptr](../standard-library/unique-ptr-class.md)|Sahip olunan bir nesnenin işaretçisini depolar. İşaretçinin tarafından başka ait `unique_ptr`. `unique_ptr` Sahibi bozulduğunda yok.|  
|[weak_ptr](../standard-library/weak-ptr-class.md)|Zayıf bağlantılı bir işaretçi sarar.|  
  
### <a name="specializations"></a>Uzmanlıklar  
  
|||  
|-|-|  
|[Ayırıcı\<void >](../standard-library/allocator-void-class.md)|Yalnızca bu özelleştirilen içerikte anlamlı üye türleri tanımlayarak void türüne şablon sınıf ayırıcı uzmanlığı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



