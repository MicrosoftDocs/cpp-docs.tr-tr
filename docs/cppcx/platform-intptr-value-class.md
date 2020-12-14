---
description: 'Daha fazla bilgi edinin: Platform:: IntPtr değer sınıfı'
title: Platform::IntPtr değer sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
ms.openlocfilehash: 18c5316eaae84b1e6af4e54d86ef876d81a866ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295269"
---
# <a name="platformintptr-value-class"></a>Platform::IntPtr değer sınıfı

İmzalı bir işaretçiyi veya tanıtıcıyı temsil eder ve boyutu platforma özgü olan (32 bit veya 64 bit).

## <a name="syntax"></a>Syntax

```cpp
public value struct IntPtr
```

### <a name="members"></a>Üyeler

IntPtr aşağıdaki üyelere sahiptir:

|Üye|Açıklama|
|------------|-----------------|
|[IntPtr:: IntPtr](#ctor)|Yeni bir IntPtr örneği başlatır.|
|[IntPtr:: op_explicit Işleci](#op-explicit)|Belirtilen parametreyi bir IntPtr öğesine veya bir IntPtr değerine bir işaretçiye dönüştürür.|
|[IntPtr:: Toınt32](#toint32)|Geçerli IntPtr 'ı 32 bitlik bir tamsayıya dönüştürür.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="intptrintptr-constructor"></a><a name="ctor"></a> IntPtr:: IntPtr Oluşturucusu

Belirtilen değere sahip bir IntPtr 'ın yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );
```

### <a name="parameters"></a>Parametreler

*değer*<br/>
64 bitlik bir tanıtıcı veya işaretçi ya da 64 bit değerine yönelik bir işaretçi ya da bir 64 bit değere dönüştürülebilen bir 32 bit değeri.

## <a name="intptrop_explicit-operator"></a><a name="op-explicit"></a> IntPtr:: op_Explicit işleci

Belirtilen parametreyi bir IntPtr öğesine veya bir IntPtr değerine bir işaretçiye dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );
```

### <a name="parameters"></a>Parametreler

*value1*<br/>
Bir tanıtıcı veya IntPtr işaretçisi.

*value2*<br/>
Bir IntPtr 'a dönüştürülebilen 32 bitlik bir tamsayı.

*value3*<br/>
Bir IntPtr.

### <a name="return-value"></a>Dönüş Değeri

Birinci ve ikinci işleçler bir IntPtr döndürür. Üçüncü işleç, geçerli IntPtr tarafından temsil edilen değere bir işaretçi döndürür.

## <a name="intptrtoint32-method"></a><a name="toint32"></a> IntPtr:: ToInt32 yöntemi

Geçerli IntPtr değerini 32 bitlik bir tamsayıya dönüştürür.

### <a name="syntax"></a>Syntax

```cpp
int32 IntPtr::ToInt32();
```

### <a name="return-value"></a>Dönüş Değeri

32 bitlik bir tamsayı.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
