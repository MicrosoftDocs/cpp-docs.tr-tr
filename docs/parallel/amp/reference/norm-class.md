---
title: norm Sınıfı
ms.date: 11/04/2016
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
ms.openlocfilehash: 2d37dcb430be9941444a90ac0a4ba34f3ee30515
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630769"
---
# <a name="norm-class"></a>norm Sınıfı

Bir norm numarasını temsil eder. Her bir kayan bir öğedir aralığında nokta sayısı [-1.0f, 1.0f &].

## <a name="syntax"></a>Sözdizimi

```
class norm;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Norm Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu. İçin 0.0f başlatın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|Norm::operator-||
|Norm::operator--||
|Norm::operator float|Dönüştürme işleci. Kayan norm sayıya dönüştürme noktası değeri.|
|Norm::operator * =||
|Norm::operator / =||
|Norm::operator ++||
|Norm::operator +=||
|norm::operator=||
|Norm::operator-=||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`norm`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_short_vectors.h

**Namespace:** Concurrency::graphics

##  <a name="ctor"></a> Norm

Varsayılan Oluşturucu. İçin 0.0f başlatın.

```
norm(
    void) restrict(amp,
    cpu);

explicit norm(
    float _V) restrict(amp,
    cpu);

explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

explicit norm(
    int _V) restrict(amp,
    cpu);

explicit norm(
    double _V) restrict(amp,
    cpu);

norm(
    const norm& _Other) restrict(amp,
    cpu);

norm(
    const unorm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parametreler

*_V*<br/>
Başlatmak için kullanılan değer.

*_Diğer*<br/>
Başlatmak için kullanılan nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
