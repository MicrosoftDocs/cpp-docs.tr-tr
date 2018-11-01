---
title: unorm Sınıfı
ms.date: 11/04/2016
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
ms.openlocfilehash: b485d5efbfbcedbb1e11a3e212465340f0413ee4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491565"
---
# <a name="unorm-class"></a>unorm Sınıfı

Unorm numarasını temsil eder. Her bir kayan bir öğedir [0.0f, 1.0f] aralığında nokta sayısı.

## <a name="syntax"></a>Sözdizimi

```
class unorm;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unorm Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu. İçin 0.0f başlatın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|unorm::operator--||
|unorm::operator float|Dönüştürme işleci. Kayan unorm sayıya dönüştürme noktası değeri.|
|unorm::operator * =||
|unorm::operator / =||
|unorm::operator ++||
|unorm::operator +=||
|unorm::operator=||
|unorm::operator-=||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`unorm`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_short_vectors.h

**Namespace:** Concurrency::graphics

##  <a name="ctor"></a> unorm

Varsayılan Oluşturucu. İçin 0.0f başlatın.

```
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

*_Diğer*<br/>
Norm başlatmak için kullanılan nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
