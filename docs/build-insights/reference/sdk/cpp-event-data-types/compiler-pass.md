---
title: CompilerPass sınıfı
description: C++ Build Insights SDK 'Sı compilerpass sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3c2fa1c2c4be8aaf5bec77b383f93a4b033ca8e3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333477"
---
# <a name="compilerpass-class"></a>CompilerPass sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`CompilerPass` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [BACK_END_PASS](../event-table.md#back-end-pass) veya [FRONT_END_PASS](../event-table.md#front-end-pass) olayı ile eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class CompilerPass : public Activity
{
public:
    enum class PassCode
    {
        FRONT_END,
        BACK_END
    };

    CompilerPass(const RawEvent& event);

    PassCode       PassCode() const;
    const wchar_t* InputSourcePath() const;
    const wchar_t* OutputObjectPath() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `CompilerPass` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[CompilerPass](#compiler-pass)

### <a name="enums"></a>Numaralandırmalar

#### <a name="passcode"></a>Geçiş

|||
|-|-|
|FRONT_END|Ön uç geçişi.|
|BACK_END|Arka uç geçişi.|

### <a name="functions"></a>İşlevler

[Inputsourcepath](#input-source-path)\
[Outputobjectpath](#output-object-path)\
[Geçiş kodu](#pass-code)\

## <a name="compiler-pass"></a>CompilerPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [BACK_END_PASS](../event-table.md#back-end-pass) veya [FRONT_END_PASS](../event-table.md#front-end-pass) olayı.

## <a name="input-source-path"></a>Inputsourcepath

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu derleyici geçişi tarafından işlenen giriş kaynak dosyasının mutlak yolu.

## <a name="output-object-path"></a>OutputObjectPath

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu derleyici geçişi tarafından üretilen çıkış nesnesi dosyasının mutlak yolu.

## <a name="pass-code"></a>Geçiş

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu CompilerPass nesnesi tarafından hangi derleyici geçişinin temsil edileceğini belirten bir kod.

::: moniker-end
