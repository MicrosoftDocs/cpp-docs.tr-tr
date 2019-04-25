---
title: CComSimpleThreadAllocator sınıfı
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
ms.openlocfilehash: ef1f86ca832674ba5710083b08b67f0a775a7a33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246159"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator sınıfı

Bu sınıf, sınıf için iş parçacığı seçimi yönetir `CComAutoThreadModule`.

## <a name="syntax"></a>Sözdizimi

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComSimpleThreadAllocator::GetThread](#getthread)|Bir iş parçacığı seçer.|

## <a name="remarks"></a>Açıklamalar

`CComSimpleThreadAllocator` iş parçacığı seçimi yönetir [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread` yalnızca her bir iş parçacığı arasında geçiş yapar ve bir dizi döndürür.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="getthread"></a>  CComSimpleThreadAllocator::GetThread

Bir iş parçacığı dizisinde sonraki iş parçacığını belirterek seçer.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>Parametreler

*pApt*<br/>
ATL'ın varsayılan uygulamasında kullanılmaz.

*nThreads*<br/>
EXE modülü iş parçacıklarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfır arasında bir tamsayı ve (*nThreads* - 1). EXE modülündeki iş parçacıklarından tanımlar.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılabilirsiniz `GetThread` seçimin farklı bir yöntem sağlamak veya yapmak için kullanım *pApt* parametresi.

`GetThread` çağıran [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).

## <a name="see-also"></a>Ayrıca bkz.

[CComApartment Sınıfı](../../atl/reference/ccomapartment-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
