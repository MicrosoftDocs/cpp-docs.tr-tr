---
title: Platform::Agile Sınıfı
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
ms.openlocfilehash: 0822cef10b199a5bc3b33f116065816e380bf8a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376507"
---
# <a name="platformagile-class"></a>Platform::Agile Sınıfı

MashalingBehavior=Standart çevik bir nesne olarak sahip olan ve çalışma zamanı iş parçacığı özel durumları olasılığını büyük ölçüde azaltan bir nesneyi temsil eder. Çevik `Agile<T>` olmayan nesnenin aynı veya farklı bir iş parçacığının çağrılmasını veya çağrılmasını sağlar. Daha fazla bilgi için [Threading ve Marshaling'e](../cppcx/threading-and-marshaling-c-cx.md)bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class Agile;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Çevik olmayan sınıfın yazı adı.

### <a name="remarks"></a>Açıklamalar

Windows Runtime'daki sınıfların çoğu çeviktir. Çevik bir nesne, aynı veya farklı bir iş parçacığında proc veya proc dışı bir nesneyi arayabilir veya çağırılabilir. Bir nesne çevik değilse, çevik olmayan nesneyi çevik `Agile<T>` olan bir nesneye sarın. Daha `Agile<T>` sonra nesne marshaled olabilir ve altta yatan çevik olmayan nesne kullanılabilir.

Sınıf `Agile<T>` yerel, standart bir C++ `agile.h`sınıfıdır ve . Çevik olmayan nesneyi ve Çevik nesnenin *bağlamını*temsil eder. Bağlam, çevik bir nesnenin iş parçacığı modelini ve mareşaldavranışını belirtir. İşletim sistemi, bir nesneyi nasıl keşe edineceklerini belirlemek için bağlamı kullanır.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Çevik::Çevik](#ctor)|Çevik sınıfın yeni bir örneğini başolarak karşılar.|
|[Çevik::~Çevik Yıkıcı](#dtor)|Çevik sınıfın geçerli örneğini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Çevik::Get](#get)|Geçerli Çevik nesne tarafından temsil edilen nesneye bir tanıtıcı döndürür.|
|[Çevik::GetAddressOf](#getaddressof)|Geçerli Çevik nesneyi yeniden başharfe döndürür ve bir tanıtıcının adresini türdeki `T`bir nesneye döndürür.|
|[Çevik::GetAddressOfForInOut](#getaddressofforinout)|Bir tanıtıcının adresini geçerli Çevik nesne tarafından temsil edilen nesneye döndürür.|
|[Çevik::Yayın](#release)|Geçerli Çevik nesnenin alttaki nesnesini ve bağlamını atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[Çevik::operatör->](#operator-arrow)|Geçerli Çevik nesne tarafından temsil edilen nesneye bir tanıtıcı alır.|
|[Çevik::operator=](#operator-assign)|Geçerli Çevik nesneye belirtilen değeri atar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Object`

`Agile`

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Üstbilgi:** çevik.h

## <a name="agileagile-constructor"></a><a name="ctor"></a>Çevik::Çevik Yapıcı

Çevik sınıfın yeni bir örneğini başolarak karşılar.

## <a name="syntax"></a>Sözdizimi

```cpp
Agile();
Agile(T^ object);
Agile(const Agile<T>& object);
Agile(Agile<T>&& object);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon türü parametresi tarafından belirtilen bir tür.

*Nesne*<br/>
Bu oluşturucunun ikinci sürümünde, yeni bir Çevik örneğini başlatmak için kullanılan bir nesne. Üçüncü sürümde, yeni Çevik örneğe kopyalanan nesne. Dördüncü sürümde, yeni Çevik örneğe taşınan nesne.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucunun ilk sürümü varsayılan oluşturucudur. İkinci sürüm, parametre tarafından belirtilen nesneden yeni `object` Çevik örnek sınıfını başharfe ait hale eleştirir. Üçüncü sürüm kopya oluşturucudur. Dördüncü sürüm hareket oluşturucudur. Bu oluşturucu özel durumlar atamaz.

## <a name="agileagile-destructor"></a><a name="dtor"></a>Çevik::~Çevik Yıkıcı

Çevik sınıfın geçerli örneğini yok eder.

## <a name="syntax"></a>Sözdizimi

```cpp
~Agile();
```

### <a name="remarks"></a>Açıklamalar

Bu yıkıcı, geçerli Çevik nesne tarafından temsil edilen nesneyi de serbest bırakır.

## <a name="agileget-method"></a><a name="get"></a>Çevik::Get Metodu

Geçerli Çevik nesne tarafından temsil edilen nesneye bir tanıtıcı döndürür.

## <a name="syntax"></a>Sözdizimi

```cpp
T^ Get() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Çevik nesne tarafından temsil edilen nesneye bir tutamaç.

İade değerinin türü aslında açıklanmayan bir iç türüdür. İade değerini tutmanın kullanışlı bir yolu, onu **otomatik** tür kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene atamaktır. Örneğin, `auto x = myAgileTvariable->Get();`.

## <a name="agilegetaddressof-method"></a><a name="getaddressof"></a>Çevik::GetAddressOf Yöntemi

Geçerli Çevik nesneyi yeniden başharfe döndürür ve bir tanıtıcının adresini türdeki `T`bir nesneye döndürür.

## <a name="syntax"></a>Sözdizimi

```cpp
T^* GetAddressOf() throw();
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon türü parametresi tarafından belirtilen bir tür.

### <a name="return-value"></a>Dönüş Değeri

Bir tanıtıcının türündeki `T`bir nesneye adresi.

### <a name="remarks"></a>Açıklamalar

Bu işlem, varsa, türündeki `T`bir nesnenin geçerli temsilini salar; Çevik nesnenin veri üyelerini yeniden başharfe çeker; geçerli iş parçacığı bağlamını edinir; ve sonra çevik olmayan bir nesneyi temsil eden bir iştiş-nesne değişkeninin adresini döndürür. Bir Çevik sınıf örneğinin bir nesneyi temsil etmesini sağlamak için, nesneyi Çevik sınıf örneğine atamak için atama işleci[(Çevik::işleç=)](#operator-assign)kullanın.

## <a name="agilegetaddressofforinout-method"></a><a name="getaddressofforinout"></a>Çevik::GetAddressOfForInOut Yöntemi

Bir tanıtıcının adresini geçerli Çevik nesne tarafından temsil edilen nesneye döndürür.

## <a name="syntax"></a>Sözdizimi

```cpp
T^* GetAddressOfForInOut()  throw();
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon türü parametresi tarafından belirtilen bir tür.

### <a name="return-value"></a>Dönüş Değeri

Geçerli Çevik nesne tarafından temsil edilen nesneye bir tanıtıcı adresi.

### <a name="remarks"></a>Açıklamalar

Bu işlem geçerli iş parçacığı bağlamını kazanır ve sonra bir tanıtıcının adresini alttaki nesneye döndürür.

## <a name="agilerelease-method"></a><a name="release"></a>Çevik::Yayın Yöntemi

Geçerli Çevik nesnenin alttaki nesnesini ve bağlamını atar.

## <a name="syntax"></a>Sözdizimi

```cpp
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Geçerli Çevik nesnenin temel nesnesi ve bağlamı varsa atılır ve çevik nesnenin değeri null olarak ayarlanır.

## <a name="agileoperator-gt-operator"></a><a name="operator-arrow"></a>Çevik:::operatör-&gt; Operatör

Geçerli Çevik nesne tarafından temsil edilen nesneye bir tanıtıcı alır.

## <a name="syntax"></a>Sözdizimi

```cpp
T^ operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Çevik nesne tarafından temsil edilen nesneye bir tutamaç.

Bu işleç aslında açıklanmayan bir iç türü döndürür. İade değerini tutmanın kullanışlı bir yolu, onu **otomatik** tür kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene atamaktır.

## <a name="agileoperator-operator"></a><a name="operator-assign"></a>Çevik:::operator= Operatör

Belirtilen nesneyi geçerli Çevik nesneye atar.

## <a name="syntax"></a>Sözdizimi

```cpp
Agile<T> operator=( T^ object ) throw();
Agile<T> operator=( const Agile<T>& object ) throw();
Agile<T> operator=( Agile<T>&& object ) throw();
T^ operator=( IUnknown* lp ) throw();
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon türü tarafından belirtilen tür.

*Nesne*<br/>
Nesne veya tutamacı, kopyalanan veya geçerli Çevik nesneye taşınan bir nesneye taşınır.

*Lp*<br/>
Bir nesnenin Bilinmeyen arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Türdeki bir nesneye bir tutamaç`T`

### <a name="remarks"></a>Açıklamalar

Atama işlecinin ilk sürümü, geçerli Çevik nesneye bir başvuru türüne bir tanıtıcı kopyalar. İkinci sürüm, geçerli Çevik nesneye bir Çevik türüne yapılan başvuruyu kopyalar. Üçüncü sürüm, çevik bir türü geçerli Çevik nesneye taşır. Dördüncü sürüm, bir işaretçiyi geçerli Çevik nesneye com nesnesine taşır.

Atama işlemi, geçerli Çevik nesnenin bağlamını otomatik olarak devam ettirmez.

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)
