---
title: 'Platform:: ArrayReference sınıfı'
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: f7e587902f1c99b294ed79255397aeffccee26b5
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587917"
---
# <a name="platformarrayreference-class"></a>Platform:: ArrayReference sınıfı

`ArrayReference`, giriş parametrelerinde bir C stili diziyi doldurmanız istediğinizde [Platform:: Array ^](../cppcx/platform-array-class.md) öğesini giriş parametrelerinde yerine getirmek için kullanabileceğiniz bir iyileştirme türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
class ArrayReference
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[ArrayReference:: ArrayReference](#ctor)|@No__t_0 sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Name|Açıklama|
|----------|-----------------|
|[ArrayReference:: operator () Işleci](#operator-call)|Bu `ArrayReference` `Platform::Array<T>^*` dönüştürür.|
|[ArrayReference:: operator = Işleci](#operator-assign)|Bu örneğe başka bir `ArrayReference` içeriğini atar.|

## <a name="exceptions"></a>Özel Durumlar

### <a name="remarks"></a>Açıklamalar

C stili bir diziyi doldurmak için `ArrayReference` kullanarak, önce bir `Platform::Array` değişkenine ve sonra C stili dizi içine kopyalamaya dahil edilecek ek kopyalama işlemini önleyin. @No__t_0 kullandığınızda yalnızca bir kopyalama işlemi vardır. Kod örneği için bkz. [Array ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Üstbilgi:** vccorlib. h

## <a name="ctor"></a>ArrayReference:: ArrayReference Oluşturucusu

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
Yeni örneği başlatmak için verileri taşınacak olan bir `ArrayReference` nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="operator-assign"></a>ArrayReference:: operator = Işleci

Move semantiğini kullanarak belirtilen nesneyi geçerli [Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) nesnesine atar.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Parametreler

*Diğerarg*<br/>
Geçerli `ArrayReference` nesnesine taşınan nesne.

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 türündeki bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

`Platform::ArrayReference`, başvuru sınıfı C++ değil, standart bir sınıf şablonudur.

## <a name="operator-call"></a>ArrayReference:: operator () Işleci

Geçerli [Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) nesnesini bir [Platform:: Array](../cppcx/platform-array-class.md) sınıfına geri dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 türünde bir tanıtıcıdan nesne

### <a name="remarks"></a>Açıklamalar

[Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) standart C++ bir sınıf şablonudur ve [Platform:: Array](../cppcx/platform-array-class.md) bir başvuru sınıfıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
