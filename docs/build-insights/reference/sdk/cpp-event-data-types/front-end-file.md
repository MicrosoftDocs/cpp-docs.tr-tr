---
title: FrontEndFile sınıfı
description: C++ BUILD Insights SDK FrontEndFile sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 094b1326765e0e8edb00534ecb3d94c46702d4ec
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333288"
---
# <a name="frontendfile-class"></a>FrontEndFile sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FrontEndFile` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FRONT_END_FILE](../event-table.md#front-end-file) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class FrontEndFile : public Activity
{
public:
    FrontEndFile(const RawEvent& event);

    const char* Path() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `FrontEndFile` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FrontEndFile](#front-end-file)

### <a name="functions"></a>İşlevler

[Path](#path)

## <a name="front-end-file"></a>FrontEndFile

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FRONT_END_FILE](../event-table.md#front-end-file) bir olay.

## <a name="path"></a>Yolun

```cpp
const char* Path() const;
```

### <a name="return-value"></a>Dönüş Değeri

UTF-8 ile kodlanmış, dosyanın mutlak yolu.

::: moniker-end
