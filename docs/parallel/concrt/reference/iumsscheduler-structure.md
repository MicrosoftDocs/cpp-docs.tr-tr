---
title: IUMSScheduler Yapısı
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: 70954906122c048e5199a801632626d35a8e3f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368090"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler Yapısı

Eşzamanlı Çalışma Zamanı Kaynak Yöneticisi'nin kullanıcı modu zamanlanabilir (UMS) iş parçacıklarını teslim etmesini isteyen bir çalışma zamanlayıcısının soyutlanmasına yönelik bir arabirim. Kaynak Yöneticisi, UMS iş parçacığı zamanlayıcılarıyla iletişim kurmak için bu arabirimi kullanır. `IScheduler` Arabirim, `IUMSScheduler` arabirimden devralır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|UMS `IUMSCompletionList` iş parçacığı zamanlayıcısına bir arabirim atar.|

## <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi ile iletişim kuran özel bir zamanlayıcı uyguluyorsanız ve UMS iş parçacıklarının sıradan Win32 iş parçacıkları yerine zamanlayıcınıza verilmesini `IUMSScheduler` istiyorsanız, arabirimin uygulanmasını sağlamanız gerekir. Buna ek olarak, zamanlayıcı ilkesi anahtarı `SchedulerKind` için ilke değerini ayarlamanız `UmsThreadDefault`gerekir. İlke UMS iş parçacığı belirtse, IResourceManager'a parametre olarak geçirilen `IScheduler` arabirim::RegisterScheduler yöntemi bir [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) `IUMSScheduler` arabirim olmalıdır.

Kaynak Yöneticisi size UMS iş parçacıklarını yalnızca UMS özelliğine sahip işletim sistemlerinde verebmektedir. Sürüm Windows 7 ve daha yüksek destek UMS iş parçacıkları ile 64-bit işletim sistemleri. `SchedulerKind` Anahtar `UmsThreadDefault` değerine ayarlanmış bir zamanlayıcı ilkesi oluşturursanız ve temel platform UMS'yi `SchedulerKind` desteklemiyorsa, bu ilkedeki anahtarın değeri değere `ThreadScheduler`değiştirilir. UMS iş parçacığı almayı beklemeden önce bu ilke değerini her zaman geri okumalısınız.

Arabirim, `IUMSScheduler` zamanlayıcı ile Kaynak Yöneticisi arasındaki iki yönlü iletişim kanalının bir sonudur. Diğer uç, Kaynak Yöneticisi `IResourceManager` `ISchedulerProxy` tarafından uygulanan ve arabirimler tarafından temsil edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ıscheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a>IUMSScheduler::SetCompletionList Yöntemi

UMS `IUMSCompletionList` iş parçacığı zamanlayıcısına bir arabirim atar.

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Parametreler

*pCompletionList*<br/>
Zamanlayıcıiçin tamamlanma listesi arabirimi. Zamanlayıcı başına tek bir liste vardır.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, zamanlayıcı kaynakların ilk tahsisini istedikten sonra UMS iş parçacığı istediğini belirten bir zamanlayıcıüzerinde bu yöntemi çağırır. Zamanlayıcı, UMS `IUMSCompletionList` iş parçacığı eklerinin ne zaman engellendiğini belirlemek için arabirimi kullanabilir. Bu arabirime yalnızca UMS zamanlayıcısına atanan sanal işlemci kökünde çalışan bir iş parçacığı proxy'sinden erişmek için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
