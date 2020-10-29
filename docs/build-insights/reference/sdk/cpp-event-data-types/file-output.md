---
title: FileOutput sınıfı
description: C++ derleme öngörüleri SDK dosyası çıkış sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 65e23715d8ac47a8653215e8bd3ee7a43bbe80a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923248"
---
# <a name="fileoutput-class"></a>FileOutput sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`FileOutput`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)veya [OBJ_OUTPUT](../event-table.md#obj-output) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

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

Devralınan üyelerin [SimpleEvent](simple-event.md) temel sınıfından birlikte, `FileOutput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FileOutput](#file-output)

### <a name="functions"></a>İşlevler

[Yol](#path) 
 [Tür](#type)

## <a name="fileoutput"></a><a name="file-output"></a> Dosya çıkışı

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)veya [OBJ_OUTPUT](../event-table.md#obj-output) olay.

## <a name="path"></a><a name="path"></a> Yolun

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış dosyasının mutlak yolu.

## <a name="type"></a><a name="type"></a> Türüyle

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış dosyasının türünü tanımlayan bir kod.

::: moniker-end
