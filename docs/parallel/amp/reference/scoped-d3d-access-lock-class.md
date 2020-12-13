---
description: 'Hakkında daha fazla bilgi edinin: scoped_d3d_access_lock sınıfı'
title: scoped_d3d_access_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
ms.openlocfilehash: 1106673ba9ca095b33660f6a713a40ae8498d384
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329908"
---
# <a name="scoped_d3d_access_lock-class"></a>scoped_d3d_access_lock Sınıfı

Bir accelerator_view nesnesi üzerinde D3D erişim kilidi için ÇII sarmalayıcı.

## <a name="syntax"></a>Syntax

```cpp
class scoped_d3d_access_lock;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scoped_d3d_access_lock Oluşturucusu](#ctor)|Fazla Yüklendi. Bir `scoped_d3d_access_lock` nesnesi oluşturur. Kilit, bu nesne kapsam dışına geçtiğinde serbest bırakılır.|
|[~ scoped_d3d_access_lock yok edici](#dtor)|İlişkili nesne üzerinde D3D erişim kilidini serbest bırakır `accelerator_view` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Bir kilidin sahipliğini başka bir kilit alır `scoped_d3d_access_lock` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scoped_d3d_access_lock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** eşzamanlılık::d irect3d

## <a name="scoped_d3d_access_lock"></a><a name="ctor"></a> scoped_d3d_access_lock

Bir `scoped_d3d_access_lock` nesnesi oluşturur. Kilit, bu nesne kapsam dışına geçtiğinde serbest bırakılır.

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
`accelerator_view`Benimseme kilidi için.

*_T*<br/>
`adopt_d3d_access_lock_t` nesnesi.

*_Other*<br/>
`scoped_d3d_access_lock`Var olan kilidin taşınacağı nesne.

## <a name="construction"></a>İnşaat

[1] Oluşturucu, verilen [accelerator_view](accelerator-view-class.md) NESNESI üzerinde D3D erişim kilidi alır. Kilit alınana kadar yapı taşları.

[2] Oluşturucu verilen [accelerator_view](accelerator-view-class.md) nesnesinden D3D erişim kilidi benimseyin.

[3] taşıma Oluşturucusu, başka bir nesneden mevcut bir D3D erişim kilidi alır `scoped_d3d_access_lock` . Oluşturma engellenmiyor.

## <a name="scoped_d3d_access_lock"></a><a name="dtor"></a> ~ scoped_d3d_access_lock

İlişkili nesne üzerinde D3D erişim kilidini serbest bırakır `accelerator_view` .

```cpp
~scoped_d3d_access_lock();
```

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Bir D3D erişim kilidinin sahipliğini başka bir nesneden alır `scoped_d3d_access_lock` ve önceki kilidi serbest bırakır.

```cpp
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
D3D erişim kilidinin taşınacağı accelerator_view.

### <a name="return-value"></a>Dönüş Değeri

Buna bir başvuru `scoped_accelerator_view_lock` .

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
