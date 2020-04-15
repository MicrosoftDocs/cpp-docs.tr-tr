---
title: CComSimpleThreadAllocator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
ms.openlocfilehash: 4a3cce492db4db9f46aeb4efe738ee6a594ddcfc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327341"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator Sınıfı

Bu sınıf, sınıf `CComAutoThreadModule`için iş parçacığı seçimini yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComSimpleThreadAllocator::GetThread](#getthread)|Bir iş parçacığı seçer.|

## <a name="remarks"></a>Açıklamalar

`CComSimpleThreadAllocator`[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)için iş parçacığı seçimi yönetir. `CComSimpleThreadAllocator::GetThread`yalnızca her iş parçacığı arasında döngüleri ve sırayla bir sonraki döndürür.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a>CComSimpleThreadAllocator::GetThread

Dizideki bir sonraki iş parçacığı belirterek bir iş parçacığı seçer.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>Parametreler

*pApt*<br/>
ATL'nin varsayılan uygulamasında kullanılmaz.

*nThreads*<br/>
EXE modülündeki maksimum iş parçacığı sayısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfır ve *(nThreads* - 1) arasında bir sonda. EXE modülündeki iş parçacıklarından birini tanımlar.

### <a name="remarks"></a>Açıklamalar

Farklı bir `GetThread` seçim yöntemi sağlamak veya *pApt* parametresini kullanmak için geçersiz kılınabilirsiniz.

`GetThread`[CComAutoThreadModule tarafından çağrılır::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).

## <a name="see-also"></a>Ayrıca bkz.

[CComApartment Sınıfı](../../atl/reference/ccomapartment-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
