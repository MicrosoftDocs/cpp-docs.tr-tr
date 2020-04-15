---
title: CompilerPass sınıfı
description: C++ Build Insights SDK CompilerPass sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 11af981b647d5183f88dad024d90c0ef4f8a28bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325036"
---
# <a name="compilerpass-class"></a>CompilerPass sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `CompilerPass` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. bir [BACK_END_PASS](../event-table.md#back-end-pass) veya [FRONT_END_PASS](../event-table.md#front-end-pass) olayı eşleştirmek için kullanın.

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

[Etkinlik](activity.md) taban sınıfından devralınan üyelerle `CompilerPass` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[DerleyiciPass](#compiler-pass)

### <a name="enums"></a>Numaralandırmalar

#### <a name="passcode"></a>Şifre

|||
|-|-|
|FRONT_END|Ön uç pası.|
|BACK_END|Arka uç pası.|

### <a name="functions"></a>İşlevler

[InputSourcePath](#input-source-path)\
[OutputObjectPath](#output-object-path)\
[Şifre](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a>DerleyiciPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[BACK_END_PASS](../event-table.md#back-end-pass) veya [FRONT_END_PASS](../event-table.md#front-end-pass) bir olay.

## <a name="inputsourcepath"></a><a name="input-source-path"></a>InputSourcePath

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu derleyici geçişi tarafından işlenen giriş kaynağı dosyasına mutlak yol.

## <a name="outputobjectpath"></a><a name="output-object-path"></a>OutputObjectPath

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu derleyici geçişi tarafından üretilen çıktı nesnesi dosyasına mutlak yol.

## <a name="passcode"></a><a name="pass-code"></a>Şifre

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Derleyici geçişinin bu CompilerPass nesnesi tarafından temsil edildiğini belirten bir kod.

::: moniker-end
