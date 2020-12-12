---
description: 'Daha fazla bilgi edinin: Platform:: SizeT değer sınıfı'
title: Platform::SizeT değer sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: ebcca27a94d23082374daafaa9fd7db180955a30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308022"
---
# <a name="platformsizet-value-class"></a>Platform::SizeT değer sınıfı

Bir nesnenin boyutunu temsil eder. SizeT, işaretsiz bir veri türüdür.

## <a name="syntax"></a>Syntax

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Üyeler

|Üye|Açıklama|
|------------|-----------------|
|[SizeT:: SizeT Oluşturucusu](#ctor)|Belirtilen değer ile sınıfın yeni bir örneğini başlatır.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="sizetsizet-constructor"></a><a name="ctor"></a> SizeT:: SizeT Oluşturucusu

Belirtilen değer ile yeni bir SizeT örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Parametreler

*value1*<br/>
İşaretsiz 32 bitlik bir değer.

*value2*<br/>
İşaretsiz 32 bitlik bir değere işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
