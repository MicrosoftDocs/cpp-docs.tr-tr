---
title: FileOutput sınıfı
description: C++ Build Insights SDK FileOutput sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 37823da8a4aaac0ce4094583b8aee8ac1eb04aaa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324812"
---
# <a name="fileoutput-class"></a>FileOutput sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `FileOutput` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. Bir [EXECUTABLE_IMAGE_OUTPUT,](../event-table.md#executable-image-output) [EXP_OUTPUT,](../event-table.md#exp-output) [IMP_LIB_OUTPUT,](../event-table.md#imp-lib-output) [LIB_OUTPUT](../event-table.md#lib-output)veya [OBJ_OUTPUT](../event-table.md#obj-output) olay maç için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class FileOutput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileOutput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>Üyeler

[SimpleEvent](simple-event.md) taban sınıfından devralınan üyelerle `FileOutput` birlikte, sınıf aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Dosya Çıktısı](#file-output)

### <a name="functions"></a>İşlevler

[Yol](#path)
[Türü](#type)

## <a name="fileoutput"></a><a name="file-output"></a>Dosya Çıktısı

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
Bir [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output), veya [OBJ_OUTPUT](../event-table.md#obj-output) olay.

## <a name="path"></a><a name="path"></a>Yolu

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıktı dosyasına giden mutlak yol.

## <a name="type"></a><a name="type"></a>Türü

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıktı dosyasının türünü açıklayan bir kod.

::: moniker-end
