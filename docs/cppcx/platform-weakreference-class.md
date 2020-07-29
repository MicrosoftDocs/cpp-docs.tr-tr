---
title: 'Platform:: WeakReference sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
ms.openlocfilehash: befefba7cc76f24f6dddd58d0c5f040bfd205508
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216602"
---
# <a name="platformweakreference-class"></a>Platform:: WeakReference sınıfı

Bir başvuru sınıfının örneğine zayıf bir başvuruyu temsil eder.

## <a name="syntax"></a>Söz dizimi

```cpp
class WeakReference
```

#### <a name="parameters"></a>Parametreler

### <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Üye|Açıklama|
|------------|-----------------|
|[WeakReference:: WeakReference](#ctor)|WeakReference sınıfının yeni bir örneğini başlatır.|

### <a name="methods"></a>Yöntemler

|Üye|Açıklama|
|------------|-----------------|
|[WeakReference:: Resolve](#resolve)|Temel alınan başvuru sınıfına bir tanıtıcı döndürür veya nesne artık yoksa nullptr.|

### <a name="operators"></a>İşleçler

|Üye|Açıklama|
|------------|-----------------|
|[WeakReference:: operator =](#operator-assign)|WeakReference nesnesine yeni bir değer atar.|
|[WeakReference:: işleç BoolType](#booltype)|Güvenli bool modelini uygular.|

### <a name="remarks"></a>Açıklamalar

WeakReference sınıfının kendisi bir başvuru sınıfı değil ve bu nedenle Platform:: Object ^ öğesinden almıyor ve bir ortak metodun imzasında kullanılamaz.

## <a name="weakreferenceoperator"></a><a name="operator-assign"></a>WeakReference:: operator =

WeakReference 'a bir değer atar.

### <a name="syntax"></a>Sözdizimi

```cpp
WeakReference& operator=(decltype(__nullptr));
WeakReference& operator=(const WeakReference& otherArg);
WeakReference& operator=(WeakReference&& otherArg);
WeakReference& operator=(const volatile ::Platform::Object^ const otherArg);
```

### <a name="remarks"></a>Açıklamalar

Yukarıdaki listede son aşırı yükleme bir WeakReference değişkenine bir başvuru sınıfı atamanıza olanak sağlar. Bu durumda, ref sınıfı [Platform:: Object](../cppcx/platform-object-class.md)^ öğesine Alta ayarlanır. Özgün türü daha sonra [WeakReference:: Resolve \<T> ](#resolve) üye işlevindeki tür parametresi için bağımsız değişken olarak belirterek geri yükleyin.

## <a name="weakreferenceoperator-booltype"></a><a name="booltype"></a>WeakReference:: işleç BoolType

WeakReference sınıfı için güvenli bool modelini uygular. Kodınızdan açıkça çağrılmamalıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
BoolType BoolType();
```

## <a name="weakreferenceresolve-method-platform-namespace"></a><a name="resolve"></a>WeakReference:: Resolve Yöntemi (Platform ad alanı)

Özgün başvuru sınıfına bir tanıtıcı döndürür veya **`nullptr`** nesne artık mevcut değilse.

### <a name="syntax"></a>Söz dizimi

```cpp
template<typename T>
T^ Resolve() const;
```

### <a name="parameters"></a>Parametreler

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

WeakReference nesnesinin daha önce veya nullptr ile ilişkili olduğu başvuru sınıfına yönelik bir tanıtıcı.

### <a name="example"></a>Örnek

```cpp
Bar^ bar = ref new Bar();
//use bar...

if (bar != nullptr)
{
    WeakReference wr(bar);
    Bar^ newReference = wr.Resolve<Bar>();
}
```

Tür parametresinin T, t değil olduğunu unutmayın.

## <a name="weakreferenceweakreference-constructor"></a><a name="ctor"></a>WeakReference:: WeakReference Oluşturucusu

WeakReference oluşturmak için çeşitli yollar sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
WeakReference();
WeakReference(decltype(__nullptr));
WeakReference(const WeakReference& otherArg);
WeakReference(WeakReference&& otherArg);
explicit WeakReference(const volatile ::Platform::Object^ const otherArg);
```

### <a name="example"></a>Örnek

```cpp
MyClass^ mc = ref new MyClass();
WeakReference wr(mc);
MyClass^ copy2 = wr.Resolve<MyClass>();
```

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
