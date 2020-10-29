---
title: CommandLine sınıfı
description: C++ derleme öngörüleri SDK komut satırı sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5214f2970329510088184dc3092db66607f4d67e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923339"
---
# <a name="commandline-class"></a>CommandLine sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`CommandLine`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [COMMAND_LINE](../event-table.md#command-line) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [SimpleEvent](simple-event.md) temel sınıfından birlikte, `CommandLine` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[CommandLine](#command-line)

### <a name="functions"></a>İşlevler

[Değer](#value)

## <a name="commandline"></a><a name="command-line"></a> Komut satırı

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[COMMAND_LINE](../event-table.md#command-line) bir olay.

## <a name="value"></a><a name="value"></a> Deeri

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Komut satırı içeren bir dize. Değer bir yanıt dosyasından ve bir CL, \_ CL \_ , bağlantı ve bağlantı gibi ortam değişkenlerinden alınan bağımsız değişkenleri içerir \_ \_ .

::: moniker-end
