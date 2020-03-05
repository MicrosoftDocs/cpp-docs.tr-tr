---
title: Çağırma sınıfı
description: C++ BUILD Insights SDK çağırma sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0c4698300a3eeaf77210ad74f84b0c0cd219b457
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333232"
---
# <a name="invocation-class"></a>Çağırma sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Invocation` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Derleyici](../event-table.md#compiler) veya [bağlayıcı](../event-table.md#linker) olayını eşleştirmek için onu kullanın.

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

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte `Invocation` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Çağrılması](#invocation)

### <a name="functions"></a>İşlevler

[ToolPath](#tool-path)
[Toolversion](#tool-version)
[toolversionstring](#tool-version-string)
[tür](#type)
[WorkingDirectory](#working-directory)

## <a name="invocation"></a>Çağrılması

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[Derleyici](../event-table.md#compiler) veya [bağlayıcı](../event-table.md#linker) olayı.

## <a name="tool-path"></a>ToolPath

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan aracın mutlak yolu.

## <a name="tool-version"></a>Araç sürümü

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Dönüş Değeri

[INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) başvuru olarak çağrılan aracın sürümü.

## <a name="tool-version-string"></a>ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Dönüş Değeri

ANSI dizesi olarak çağrılan aracın sürümü.

## <a name="type"></a>Türüyle

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan aracı gösteren bir kod.

## <a name="working-directory"></a>WorkingDirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aracın çağrıldığı dizinin mutlak yolu.

::: moniker-end
