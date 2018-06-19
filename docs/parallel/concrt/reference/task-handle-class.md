---
title: task_handle sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
dev_langs:
- C++
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fa72ed19a691015214fe263033e07f8d6a74c34
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688212"
---
# <a name="taskhandle-class"></a>task_handle Sınıfı
`task_handle` Sınıfı, bir tek tek paralel iş öğesini temsil eder. Yönergeler ve bir parça işin yürütmek için gerekli verileri saklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<
    typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Function`  
 Tarafından temsil edilen çalışma yürütmek için çağrılan işlev nesnesinin türü `task_handle` nesnesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[task_handle](#ctor)|Yeni bir oluşturur `task_handle` nesnesi. Görev iş Oluşturucusu parametre olarak belirtilen işlevini çağırarak gerçekleştirilir.|  
|[~ task_handle yok Edicisi](#dtor)|Bozar `task_handle` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator()](#task_handle__operator_call)|Görev tanıtıcının işlerini yapmak için çalışma zamanı çağıran işlev çağırma işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 `task_handle` nesneleri ile birlikte kullanılabilir bir `structured_task_group` ya da daha fazla genel `task_group` Paralel Görevler içine iş parçalayın için nesne. Daha fazla bilgi için bkz: [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Unutmayın oluşturan bir `task_handle` nesnesidir oluşturulan ömrü bakımından sorumlu `task_handle` eşzamanlılık çalışma zamanı tarafından artık gerekli kadar nesnesi. Genellikle, bunun anlamı `task_handle` nesne gerekir değil destruct kadar `wait` veya `run_and_wait` yöntemi `task_group` veya `structured_task_group` hangi kuyruğa alınır için çağrılır.  
  
 `task_handle` nesneleri genellikle C++ Lambda'lar ile birlikte kullanılır. Lambda true türünü bilmiyorsanız çünkü [make_task](concurrency-namespace-functions.md#make_task) işlevi oluşturmak için kullanılan genellikle bir `task_handle` nesnesi.  
  
 Çalışma zamanı için geçirdiğiniz çalışma işlevini bir kopyasını oluşturur bir `task_handle` nesnesi. Bu nedenle, bir işlev içinde gerçekleşen durumu değişiklikleri için geçirdiğiniz nesne bir `task_handle` nesne bu işlev nesnesi kopyanızda görünmez.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `task_handle`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="task_handle__operator_call"></a> operator() 

 Görev tanıtıcının işlerini yapmak için çalışma zamanı çağıran işlev çağırma işleci.  
  
```  
void operator()() const;

 
```  
  
##  <a name="task_handle__ctor"></a> task_handle 

 Yeni bir oluşturur `task_handle` nesnesi. Görev iş Oluşturucusu parametre olarak belirtilen işlevini çağırarak gerçekleştirilir.  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Func`  
 Tarafından temsil edilen çalışma yürütmek için çağrılan işlev `task_handle` nesnesi. Bu, bir işlev için bir işaretçi bir lambda functor olabilir veya herhangi bir işlev çağırma işleci imzalı sürümünü destekleyen nesne `void operator()()`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı oluşturucuya geçirdiğiniz çalışma işlevini bir kopyasını oluşturur. Bu nedenle, bir işlev içinde gerçekleşen durumu değişiklikleri için geçirdiğiniz nesne bir `task_handle` nesne bu işlev nesnesi kopyanızda görünmez.  
  
##  <a name="dtor"></a> ~ task_handle 

 Bozar `task_handle` nesnesi.  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [task_group sınıfı](task-group-class.md)   
 [structured_task_group Sınıfı](structured-task-group-class.md)
