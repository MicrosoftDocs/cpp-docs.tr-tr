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
ms.openlocfilehash: a61e72f14448d5033d5be9069ffeec7d3bb08061
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142550"
---
# <a name="task_handle-class"></a>task_handle Sınıfı

`task_handle` sınıfı, tek bir paralel iş öğesini temsil eder. Bir iş parçasını yürütmek için gereken yönergeleri ve verileri saklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
`task_handle` nesnesi tarafından temsil edilen işi yürütmek için çağrılacak işlev nesnesinin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_handle](#task_handle)|Yeni bir `task_handle` nesnesi oluşturur. Görevin çalışması, oluşturucunun parametresi olarak belirtilen işlevi çağrılarak gerçekleştirilir.|
|[~ task_handle yok edici](#dtor)|`task_handle` nesnesini yok eder.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator ()](#task_handle__operator_call)|Çalışma zamanının görev tanıtıcısının işini gerçekleştirmesini sağlamak için çağırdığı işlev çağrısı işleci.|

## <a name="remarks"></a>Açıklamalar

`task_handle` nesneler, bir `structured_task_group` ya da daha genel `task_group` nesnesiyle birlikte çalışarak paralel görevlerle çalışmayı geri alabilir. Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

`task_handle` nesne oluşturucusunun, Eşzamanlılık Çalışma Zamanı tarafından artık gerekene kadar oluşturulan `task_handle` nesnesinin yaşam süresini sürdürmekten sorumlu olduğunu unutmayın. Genellikle bu, `task_handle` nesnesinin, kuyruğa alındığı `task_group` veya `structured_task_group` `wait` ya da `run_and_wait` yöntemi çağırana kadar yapı kaldırmaması gerektiği anlamına gelir.

`task_handle` nesneler genellikle Lambdalar ile C++ birlikte kullanılır. Lambda 'nin doğru türünü tanımadığınız için [make_task](concurrency-namespace-functions.md#make_task) işlevi genellikle bir `task_handle` nesnesi oluşturmak için kullanılır.

Çalışma zamanı, bir `task_handle` nesnesine geçirdiğiniz çalışma işlevinin bir kopyasını oluşturur. Bu nedenle, bir `task_handle` nesnesine geçirdiğiniz bir işlev nesnesinde oluşan tüm durum değişiklikleri, bu işlev nesnesinin kopyasında görünmez.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_handle`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="task_handle__operator_call"></a>operator ()

Çalışma zamanının görev tanıtıcısının işini gerçekleştirmesini sağlamak için çağırdığı işlev çağrısı işleci.

```cpp
void operator()() const;
```

## <a name="task_handle"></a>task_handle

Yeni bir `task_handle` nesnesi oluşturur. Görevin çalışması, oluşturucunun parametresi olarak belirtilen işlevi çağrılarak gerçekleştirilir.

```cpp
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Func*<br/>
`task_handle` nesnesi tarafından temsil edilen işi yürütmek için çağrılacak işlev. Bu bir lambda functor, bir işlevin işaretçisi veya imza `void operator()()`işlev çağrısı işlecinin bir sürümünü destekleyen herhangi bir nesne olabilir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, oluşturucuya geçirdiğiniz çalışma işlevinin bir kopyasını oluşturur. Bu nedenle, bir `task_handle` nesnesine geçirdiğiniz bir işlev nesnesinde oluşan tüm durum değişiklikleri, bu işlev nesnesinin kopyasında görünmez.

## <a name="dtor"></a>~ task_handle

`task_handle` nesnesini yok eder.

```cpp
~task_handle();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_group Sınıfı](task-group-class.md)<br/>
[structured_task_group Sınıfı](structured-task-group-class.md)
