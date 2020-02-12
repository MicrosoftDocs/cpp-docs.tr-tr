---
title: scoped_d3d_access_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: b5a2d9dab9cba7b19fa0d0b1627f653f2c7fdc57
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126402"
---
# <a name="scoped_d3d_access_lock-class"></a>scoped_d3d_access_lock Sınıfı

Bir accelerator_view nesnesi üzerinde D3D erişim kilidi için ÇII sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```cpp
class scoped_d3d_access_lock;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scoped_d3d_access_lock Oluşturucusu](#ctor)|Fazla Yüklendi. `scoped_d3d_access_lock` nesnesi oluşturur. Kilit, bu nesne kapsam dışına geçtiğinde serbest bırakılır.|
|[~ scoped_d3d_access_lock yok edici](#dtor)|İlişkili `accelerator_view` nesnesi üzerinde D3D erişim kilidini serbest bırakır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Bir kilidin sahipliğini başka bir `scoped_d3d_access_lock`alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scoped_d3d_access_lock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** eşzamanlılık::d irect3d

## <a name="ctor"></a>scoped_d3d_access_lock

`scoped_d3d_access_lock` nesnesi oluşturur. Kilit, bu nesne kapsam dışına geçtiğinde serbest bırakılır.

```cpp
explicit scoped_d3d_access_lock(// [1] constructor
    accelerator_view& _Av);

explicit scoped_d3d_access_lock(// [2] constructor
    accelerator_view& _Av,
    adopt_d3d_access_lock_t _T);

scoped_d3d_access_lock(// [3] move constructor
    scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
Benimseme için kilit `accelerator_view`.

*_T*<br/>
`adopt_d3d_access_lock_t` nesnesi.

*_Other*<br/>
Var olan kilidin taşınacağı nesne `scoped_d3d_access_lock`.

## <a name="construction"></a>İnşaat

[1] Oluşturucu, verilen [accelerator_view](accelerator-view-class.md) NESNESI üzerinde D3D erişim kilidi alır. Kilit alınana kadar yapı taşları.

[2] Oluşturucu verilen [accelerator_view](accelerator-view-class.md) nesnesinden D3D erişim kilidi benimseyin.

[3] taşıma Oluşturucusu, başka bir `scoped_d3d_access_lock` nesnesinden mevcut bir D3D erişim kilidi alır. Oluşturma engellenmiyor.

## <a name="dtor"></a>~ scoped_d3d_access_lock

İlişkili `accelerator_view` nesnesi üzerinde D3D erişim kilidini serbest bırakır.

```cpp
~scoped_d3d_access_lock();
```

## <a name="operator_eq"></a>işleç =

Bir D3D erişim kilidinin sahipliğini başka bir `scoped_d3d_access_lock` nesnesinden alır ve önceki kilidi serbest bırakır.

```cpp
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
D3D erişim kilidinin taşınacağı accelerator_view.

### <a name="return-value"></a>Dönüş Değeri

Bu `scoped_accelerator_view_lock`bir başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
