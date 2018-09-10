---
title: Platform::ArrayReference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
dev_langs:
- C++
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d11aa58ba502e4e5eb4122e1d596da978a4e4ef6
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106576"
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference sınıfı

`ArrayReference` için yedek bir iyileştirme türü [Platform::Array ^](../cppcx/platform-array-class.md) bir C tarzı dizi giriş verileriyle doldurmak istediğiniz zaman giriş parametreleri.

## <a name="syntax"></a>Sözdizimi

```cpp
class ArrayReference
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ArrayReference::ArrayReference](#ctor)|Yeni bir örneğini başlatır `ArrayReference` sınıfı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[ArrayReference::operator() işleci](#operator-call)|Bu dönüştürür `ArrayReference` için bir `Platform::Array<T>^*`.|
|[ArrayReference::operator = işleci](#operator-assign)|Başka bir deponun içeriğini atar `ArrayReference` Bu örneği.|

## <a name="exceptions"></a>Özel Durumlar

### <a name="remarks"></a>Açıklamalar

Kullanarak `ArrayReference` bir C tarzı dizi doldurmak için ilk kopyalama söz konusu ek kopyalama işlemi kaçının bir `Platform::Array` değişken ve sonra C tarzı dizi. Kullanırken `ArrayReference`, yalnızca bir kopyalama işlemi yok. Kod örneği için bkz: [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Başlık:** vccorlib.h

## <a name="ctor"></a>  ArrayReference::ArrayReference Oluşturucusu

Yeni bir örneğini başlatır [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) sınıfı.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)

```

### <a name="parameters"></a>Parametreler

*dataArg*<br/>
Dizi verileri için bir işaretçi.

*sizeArg*<br/>
Kaynak dizideki öğelerin sayısı.

*otherArg*<br/>
Bir `ArrayReference` nesnesinin verisini yeni örneği başlatmak için taşınacak.

### <a name="remarks"></a>Açıklamalar

## <a name="operator-assign"></a>  ArrayReference::operator = işleci

Belirtilen nesnenin geçerli atar [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) taşıma semantiği kullanarak nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Parametreler

*otherArg*<br/>
Geçerli taşınır nesne `ArrayReference` nesne.

### <a name="return-value"></a>Dönüş Değeri

Türü bir nesneye başvuru `ArrayReference`.

### <a name="remarks"></a>Açıklamalar

`Platform::ArrayReference` Standart C++ sınıf şablonu, başvuru sınıfı ' dir.

## <a name="operator-call"></a>  ArrayReference::operator() işleci

Geçerli dönüştürür [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) geri nesnesini bir [Platform::Array](../cppcx/platform-array-class.md) sınıfı.

### <a name="syntax"></a>Sözdizimi

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tanıtıcı nesne türü `Array<TArg>^`

### <a name="remarks"></a>Açıklamalar

[Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) ve [Platform::Array](../cppcx/platform-array-class.md) standart C++ sınıf şablonları, başvuru değil sınıflardır.

## <a name="see-also"></a>Ayrıca Bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)