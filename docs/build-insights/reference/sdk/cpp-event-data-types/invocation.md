---
title: Çağırma sınıfı
description: C++ Build Insights SDK Çağırma sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fcb087d46ea445251b0108f811545a44c26f421e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324636"
---
# <a name="invocation-class"></a>Çağırma sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `Invocation` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. [DerLEYICI](../event-table.md#compiler) veya [LINKER](../event-table.md#linker) olayıyla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Invocation : public Activity
{
    const INVOCATION_DATA* data_;

public:
    enum class Type
    {
        CL      = MSVC_TOOL_CODE_CL,
        LINK    = MSVC_TOOL_CODE_LINK
    };

    Invocation(const RawEvent& event);

    Type             Type() const;
    const char*      ToolVersionString() const;
    const wchar_t*   WorkingDirectory() const;
    const wchar_t*   ToolPath() const;

    const INVOCATION_VERSION_DATA& ToolVersion() const;
};
```

## <a name="members"></a>Üyeler

[Etkinlik](activity.md) taban sınıfından devralınan üyelerle `Invocation` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Çağırma](#invocation)

### <a name="functions"></a>İşlevler

[ToolPath](#tool-path)
[ToolVersion](#tool-version)
[ToolVersionString](#tool-version-string)
[Tipi](#type)
Çalışma[Rehberi](#working-directory)

## <a name="invocation"></a><a name="invocation"></a>Çağırma

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
[DERLEYICI](../event-table.md#compiler) veya [LINKER](../event-table.md#linker) olayı.

## <a name="toolpath"></a><a name="tool-path"></a>Araç Yolu

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan araca giden mutlak yol.

## <a name="toolversion"></a><a name="tool-version"></a>ToolVersion

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Çağrılan](../c-event-data-types/invocation-version-data-struct.md) aracın INVOCATION_VERSION_DATA bir başvuru olarak sürümü.

## <a name="toolversionstring"></a><a name="tool-version-string"></a>ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ansi dizesi olarak çağrılan aracın sürümü.

## <a name="type"></a><a name="type"></a>Türü

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan aracı gösteren bir kod.

## <a name="workingdirectory"></a><a name="working-directory"></a>Workingdirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aracın çağrıldığı dizine giden mutlak yol.

::: moniker-end
