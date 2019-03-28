---
title: task_handle Sınıfı
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: 8528bc212603484be9325ed967e9475e4faa1348
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565106"
---
# <a name="taskhandle-class"></a>task_handle Sınıfı

`task_handle` Sınıfı, tek bir paralel iş öğesinin temsil eder. Bu yönergeler ve bir parça işin yürütme için gerekli verileri saklar.

## <a name="syntax"></a>Sözdizimi

```
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

#### <a name="parameters"></a>Parametreler

*_Function*<br/>
Tarafından temsil edilen iş yürütme için çağrılacak işlev nesnesinin türü `task_handle` nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_handle](#task_handle)|Yeni bir oluşturur `task_handle` nesne. Görevin iş oluşturucusuna bir parametre olarak belirtilen işlevi çağrılarak gerçekleştirilir.|
|[~ task_handle yok Edicisi](#dtor)|Yok eder `task_handle` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator()](#task_handle__operator_call)|Görev tanıtıcısını işini gerçekleştirmek için çalışma zamanı çağıran işlev çağrısı işleci.|

## <a name="remarks"></a>Açıklamalar

`task_handle` nesneleri ile birlikte kullanılabilir bir `structured_task_group` ya da daha fazla genel `task_group` Paralel Görevler halinde ayırmak için nesne. Daha fazla bilgi için [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Unutmayın oluşturan bir `task_handle` nesnedir oluşturulan ömrünü sorumlu `task_handle` eşzamanlılık çalışma zamanı tarafından artık gerekli kadar nesne. Genellikle, yani `task_handle` nesne gerekir değil yok etmek kadar `wait` veya `run_and_wait` yöntemi `task_group` veya `structured_task_group` , hemen ardından kuyruğa için çağrılır.

`task_handle` nesneler genellikle C++ lambda ifadeleri ile birlikte kullanılır. Lambda true türünü bilmiyorsanız çünkü [make_task](concurrency-namespace-functions.md#make_task) işlevi oluşturmak için kullanılan tipik bir `task_handle` nesne.

Çalışma zamanı öğesine geçirdiğiniz çalışma işlevini bir kopyasını oluşturur. bir `task_handle` nesne. Bu nedenle, bir işlevde gerçekleşen durumu değişiklikleri için geçirdiğiniz nesne bir `task_handle` nesne, bu işlev nesnesi kopyanızda görünmez.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_handle`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="task_handle__operator_call"></a> operator()

Görev tanıtıcısını işini gerçekleştirmek için çalışma zamanı çağıran işlev çağrısı işleci.

```
void operator()() const;
```

## <a name="taskhandle"></a>task_handle

Yeni bir oluşturur `task_handle` nesne. Görevin iş oluşturucusuna bir parametre olarak belirtilen işlevi çağrılarak gerçekleştirilir.

```
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Func*<br/>
Tarafından temsil edilen iş yürütme için çağrılacak işlev `task_handle` nesne. Bu bir lambda işlevse, bir işlev işaretçisine olabilir veya herhangi bir işlev çağrısı işleci imzalı sürümünü destekleyen nesne `void operator()()`.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, oluşturucuya geçirdiğiniz çalışma işlevi bir kopyasını oluşturur. Bu nedenle, bir işlevde gerçekleşen durumu değişiklikleri için geçirdiğiniz nesne bir `task_handle` nesne, bu işlev nesnesi kopyanızda görünmez.

##  <a name="dtor"></a> ~ task_handle

Yok eder `task_handle` nesne.

```
~task_handle();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_group Sınıfı](task-group-class.md)<br/>
[structured_task_group Sınıfı](structured-task-group-class.md)
