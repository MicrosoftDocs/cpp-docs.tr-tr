---
description: 'Daha fazla bilgi edinin: Platform:: çevik sınıf'
title: 'Platform:: çevik sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- AGILE/Platform::Platform
- AGILE/Platform::Platform::Agile::Agile
- AGILE/Platform::Platform::Agile::Get
- AGILE/Platform::Platform::Agile::GetAddressOf
- AGILE/Platform::Platform::Agile::GetAddressOfForInOut
- AGILE/Platform::Platform::Agile::Release
helpviewer_keywords:
- Platform::Agile
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
ms.openlocfilehash: 6407bbfecdc84cdb47024e09f632a6e574439814
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312182"
---
# <a name="platformagile-class"></a>Platform:: çevik sınıfı

Çevik bir nesne olarak MashalingBehavior = standardı olan bir nesneyi temsil eder ve bu da çalışma zamanı iş parçacığı özel durumlarının olasılığını önemli ölçüde azaltır. , `Agile<T>` Çevik olmayan nesnenin aynı veya farklı bir iş parçacığından çağrılması veya çağırılabilmesi için sağlar. Daha fazla bilgi için bkz. [Threading and Marshal](../cppcx/threading-and-marshaling-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class Agile;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Çevik olmayan sınıf için typeName.

### <a name="remarks"></a>Açıklamalar

Windows Çalışma Zamanı sınıfların çoğu çevik. Çevik bir nesne, aynı veya farklı bir iş parçacığında işlem içi veya proc dışı bir nesne tarafından çağrılabilir veya çağrılabilir. Bir nesne çevik değilse, çevik olmayan nesneyi çevik bir nesne içinde sarın `Agile<T>` . Ardından `Agile<T>` nesne sıralanabilir ve temeldeki çevik olmayan nesne kullanılabilir.

`Agile<T>`Sınıfı, yerel, standart bir C++ sınıfıdır ve gerektirir `agile.h` . Çevik olmayan nesne ve çevik nesne *bağlamını* temsil eder. Bağlam, çevik bir nesnenin iş parçacığı modeli ve sıralama davranışını belirtir. İşletim sistemi, bir nesnenin nasıl hazırlanacağını belirlemede bağlamını kullanır.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Çevik:: çevik](#ctor)|Çevik sınıfının yeni bir örneğini başlatır.|
|[Çevik:: ~ çevik yok edicisi](#dtor)|Çevik sınıfının geçerli örneğini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Çevik:: Get](#get)|Geçerli çevik nesne tarafından temsil edilen nesneye bir tanıtıcı döndürür.|
|[Çevik:: GetAddressOf](#getaddressof)|Geçerli çevik nesnesini yeniden başlatır ve ardından türü bir nesneye yapılan tanıtıcının adresini döndürür `T` .|
|[Çevik:: Getaddressofforınout](#getaddressofforinout)|Geçerli çevik nesnenin temsil ettiği nesne için bir tanıtıcının adresini döndürür.|
|[Çevik:: yayın](#release)|Geçerli çevik nesnenin temel alınan nesnesini ve bağlamını atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Çevik:: operator->](#operator-arrow)|Geçerli çevik nesnenin temsil ettiği nesneye bir tanıtıcı alır.|
|[Çevik:: operator =](#operator-assign)|Geçerli çevik nesnesine belirtilen değeri atar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Object`

`Agile`

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Üst bilgi:** çevik. h

## <a name="agileagile-constructor"></a><a name="ctor"></a> Çevik:: çevik Oluşturucu

Çevik sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
Agile();
Agile(T^ object);
Agile(const Agile<T>& object);
Agile(Agile<T>&& object);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon typeName parametresi tarafından belirtilen bir tür.

*object*<br/>
Bu oluşturucunun ikinci sürümünde, yeni bir çevik örneği başlatmak için kullanılan bir nesne. Üçüncü sürümünde, yeni çevik örneğe kopyalanmış nesne. Dördüncü sürümde, yeni çevik örneğe taşınan nesne.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucunun ilk sürümü varsayılan oluşturucudur. İkinci sürüm, parametresi tarafından belirtilen nesneden yeni çevik örnek sınıfı başlatır `object` . Üçüncü sürüm kopya oluşturucudur. Dördüncü sürüm, taşıma oluşturucusudur. Bu Oluşturucu özel durum oluşturmaz.

## <a name="agileagile-destructor"></a><a name="dtor"></a> Çevik:: ~ çevik yok edicisi

Çevik sınıfının geçerli örneğini yok eder.

### <a name="syntax"></a>Syntax

```cpp
~Agile();
```

### <a name="remarks"></a>Açıklamalar

Bu yıkıcı ayrıca geçerli çevik nesne tarafından temsil edilen nesneyi serbest bırakır.

## <a name="agileget-method"></a><a name="get"></a> Çevik:: get yöntemi

Geçerli çevik nesne tarafından temsil edilen nesneye bir tanıtıcı döndürür.

### <a name="syntax"></a>Syntax

```cpp
T^ Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli çevik nesne tarafından temsil edilen nesneye yönelik bir tanıtıcı.

Dönüş değerinin türü aslında açıklanmamıştır bir iç türdür. Dönüş değerini tutmanın uygun bir yolu, **`auto`** türü, tür kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin, `auto x = myAgileTvariable->Get();`.

## <a name="agilegetaddressof-method"></a><a name="getaddressof"></a> Çevik:: GetAddressOf yöntemi

Geçerli çevik nesnesini yeniden başlatır ve ardından türü bir nesneye yapılan tanıtıcının adresini döndürür `T` .

### <a name="syntax"></a>Sözdizimi

```cpp
T^* GetAddressOf() throw();
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon typeName parametresi tarafından belirtilen bir tür.

### <a name="return-value"></a>Dönüş Değeri

Türü bir nesneye yönelik tanıtıcının adresi `T` .

### <a name="remarks"></a>Açıklamalar

Bu işlem, türünde bir nesnenin geçerli temsilini serbest bırakır `T` ; çevik nesnenin veri üyelerini yeniden başlatır; geçerli iş parçacığı bağlamını alır; ardından, çevik olmayan bir nesneyi temsil eden bir tanıtıcıdan nesne değişkeninin adresini döndürür. Çevik sınıf örneğinin bir nesneyi göstermesini sağlamak için, nesneyi çevik sınıf örneğine atamak için atama işlecini ([çevik:: operator =](#operator-assign)) kullanın.

## <a name="agilegetaddressofforinout-method"></a><a name="getaddressofforinout"></a> Çevik:: Getaddressofforınout yöntemi

Geçerli çevik nesnenin temsil ettiği nesne için bir tanıtıcının adresini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T^* GetAddressOfForInOut()  throw();
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon typeName parametresi tarafından belirtilen bir tür.

### <a name="return-value"></a>Dönüş Değeri

Geçerli çevik nesne tarafından temsil edilen nesneye yönelik tanıtıcının adresi.

### <a name="remarks"></a>Açıklamalar

Bu işlem geçerli iş parçacığı bağlamını alır ve ardından nesnenin temelindeki bir tanıtıcının adresini döndürür.

## <a name="agilerelease-method"></a><a name="release"></a> Çevik:: Release yöntemi

Geçerli çevik nesnenin temel alınan nesnesini ve bağlamını atar.

### <a name="syntax"></a>Syntax

```cpp
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Mevcut çevik nesnenin temel alınan nesnesi ve bağlamı atılır, varsa, çevik nesnenin değeri null olarak ayarlanır.

## <a name="agileoperator-gt-operator"></a><a name="operator-arrow"></a> Çevik:: operator- &gt; işleci

Geçerli çevik nesnenin temsil ettiği nesneye bir tanıtıcı alır.

### <a name="syntax"></a>Syntax

```cpp
T^ operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli çevik nesne tarafından temsil edilen nesneye yönelik bir tanıtıcı.

Bu işleç aslında açıklanmaedilmemiş bir iç tür döndürür. Dönüş değerini tutmanın uygun bir yolu, **`auto`** türü, tür kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır.

## <a name="agileoperator-operator"></a><a name="operator-assign"></a> Çevik:: operator = Işleci

Belirtilen nesneyi geçerli çevik nesnesine atar.

### <a name="syntax"></a>Sözdizimi

```cpp
Agile<T> operator=( T^ object ) throw();
Agile<T> operator=( const Agile<T>& object ) throw();
Agile<T> operator=( Agile<T>&& object ) throw();
T^ operator=( IUnknown* lp ) throw();
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon TypeName tarafından belirtilen tür.

*object*<br/>
Geçerli çevik nesnesine kopyalanmış veya taşınmış bir nesne için nesne veya tanıtıcı.

*'nin*<br/>
Bir nesnenin IUnknown arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Türünde bir nesne için bir tanıtıcı `T`

### <a name="remarks"></a>Açıklamalar

Atama işlecinin ilk sürümü bir tanıtıcıyı bir başvuru türüne geçerli çevik nesnesine kopyalar. İkinci sürüm, bir başvuruyu çevik bir türe geçerli çevik nesnesine kopyalar. Üçüncü sürüm çevik bir türü geçerli çevik nesnesine taşımaz. Dördüncü sürüm, geçerli çevik nesnesine bir COM nesnesi işaretçisi taşıdıkça.

Atama işlemi, geçerli çevik nesnenin bağlamını otomatik olarak devam ettirir.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
