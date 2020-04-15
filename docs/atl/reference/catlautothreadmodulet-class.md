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
ms.openlocfilehash: e7b7a327d7c47c4472b43ed58fbe9ad0556a7620
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321550"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT Sınıfı

Bu sınıf, iş parçacığı havuzlu, apartman modeli COM sunucusu uygulamak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
COM sunucusunu uygulayacak sınıf.

*ThreadAllocator*<br/>
Sınıf yönetim iş parçacığı seçimi. Varsayılan değer [CComSimpleThreadAllocator'dur.](../../atl/reference/ccomsimplethreadallocator-class.md)

*dwWait*<br/>
Zaman aralığını milisaniye cinsinden belirtir. Varsayılan, yöntemin zaman aşımı aralığının hiçbir zaman gerçekleşmediği anlamına gelen SONSUZ'dur.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Bu statik işlev, işlemci sayısına bağlı olarak EXE modülü için maksimum iş parçacığı sayısını dinamik olarak hesaplar ve döndürür.|

## <a name="remarks"></a>Açıklamalar

[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) sınıfı, iş `CAtlAutoThreadModuleT` parçacığı havuzu, daire modeli COM sunucusu nu uygulamak için türetilmiştir. Bu eski sınıf [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)değiştirir.

> [!NOTE]
> DLL boşaltıldığında SONSUZ varsayılan *dwWait* değeri bir kilitlenme neden olacağından, bu sınıf bir DLL kullanılmamalıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads

Bu statik işlev, işlemci sayısına bağlı olarak EXE modülü için maksimum iş parçacığı sayısını dinamik olarak hesaplar ve döndürür.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Dönüş Değeri

EXE modülünde oluşturulacak iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

İş parçacığı sayısını hesaplamak için farklı bir yöntem kullanmak istiyorsanız bu yöntemi geçersiz kılın. Varsayılan olarak, iş parçacığı sayısı işlemci sayısını temel alır.

## <a name="see-also"></a>Ayrıca bkz.

[IAtlAutoThreadModule Sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[IAtlAutoThreadModule Sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)
