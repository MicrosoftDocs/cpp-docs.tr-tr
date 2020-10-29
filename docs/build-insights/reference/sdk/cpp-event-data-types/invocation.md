---
title: Çağırma sınıfı
description: C++ derleme öngörüleri SDK çağırma sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dfd463c7b9ca72dc14ad74b3759fdd1e3730d5a9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923135"
---
# <a name="invocation-class"></a>Çağırma sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Invocation`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [Derleyici](../event-table.md#compiler) veya [bağlayıcı](../event-table.md#linker) olayını eşleştirmek için onu kullanın.

## <a name="syntax"></a>Syntax

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

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `Invocation` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Çağrı](#invocation)

### <a name="functions"></a>İşlevler

[ToolPath](#tool-path) 
 [Araç sürümü](#tool-version) 
 [Toolversionstring](#tool-version-string) 
 [Tür](#type) 
 [WorkingDirectory](#working-directory)

## <a name="invocation"></a><a name="invocation"></a> Çağrılması

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[Derleyici](../event-table.md#compiler) veya [bağlayıcı](../event-table.md#linker) olayı.

## <a name="toolpath"></a><a name="tool-path"></a> ToolPath

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan aracın mutlak yolu.

## <a name="toolversion"></a><a name="tool-version"></a> Araç sürümü

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Dönüş Değeri

[INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) başvuru olarak çağrılan aracın sürümü.

## <a name="toolversionstring"></a><a name="tool-version-string"></a> ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Dönüş Değeri

ANSI dizesi olarak çağrılan aracın sürümü.

## <a name="type"></a><a name="type"></a> Türüyle

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan aracı gösteren bir kod.

## <a name="workingdirectory"></a><a name="working-directory"></a> WorkingDirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aracın çağrıldığı dizinin mutlak yolu.

::: moniker-end
