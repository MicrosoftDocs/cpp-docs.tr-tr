---
title: FrontEndFile sınıfı
description: C++ derleme öngörüleri SDK FrontEndFile sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7715a153df538eab94b8de5281a91d4f6b439ff9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920664"
---
# <a name="frontendfile-class"></a>FrontEndFile sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndFile`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FRONT_END_FILE](../event-table.md#front-end-file) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class FrontEndFile : public Activity
{
public:
    FrontEndFile(const RawEvent& event);

    const char* Path() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `FrontEndFile` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FrontEndFile](#front-end-file)

### <a name="functions"></a>İşlevler

[Yol](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a> FrontEndFile

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FRONT_END_FILE](../event-table.md#front-end-file) bir olay.

## <a name="path"></a><a name="path"></a> Yolun

```cpp
const char* Path() const;
```

### <a name="return-value"></a>Dönüş Değeri

UTF-8 ile kodlanmış, dosyanın mutlak yolu.

::: moniker-end
