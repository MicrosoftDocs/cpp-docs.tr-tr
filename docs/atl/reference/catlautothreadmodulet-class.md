---
description: 'Daha fazla bilgi edinin: Catlautothreadmodület sınıfı'
title: Catlautothreadmodület sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: ad55c78488567c12477c427b99a527b8154ddd22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158419"
---
# <a name="catlautothreadmodulet-class"></a>Catlautothreadmodület sınıfı

Bu sınıf, iş parçacığı havuza alınmış, Apartman modeli COM sunucusu uygulamak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

### <a name="parameters"></a>Parametreler

*T*<br/>
COM sunucusu uygulanacak sınıf.

*Threadayırıcı*<br/>
İş parçacığı seçimini yöneten sınıf. Varsayılan değer [Ccomsimplethreadayırıcı](../../atl/reference/ccomsimplethreadallocator-class.md)' dır.

*dwWait*<br/>
Milisaniye cinsinden zaman aşımı aralığını belirtir. Varsayılan değer sonsuz ' dur, bu da yöntemin zaman aşımı aralığının hiçbir zaman sona ermediği anlamına gelir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Catlautothreadmodület:: GetDefaultThreads](#getdefaultthreads)|Bu statik işlev, işlemci sayısına göre, EXE modülü için en fazla iş parçacığı sayısını dinamik olarak hesaplar ve döndürür.|

## <a name="remarks"></a>Açıklamalar

[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) sınıfı `CAtlAutoThreadModuleT` , iş parçacığı havuza alınmış, Apartman modeli com sunucusu uygulamak için öğesinden türetilir. Eski sınıf [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)yerini almıştır.

> [!NOTE]
> Bu sınıf DLL 'de kullanılmamalıdır, çünkü sonsuz varsayılan *dwWait* değeri dll kaldırıldığında kilitlenmeyle sonuçlanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a> Catlautothreadmodület:: GetDefaultThreads

Bu statik işlev, işlemci sayısına göre, EXE modülü için en fazla iş parçacığı sayısını dinamik olarak hesaplar ve döndürür.

```cpp
static int GetDefaultThreads();
```

### <a name="return-value"></a>Dönüş Değeri

EXE modülünde oluşturulacak iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

İş parçacığı sayısını hesaplamak için farklı bir yöntem kullanmak istiyorsanız bu yöntemi geçersiz kılın. Varsayılan olarak, iş parçacığı sayısı işlemci sayısını temel alır.

## <a name="see-also"></a>Ayrıca bkz.

[IAtlAutoThreadModule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[IAtlAutoThreadModule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
