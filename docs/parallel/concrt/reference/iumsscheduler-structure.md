---
description: 'Daha fazla bilgi edinin: IUMSScheduler yapısı'
title: IUMSScheduler Yapısı
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: e42a2e3d39e568ba12cd681053406ce88c7b5dba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334336"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler Yapısı

Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi, Kullanıcı modu zamanlanabilen (UMS) iş parçacıklarını ele almak isteyen bir iş Zamanlayıcı soyutlaması için arabirim. Kaynak Yöneticisi, UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için bu arabirimi kullanır. `IUMSScheduler`Arabirim `IScheduler` arabiriminden devralır.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IUMSScheduler:: SetCompletionList](#setcompletionlist)|`IUMSCompletionList`UMS iş parçacığı zamanlayıcısına bir arabirim atar.|

## <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi ile iletişim kuran özel bir Zamanlayıcı uygulamadıysanız ve UMS iş parçacıklarının sıradan Win32 iş parçacıkları yerine Scheduler 'a devredilmesi istiyorsanız, arabirimin bir uygulamasını sağlamanız gerekir `IUMSScheduler` . Ayrıca, Zamanlayıcı İlkesi anahtarının ilke değerini de `SchedulerKind` olacak şekilde ayarlamanız gerekir `UmsThreadDefault` . İlke UMS iş parçacığını belirtiyorsa, `IScheduler` [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) metoduna parametre olarak geçirilen arabirim bir `IUMSScheduler` arabirim olmalıdır.

Kaynak Yöneticisi, yalnızca UMS özelliğine sahip işletim sistemlerinde UMS iş parçacıklarını ele alır. Windows 7 sürümü ve daha yüksek olan 64 bitlik işletim sistemleri, UMS iş parçacıklarını destekler. Anahtarı değere ayarlanmış bir Zamanlayıcı İlkesi oluşturursanız `SchedulerKind` `UmsThreadDefault` ve temel ALıNAN platform UMS 'yi desteklemiyorsa, `SchedulerKind` Bu ilkedeki anahtarın değeri değere değiştirilir `ThreadScheduler` . UMS iş parçacıklarını almayı beklemeden önce Bu ilke değerini her zaman okumanız gerekir.

`IUMSScheduler`Arabirim, bir Zamanlayıcı ve kaynak yöneticisi arasındaki iki yönlü bir kanalın bir bitişidir. Diğer son, `IResourceManager` `ISchedulerProxy` Kaynak Yöneticisi tarafından uygulanan ve arabirimleri tarafından temsil edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a> IUMSScheduler:: SetCompletionList yöntemi

`IUMSCompletionList`UMS iş parçacığı zamanlayıcısına bir arabirim atar.

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Parametreler

*pCompletionList*<br/>
Zamanlayıcı için tamamlanma listesi arabirimi. Zamanlayıcı başına tek bir liste vardır.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, Zamanlayıcı ilk kaynak ayırmayı istediğinde, bu yöntemi, UMS iş parçacıkları istediğini belirten bir Scheduler 'da çağıracaktır. Zamanlayıcı, `IUMSCompletionList` UMS iş parçacığı proxy 'lerinin ne zaman engellenmemiş olduğunu anlamak için arabirimini kullanabilir. Bu arabirime yalnızca, UMS Scheduler 'a atanmış sanal bir işlemci kökünde çalışan bir iş parçacığı proxy 'sinden erişim için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
