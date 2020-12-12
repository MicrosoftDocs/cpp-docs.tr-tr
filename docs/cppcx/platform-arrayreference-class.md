---
description: 'Daha fazla bilgi edinin: Platform:: ArrayReference sınıfı'
title: 'Platform:: ArrayReference sınıfı'
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: 6d883dd369b4b439bd02a337017e8c13731999d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284089"
---
# <a name="platformarrayreference-class"></a>Platform:: ArrayReference sınıfı

`ArrayReference` , giriş parametrelerinde bir C stili diziyi doldurmanız istediğinizde [Platform:: Array ^](../cppcx/platform-array-class.md) öğesini giriş parametrelerinde yerine getirmek için kullanabileceğiniz bir iyileştirme türüdür.

## <a name="syntax"></a>Syntax

```cpp
class ArrayReference
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ArrayReference:: ArrayReference](#ctor)|`ArrayReference` sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[ArrayReference:: operator () Işleci](#operator-call)|Bunu `ArrayReference` bir öğesine dönüştürür `Platform::Array<T>^*` .|
|[ArrayReference:: operator = Işleci](#operator-assign)|Bu örneğe bir diğerinin içeriğini atar `ArrayReference` .|

## <a name="exceptions"></a>Özel durumlar

### <a name="remarks"></a>Açıklamalar

`ArrayReference`C stili bir diziyi doldurmak için kullanarak, önce bir `Platform::Array` değişkene ve sonra C stili diziye kopyalamaya dahil edilecek ek kopyalama işlemini önleyin. Kullandığınızda `ArrayReference` yalnızca bir kopyalama işlemi vardır. Kod örneği için bkz. [Array ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Üstbilgi:** vccorlib. h

## <a name="arrayreferencearrayreference-constructor"></a><a name="ctor"></a> ArrayReference:: ArrayReference Oluşturucusu

[Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>Parametreler

*dataArg*<br/>
Dizi verilerine yönelik bir işaretçi.

*Sizliye g*<br/>
Kaynak dizideki öğelerin sayısı.

*Diğerarg*<br/>
`ArrayReference`Yeni örneği başlatmak için verileri taşınacak olan nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="arrayreferenceoperator-operator"></a><a name="operator-assign"></a> ArrayReference:: operator = Işleci

Move semantiğini kullanarak belirtilen nesneyi geçerli [Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) nesnesine atar.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Parametreler

*Diğerarg*<br/>
Geçerli nesneye taşınan nesne `ArrayReference` .

### <a name="return-value"></a>Dönüş Değeri

Türündeki bir nesneye başvuru `ArrayReference` .

### <a name="remarks"></a>Açıklamalar

`Platform::ArrayReference` , başvuru sınıfı değil, standart bir C++ sınıf şablonudur.

## <a name="arrayreferenceoperator-operator"></a><a name="operator-call"></a> ArrayReference:: operator () Işleci

Geçerli [Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) nesnesini bir [Platform:: Array](../cppcx/platform-array-class.md) sınıfına geri dönüştürür.

### <a name="syntax"></a>Syntax

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Dönüş Değeri

Türünden nesne tanıtıcısı `Array<TArg>^`

### <a name="remarks"></a>Açıklamalar

[Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) standart bir C++ sınıf şablonudur ve [Platform:: Array](../cppcx/platform-array-class.md) bir başvuru sınıfıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
