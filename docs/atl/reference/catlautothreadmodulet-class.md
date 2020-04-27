---
title: CAtlAutoThreadModuleT Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: 7308e3a51c531fbe942e2df326c03273eeb326e2
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168730"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT Sınıfı

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

|Adı|Açıklama|
|----------|-----------------|
|[Catlautothreadmodület:: GetDefaultThreads](#getdefaultthreads)|Bu statik işlev, işlemci sayısına göre, EXE modülü için en fazla iş parçacığı sayısını dinamik olarak hesaplar ve döndürür.|

## <a name="remarks"></a>Açıklamalar

[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) sınıfı, iş parçacığı `CAtlAutoThreadModuleT` havuza alınmış, Apartman modeli com sunucusu uygulamak için öğesinden türetilir. Eski sınıf [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)yerini almıştır.

> [!NOTE]
> Bu sınıf DLL 'de kullanılmamalıdır, çünkü sonsuz varsayılan *dwWait* değeri dll kaldırıldığında kilitlenmeyle sonuçlanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a>Catlautothreadmodület:: GetDefaultThreads

Bu statik işlev, işlemci sayısına göre, EXE modülü için en fazla iş parçacığı sayısını dinamik olarak hesaplar ve döndürür.

```cpp
static int GetDefaultThreads();
```

### <a name="return-value"></a>Dönüş Değeri

EXE modülünde oluşturulacak iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

İş parçacığı sayısını hesaplamak için farklı bir yöntem kullanmak istiyorsanız bu yöntemi geçersiz kılın. Varsayılan olarak, iş parçacığı sayısı işlemci sayısını temel alır.

## <a name="see-also"></a>Ayrıca bkz.

[IAtlAutoThreadModule Sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[IAtlAutoThreadModule Sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
