---
description: 'Daha fazla bilgi edinin: unorm sınıfı'
title: unorm Sınıfı
ms.date: 11/04/2016
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
ms.openlocfilehash: 947660d046ea41025e70aa4e6521e3c8f34c0a94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314534"
---
# <a name="unorm-class"></a>unorm Sınıfı

Bir unorm numarasını temsil eder. Her öğe [0.0 f, 1.0 f] aralığındaki bir kayan noktalı sayıdır.

## <a name="syntax"></a>Syntax

```cpp
class unorm;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unorm Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu. 0.0 f 'ye başlatın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|unorm:: operator--||
|unorm:: operator float|Dönüştürme işleci. Unorm numarasını bir kayan nokta değerine dönüştürün.|
|unorm:: operator * =||
|unorm:: operator/=||
|unorm:: operator + +||
|unorm:: operator + =||
|unorm:: operator =||
|unorm:: operator-=||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`unorm`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_short_vectors. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="unorm"></a><a name="ctor"></a> unorm

Varsayılan Oluşturucu. 0.0 f 'ye başlatın.

```cpp
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parametreler

*_V*<br/>
Başlatmak için kullanılan değer.

*_Other*<br/>
Başlatmak için kullanılan norm nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
