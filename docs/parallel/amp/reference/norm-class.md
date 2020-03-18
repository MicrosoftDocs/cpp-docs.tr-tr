---
title: norm Sınıfı
ms.date: 11/04/2016
f1_keywords:
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
ms.openlocfilehash: b5740f33dea6aad79770f77f179803023432248a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447531"
---
# <a name="norm-class"></a>norm Sınıfı

Norm bir sayıyı temsil eder. Her öğe [-1.0 f, 1.0 f] aralığındaki bir kayan noktalı sayıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
class norm;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Norm Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu. 0\.0 f 'ye başlatın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|norm:: operator-||
|norm:: operator--||
|norm:: operator float|Dönüştürme işleci. Norm sayıyı bir kayan nokta değerine dönüştürür.|
|norm:: operator * =||
|norm:: operator/=||
|norm:: operator + +||
|norm:: operator + =||
|norm::operator=||
|norm:: operator-=||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`norm`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_short_vectors. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="ctor"></a>eklenmeli

Varsayılan Oluşturucu. 0\.0 f 'ye başlatın.

```cpp
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

*_Other*<br/>
Başlatmak için kullanılan nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
