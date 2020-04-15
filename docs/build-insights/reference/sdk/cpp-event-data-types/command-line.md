---
title: CommandLine sınıfı
description: C++ Build Insights SDK CommandLine sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b35d688acf06579cc27f2fee053ef58032e204e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325054"
---
# <a name="commandline-class"></a>CommandLine sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `CommandLine` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [COMMAND_LINE](../event-table.md#command-line) bir olayı eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>Üyeler

[SimpleEvent](simple-event.md) taban sınıfından devralınan üyelerle `CommandLine` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Commandline](#command-line)

### <a name="functions"></a>İşlevler

[Değer](#value)

## <a name="commandline"></a><a name="command-line"></a>Commandline

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[COMMAND_LINE](../event-table.md#command-line) bir olay.

## <a name="value"></a><a name="value"></a>Değer

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Komut satırı içeren bir dize. Değer, bir yanıt dosyasından \_ve cl, CL,\_Link ve \_LINK\_gibi ortam değişkenlerinden elde edilen bağımsız değişkenleri içerir.

::: moniker-end
