---
title: Platform::SizeT değer sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 5add9212dc2655bc37cd357741073f855b009bde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322155"
---
# <a name="platformsizet-value-class"></a>Platform::SizeT değer sınıfı

Nesnenin boyutunu temsil eder. SizeT imzasız bir veri türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Üyeler

|Üye|Açıklama|
|------------|-----------------|
|[SizeT::SizeT oluşturucu](#ctor)|Belirtilen değere sahip sınıfın yeni bir örneğini başolarak adlandırır.|

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Meta veriler:** platform.winmd

## <a name="sizetsizet-constructor"></a><a name="ctor"></a>SizeT::SizeT oluşturucu

Belirtilen değerle SizeT'nin yeni bir örneğini başolarak karşılar.

### <a name="syntax"></a>Sözdizimi

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Parametreler

*değer1*<br/>
İmzasız 32 bit lik bir değer.

*değeri2*<br/>
İmzasız 32 bit değeri için işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
