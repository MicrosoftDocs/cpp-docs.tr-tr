---
title: CommandLine sınıfı
description: C++ BUILD Insights SDK komut satırı sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ff16646920fe77f7f3b4cb8a194a38984c3e6c32
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333512"
---
# <a name="commandline-class"></a>CommandLine sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`CommandLine` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [COMMAND_LINE](../event-table.md#command-line) olayına uyacak şekilde kullanın.

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

[SimpleEvent](simple-event.md) temel sınıfından devralınan üyelerle birlikte `CommandLine` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Komut satırı](#command-line)

### <a name="functions"></a>İşlevler

[Değer](#value)

## <a name="command-line"></a>Komut satırı

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[COMMAND_LINE](../event-table.md#command-line) bir olay.

## <a name="value"></a>Deeri

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Komut satırı içeren bir dize. Değer bir yanıt dosyasından ve bir CL, \_CL\_, bağlantı ve \_bağlantı\_olan ortam değişkenlerinden alınan bağımsız değişkenleri içerir.

::: moniker-end
