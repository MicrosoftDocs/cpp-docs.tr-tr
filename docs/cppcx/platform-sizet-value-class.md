---
title: Platform::SizeT değer sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 7f81cb9e1fc2ef7a74cb3878c369e4d7d14e3d90
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330147"
---
# <a name="platformsizet-value-class"></a>Platform::SizeT değer sınıfı

Bir nesnenin boyutunu temsil eder. SizeT imzasız veri türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Üyeler

|Üye|Açıklama|
|------------|-----------------|
|[SizeT::SizeT Oluşturucusu](#ctor)|Belirtilen değerle sınıfının yeni bir örneğini başlatır.|

### <a name="requirements"></a>Gereksinimler

**En düşük desteklenen istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** Platform

**Meta veri:** platform.winmd

## <a name="ctor"></a>  SizeT::SizeT Oluşturucusu

Belirtilen değerle SizeT yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Parametreler

*Değer1*<br/>
İmzalanmamış bir 32-bit değeri.

*Value2*<br/>
Bir işaretsiz 32-bit değere işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
