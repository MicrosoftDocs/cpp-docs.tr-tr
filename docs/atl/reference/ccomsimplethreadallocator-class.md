---
description: 'Daha fazla bilgi edinin: Ccomsimplethreadayırıcı sınıfı'
title: Ccomsimplethreadayırıcı sınıfı
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
ms.openlocfilehash: 5925707ecd459475d9e9002af76fb76dd9cf9d38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142200"
---
# <a name="ccomsimplethreadallocator-class"></a>Ccomsimplethreadayırıcı sınıfı

Bu sınıf, sınıf için iş parçacığı seçimini yönetir `CComAutoThreadModule` .

## <a name="syntax"></a>Syntax

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccomsimplethreadayırıcı:: GetThread](#getthread)|Bir iş parçacığı seçer.|

## <a name="remarks"></a>Açıklamalar

`CComSimpleThreadAllocator`[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)için iş parçacığı seçimini yönetir. `CComSimpleThreadAllocator::GetThread` Her bir iş parçacığı boyunca döngü yapar ve sıradaki bir sonrakini döndürür.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a> Ccomsimplethreadayırıcı:: GetThread

Sıradaki bir sonraki iş parçacığını belirterek bir iş parçacığı seçer.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>Parametreler

*pApt*<br/>
ATL 'nin varsayılan uygulamasında kullanılmıyor.

*nThreads*<br/>
EXE modülündeki iş parçacığı sayısı üst sınırı.

### <a name="return-value"></a>Dönüş Değeri

Sıfır ve (*nThreads* -1) arasında bir tamsayı. EXE modülündeki iş parçacıklarından birini tanımlar.

### <a name="remarks"></a>Açıklamalar

`GetThread`Farklı bir seçim yöntemi sağlamak ya da *pApt* parametresini kullanmak için geçersiz kılabilirsiniz.

`GetThread`[CComAutoThreadModule:: CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)tarafından çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[CComApartment sınıfı](../../atl/reference/ccomapartment-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
