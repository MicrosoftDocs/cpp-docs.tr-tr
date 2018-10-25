---
title: scoped_d3d_access_lock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs:
- C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0bb3442de264e263ae0f0eabd93345eace1fde1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059616"
---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock Sınıfı

Hızlandırıcı görünümü nesnesindeki D3D erişim kilidi için RAII sarmalayıcı.

### <a name="syntax"></a>Sözdizimi

```
class scoped_d3d_access_lock;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scoped_d3d_access_lock Constructor](#ctor)|Fazla Yüklendi. Oluşturur bir `scoped_d3d_access_lock` nesne. Bu nesne kapsam dışına çıktığında kilidi serbest bırakılır.|
|[~ scoped_d3d_access_lock yok Edicisi](#dtor)|İlişkili D3D erişim kilidi serbest `accelerator_view` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Başka bir kilidi sahipliğini `scoped_d3d_access_lock`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scoped_d3d_access_lock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** concurrency::direct3d

##  <a name="ctor"></a> scoped_d3d_access_lock

Oluşturur bir `scoped_d3d_access_lock` nesne. Bu nesne kapsam dışına çıktığında kilidi serbest bırakılır.

```
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
`accelerator_view` Benimsenecek kilit için.

*_T*<br/>
`adopt_d3d_access_lock_t` Nesne.

*_Diğer*<br/>
`scoped_d3d_access_lock` Varolan bir kilidin kaldırılacağı nesne.

## <a name="construction"></a>Oluşturma

[1] oluşturucu üzerinde D3D erişim kilidi edinme verilen [accelerator_view](accelerator-view-class.md) nesne. Kilit alınıncaya kadar oluşturma blokedir.

[2] Oluşturucusu bir D3D erişim kilidi benimseyin verilen [accelerator_view](accelerator-view-class.md) nesne.

[3] taşıma Oluşturucu, varolan bir D3D erişim kilidini başka bir alan `scoped_d3d_access_lock` nesne. Oluşturma bloke değildir.

##  <a name="dtor"></a> ~scoped_d3d_access_lock

İlişkili D3D erişim kilidi serbest `accelerator_view` nesne.

```
~scoped_d3d_access_lock();
```

## <a name="operator_eq"></a> işleç =

Başka bir D3D erişim kilidi sahipliğini `scoped_d3d_access_lock` nesnesi ve önceki kilidi açar.

```
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
D3D erişim kilidinin taşınacağı, accelerator_view.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `scoped_accelerator_view_lock`.

## <a name="see-also"></a>Ayrıca Bkz.

[Concurrency::direct3d Ad Alanı](concurrency-direct3d-namespace.md)
