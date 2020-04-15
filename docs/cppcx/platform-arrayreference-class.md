---
title: Platform::ArrayReference Sınıfı
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: e9dd16ad6c3f53c5562b0419197a582c06fbc642
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354798"
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference Sınıfı

`ArrayReference`bir C stili diziyi giriş verileriyle doldurmak istediğinizde giriş parametrelerinde [Platform::Array^](../cppcx/platform-array-class.md) yerine koyabileceğiniz bir optimizasyon türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
class ArrayReference
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[ArrayReference::ArrayReference](#ctor)|`ArrayReference` sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[ArrayReference::operator() Operatör](#operator-call)|Bunu `ArrayReference` bir `Platform::Array<T>^*`.|
|[ArrayReference::operator= Operatör](#operator-assign)|Başka birinin `ArrayReference` içeriğini bu örneğin içeriğini atar.|

## <a name="exceptions"></a>Özel durumlar

### <a name="remarks"></a>Açıklamalar

C `ArrayReference` stili diziyi doldurmak için kullanarak, önce bir `Platform::Array` değişkene, ardından C stili diziye kopyalamada rol alacak ekstra kopyalama işleminden kaçınırsınız. Kullandığınızda, `ArrayReference`yalnızca bir kopyalama işlemi vardır. Kod örneği için [Array ve WriteOnlyArray'e](../cppcx/array-and-writeonlyarray-c-cx.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Başlık:** vccorlib.h

## <a name="arrayreferencearrayreference-constructor"></a><a name="ctor"></a>ArrayReference::ArrayReference Constructor

Platformun yeni bir örneğini başolarak [laştırır::ArrayReference](../cppcx/platform-arrayreference-class.md) sınıfı.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>Parametreler

*dataArg*<br/>
Dizi verilerine işaretçi.

*boyutArg*<br/>
Kaynak dizisindeki öğelerin sayısı.

*otherArg*<br/>
Verileri `ArrayReference` yeni örneği başlatmak için taşınacak bir nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="arrayreferenceoperator-operator"></a><a name="operator-assign"></a>ArrayReference::operator= Operatör

Belirtilen nesneyi geçerli [Platforma atar::ArrayReference](../cppcx/platform-arrayreference-class.md) nesnesi taşıma semantiklerini kullanarak.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Parametreler

*otherArg*<br/>
Geçerli `ArrayReference` nesneye taşınan nesne.

### <a name="return-value"></a>Dönüş Değeri

Türdeki `ArrayReference`bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

`Platform::ArrayReference`standart bir C++ sınıfı şablonudur, ref sınıfı değildir.

## <a name="arrayreferenceoperator-operator"></a><a name="operator-call"></a>ArrayReference::operator() Operatör

Geçerli Platformu [dönüştürür::ArrayReference](../cppcx/platform-arrayreference-class.md) nesnesini [platforma geri döndürür::Dizi](../cppcx/platform-array-class.md) sınıfına.

### <a name="syntax"></a>Sözdizimi

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tür tutamaç-nesne`Array<TArg>^`

### <a name="remarks"></a>Açıklamalar

[Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) standart bir C++ sınıfı şablondur ve [Platform::Array](../cppcx/platform-array-class.md) bir ref sınıfıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
