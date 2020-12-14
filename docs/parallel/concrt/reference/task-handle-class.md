---
description: 'Hakkında daha fazla bilgi edinin: task_handle Sınıfı'
title: task_handle Sınıfı
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: 21fa2a1782fad200061deb1e85bf052613354a34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188228"
---
# <a name="task_handle-class"></a>task_handle Sınıfı

`task_handle`Sınıfı, tek bir paralel iş öğesini temsil eder. Bir iş parçasını yürütmek için gereken yönergeleri ve verileri saklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Nesne tarafından temsil edilen işi yürütmek için çağrılacak işlev nesnesinin türü `task_handle` .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_handle](#task_handle)|Yeni bir `task_handle` nesne oluşturur. Görevin çalışması, oluşturucunun parametresi olarak belirtilen işlevi çağrılarak gerçekleştirilir.|
|[~ task_handle yok edici](#dtor)|Nesneyi yok eder `task_handle` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator ()](#task_handle__operator_call)|Çalışma zamanının görev tanıtıcısının işini gerçekleştirmesini sağlamak için çağırdığı işlev çağrısı işleci.|

## <a name="remarks"></a>Açıklamalar

`task_handle` nesneler `structured_task_group` , bir veya daha fazla genel nesne ile birlikte kullanılabilir `task_group` ve paralel görevlere iş oluşturmak için kullanabilirsiniz. Daha fazla bilgi için bkz. [Görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Bir nesne oluşturanın, `task_handle` `task_handle` artık eşzamanlılık çalışma zamanı tarafından gerekmediği sürece oluşturulan nesnenin yaşam süresini sürdürmekten sorumlu olduğunu unutmayın. Genellikle bu, nesnenin, kuyruğa alındığı ya da `task_handle` `wait` `run_and_wait` yöntemi `task_group` çağrılana kadar bir struct olmaması gerektiği anlamına gelir `structured_task_group` .

`task_handle` nesneler genellikle C++ Lambdalar ile birlikte kullanılır. Lambda 'nin doğru türünü tanımadığınız için [make_task](concurrency-namespace-functions.md#make_task) işlevi genellikle bir nesne oluşturmak için kullanılır `task_handle` .

Çalışma zamanı, bir nesneye geçirdiğiniz çalışma işlevinin bir kopyasını oluşturur `task_handle` . Bu nedenle, nesnesine geçirdiğiniz bir işlev nesnesinde oluşan tüm durum değişiklikleri, `task_handle` Bu işlev nesnesinin kopyasında görünmez.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_handle`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="operator"></a><a name="task_handle__operator_call"></a> operator ()

Çalışma zamanının görev tanıtıcısının işini gerçekleştirmesini sağlamak için çağırdığı işlev çağrısı işleci.

```cpp
void operator()() const;
```

## <a name="task_handle"></a><a name="task_handle"></a> task_handle

Yeni bir `task_handle` nesne oluşturur. Görevin çalışması, oluşturucunun parametresi olarak belirtilen işlevi çağrılarak gerçekleştirilir.

```cpp
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Parametreler

*_Func*<br/>
Nesne tarafından temsil edilen işi yürütmek için çağrılacak işlev `task_handle` . Bu bir lambda functor, bir işlev işaretçisi veya imza ile işlev çağrısı işlecinin bir sürümünü destekleyen herhangi bir nesne olabilir `void operator()()` .

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı, oluşturucuya geçirdiğiniz çalışma işlevinin bir kopyasını oluşturur. Bu nedenle, nesnesine geçirdiğiniz bir işlev nesnesinde oluşan tüm durum değişiklikleri, `task_handle` Bu işlev nesnesinin kopyasında görünmez.

## <a name="task_handle"></a><a name="dtor"></a> ~ task_handle

Nesneyi yok eder `task_handle` .

```cpp
~task_handle();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[task_group sınıfı](task-group-class.md)<br/>
[structured_task_group sınıfı](structured-task-group-class.md)
